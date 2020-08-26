---
title: How the delete operator can be your super saver!
date: "2020-08-06T22:40:32.169Z"
template: "post"
draft: false
slug: "how-to-delete-operator-can-be-your-super-saver"
category: "Javascript"
tags:
  - "Javascript"
  - "Delete Operator"
description: "In this article lets discuss how the delete operator in javascript can be your rescuer. I'm jotting down my learning and working experience, so that others may found useful."
socialImage: "https://dev-to-uploads.s3.amazonaws.com/i/xz80i2w90nf9xk57pvbl.jpeg"
---

# How the delete operator can be your super saver

In this article lets discuss how the delete operator in javascript can be your rescuer. I'm jotting down my learning and working experience, so that others may found useful.

Recently I came up with a scenario where there is an array of objects with the different fields of value, and I want to remove the unwanted fields in the object and return it as an object. 
  
  Example: Array of objects with different fields. 
  ```
      rewards = [
        {
            _id: "5d6fcdf63eb318a9d6981f35",
            type: "welcome_offer",
            discount: 15,
            status: true, 
            validity: "05-09-2020"
        },
        {
           _id:"5d779b833eb318a9d6f60528",
           type: "extend_subscription",
           duration: 3,
           status: true,
           validity: "05-09-2020"
        },
        {
            _id: "5d7b700b3eb318a9d6227637",
            type: "unlock_course",
            eligiblePlans: [ "js-combo", "react-combo"],
            status: true,
            validity: "05-09-2020"
        }
    ]
  ```
  
 How the actual outcome should be? 

```
    rewards: {
        "WELCOME_OFFER": {
            discount: 15,
            validity: "05-09-2020"
        },
        "EXTEND_SUBSCRIPTION": {
            duration: 3,
            validity: "05-09-2020"
        },
        "UNLOCK_COURSE": {
            eligiblePlans: [ "js-combo", "react-combo"],
            validity: "05-09-2020"
        }
    }
```
So how can bring the above array to this format?  

1. Need to convert the array to object. So we can use the reduce function in javascript to convert to a single object. Okay!
2. To capitalise the type, we can just use toUpperCase() function. Okay, that also fine. 

How can we remove the unwanted fields in the object? 🤔
There comes the [delete operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/delete) to rescue me. 
    
    The JavaScript delete operator removes a property from an object; if no more references to the same property are held, it is eventually released automatically.

#### Syntax
    delete object.property
    delete object['property'] 

Okay, its time to put all the knowledge into coding. 

```
    const eligible_rewards = rewards.reduce( ( acc, val) => {
             const type    = val.type.toUpperCase();
            const details  = {
                        [type]: {
                        ...val
                }
            }
            delete details[type].type;
            delete details[type].status;
            delete details[type]._id;
            return {...acc, ...details}
        },{})
```

Checkout this snippet in [JSfiddle](https://jsfiddle.net/rams_codes/h1yL7to9/1/)

I'm sure there are other ways to solve the problem. Share your solution in the comment section below. I hope you find this useful. If you find useful keep supporting me. For doubts, suggestions and feedback kindly contact me at [@code_rams](https://twitter.com/code_rams)


*Originally published by [Rams Codes](https://dev.to/code_rams) on [Dev](https://dev.to/code_rams/how-the-delete-operator-can-be-your-super-saver-5c34).*