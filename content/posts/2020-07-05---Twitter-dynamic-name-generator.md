---
title: Twitter Dynamic Name Generator 
date: "2020-07-05T23:46:37.121Z"
template: "post"
draft: false
slug: "twitter-dynamice-name-generator"
category: "Nodejs"
tags:
  - "node"
  - "cron"
  - "aws"
  - "twitter"
description: "The Twitter dynamic name generator is a pet project in which the twitter profile name updates for every minute with the followers count. I have written this article as a journal note of how I did this."
socialImage: "https://dev-to-uploads.s3.amazonaws.com/i/1j189nwdo2g4lzp7tez2.png"
---



![Alt Text](https://dev-to-uploads.s3.amazonaws.com/i/1j189nwdo2g4lzp7tez2.png)

The Twitter dynamic name generator is a pet project in which the twitter profile name updates for every minute with the followers count. I have written this article as a journal note of how I did this.

It was done as one of the challenges of #100DaysOfCode.  Thanks to [Suren](https://twitter.com/radnerus93) and [Vadim Bauer](https://twitter.com/BauerVadim) for their idea inspiration. Special thanks to [Karthikeyan](https://twitter.com/_karthikyn) for his guidance.

##### Tech Stack Includes, 
  * [Twitter lite](https://www.npmjs.com/package/twitter-lite) - to communicate with twitter API
  * [node.js](https://nodejs.org/) - script to update the twitter profile name
  * [AWS Lambda with serverless](https://aws.amazon.com/lambda/) - to run Cron part

# How I did this? What all the steps? 
Initially started with the guidance of [this article](https://dev.to/radnerus/twitter-api-is-followers-count-mda) written by [Suren](https://twitter.com/radnerus93). I majorly broke down this task into 3 parts.

1. Getting Twitter API key from Twitter Dev account.
2. Node js script to update the profile name.
3. Cron part to update the profile name for every 1 minute.

## Step 1 - Getting twitter API keys

Went to the [twitter developers page](https://developer.twitter.com/) as mentioned in the article and signed in. By providing the required pieces of information, twitter asked me to verify with my account email. Once verified with the email, my developers account was created. (Hurray!🎉) In the [Create an app](https://developer.twitter.com/en/apps/create) after entering the information like app name, app description and so on, it asked me to clearly explain the reason of how I'm going to use the app. After reviewing the terms, my app was created. Noted down the Consumer API key, Consumer API Secret key and Access token & access token secret keys!

At the end this step I got my **Consumer API key**, **Consumer API Secret key**, **Access token**, **Access secret key**.

Next interesting part! let's dive into coding!

## Step 2 - Script to update the profile name. 

Okay, now it coding time. Fire mode on🔥
I chose [node.js](https://nodejs.org/) as I'm familiar with that. From the [Suren article](https://twitter.com/radnerus93) I came to know about the [twitter-lite](https://www.npmjs.com/package/twitter-lite). 

Started with the simple, 
```
$ npm init
$ npm install twitter-lite
```
In the index.js file, imported the twitter-lite and update the required keys as we got from the previous step, 
```
const Twitter = require("twitter-lite");
const client = new Twitter({
  subdomain: "api", // api is the default
  version: "1.1", // version 1.1 is the default
  consumer_key: process.env.twitter_consumer_key,
  consumer_secret: process.env.twitter_consumer_secret,
  access_token_key: process.env.twitter_access_token_key, 
  access_token_secret: process.env.twitter_access_token_secret, 
});
```
Now comes the actually coding part.
So what is the logic to do this? 
1. We need to get the follower count using twitter API.
2. We need to append the followers count with the name, but with emoji🤔 (Hmm)
3. We need to update the new name to profile name using twitter API. 

Cool, let's do it! 
To get the followers count, used the twitter lite api. 
```
client
    .get("account/verify_credentials")
    .then((results) => {
      const followerCount = results.followers_count;
    });
    .catch(console.error);
};
```
Now, some little tricks! I got all the logic but struck with how to update the emoji dynamically. So asked [Suren](https://twitter.com/code_rams/status/1278585965963956225?s=20) in the twitter. He just replied with, Have JSON with matching emoji. Gotcha, now continue with the journey! 
Next simple logics like, get the followers count, convert to string, change to string array, then finally reduce the followers count with mapped emoji. 

```
exports.handler = () => {
  client
    .get("account/verify_credentials")
    .then((results) => {
      const followerCount = results.followers_count;
      const string = followerCount.toString();
      const stringSplit = string.split("");
      const followers = stringSplit.reduce((acc, val) => {
        return acc + numberMatch[val];
      }, "");
      const profile_name = `${name} | ${emoji} |" + ${followers}`;
      console.log("profile_name: ", profile_name);
    })
    .catch(console.error);
};

const numberMatch = {
  "0": "0️⃣",
  "1": "1️⃣",
  "2": "2️⃣",
  "3": "3️⃣",
  "4": "4️⃣",
  "5": "5️⃣",
  "6": "6️⃣",
  "7": "7️⃣",
  "8": "8️⃣",
  "9": "9️⃣",
};
```
Checked with by running, 
```
node index.js
```
Coool!, now got the console with the new name, appended with the emoji. Now next is, need to update the profile name. Used the same twitter-lite API, to update the profile. 
```
  const response = client.post("account/update_profile", {
        name: user_name,
      });
```
Ran again to check whether the name gets updated in the twitter profile ( Tik tik tik moments) 

Hurray 🎉  It works!

Now comes the final part!

### Step 3 - Cron to update the profile name for every 1 minute. 

Okay! Now all works fine, but how to make this to run for every minute? Here comes my technical guru [Karthikeyan](https://twitter.com/_karthikyn) into the play. Since he is a serverless expert, he suggested me to run the Cron in AWS Lambda function since I'm already familiar with lambda. Okay! Cool, let's do it. I'm skipping the AWS setup since it takes too long, and diving directly into the Cron part. 

```
service: twitter-scheduler

custom:
    twitter_consumer_key: ${ssm:/twitter_consumer_key~true}
    twitter_consumer_secret: ${ssm:/twitter_consumer_secret~true}
    twitter_access_token_key: ${ssm:/twitter_access_token_key~true}
    twitter_access_token_secret: ${ssm:/twitter_access_token_secret~true}

provider:
  name: aws
  runtime: nodejs12.x
  stage: prod
  region: ap-south-1
  environment:
      STAGE: prod
  
functions:
  subscription:
    handler: index.handler
    environment: 
      twitter_consumer_key: ${self:custom.twitter_consumer_key}
      twitter_consumer_secret: ${self:custom.twitter_consumer_secret}
      twitter_access_token_key: ${self:custom.twitter_access_token_key}
      twitter_access_token_secret: ${self:custom.twitter_access_token_secret}
    events:
      - schedule: rate(1 minute)
```

This cron runs for every 1 minute, and the new profile name is updated dynamically. New profile name is consoled in cloud watch. 

I have used service [AWS System Manager(SSM)](https://www.amazonaws.cn/en/systems-manager/) to avoid the exposure of explicit keys. 

Finally, my work is done. Here is the link to the [source code](https://github.com/RamyaChinnadurai/100DaysOfCode/tree/master/Day3%20-%20Twitter%20name).

For any doubts, suggestions and feedback contact me in my twitter profile [@code_rams](https://twitter.com/code_rams). Hope you enjoyed and find this useful. Thanks for reading.

*Originally published by [Rams Codes](https://dev.to/code_rams) on [Dev](https://dev.to/code_rams/twitter-dynamic-name-generator-3ka2).*
