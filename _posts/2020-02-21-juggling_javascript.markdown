---
layout: post
title:      "Juggling JavaScript"
date:       2020-02-21 22:09:39 -0500
permalink:  juggling_javascript
---


Draft Draft Draft Draft Draft Draft Draft Draft

For my JavaScript SPA Project, I have an app called **飲む(nomu)** . It is an app for cocktail lovers where the user can input their favorite cocktails, even their experimental cocktail mixes. As challenging as this project can be, I have learned so much about JavaScript and added some new Rails knowledge. I realized that there is still a lot more to learn. 

> Like what Socrates said, “The more I know, the more I realize I know nothing.” 

Here are some of the lessons that I have learned based on the errors that I have encountered while doing this project:

### 1. Foreign Key Violation on postgresql

![](https://lh3.googleusercontent.com/8jWOlyPVs_nEu72jP7w2vv8mRX-0FTZYKYC0KkOX_xgjIoMJ9tgrlTwGs8w7iKcHIH5Sdk7NUj5xTutQCgm9tplngx_z-4sGyLVr0Vwz_vy-Z3J7F8QrJMX0qgzohLm_AjNNAu1HFQ=w2400)

I spent I don’t know many hours figuring out why my `destroy` action in my controller is not working and almost gave up on this functionality. During that time, my friend and I figured out that postgres is not allowing me to delete a cocktail because ActiveRecord tried deleting an instance of a cocktail while my liquor table is still referencing it. One option that I found is adding referential integrity options set to cascade. In this it is ON DELETE. ON DELETE CASCADE will delete that instance of a cocktail and the other rows on your table associated with it. There are other options like ON DELETE SET NULL and ON DELETE RESTRICT that I could probably use as well but I will have to dig deeper into to know how they work and what option to use depending on the functionality of my application.

### 2. ** `.bind()` `.this`**

> MDN web docs definition of `.bind()`:
> 
> The bind() method creates a new function that, when called, has its this keyword set to the provided value, with a given sequence of arguments preceding any provided when the new function is called.

![](https://lh3.googleusercontent.com/dasXIy9N3xLB7WqcPPo52uXYPrXe5QGx_ta9O5Yqk7X1AnAM8JjBCcvRYxuxJ3bBkUlJv-IXZpCG7LAUvkY43uY1aUcrv-8sI2Yzw6OVkdUEa42Xg_cxjHdrCDsFFXHct8QNcCHXhg=w2400)

This is the first time I have actually seen how useful `.bind()` is. 
So in my code above, I use `.bind()` to invoke a function that has a parameter of `this` meaning I want to use the same object when that function is called. In this case when I click submit in my form the values that I entered in my form is the same exact object that I want to create. What’s `this`? This is how I think of it: this === self === Object. With `this` object do(bind) this action.`.bind()` acts a bridge between the object and a function is another way of thinking about it. My reference might be a little off but it has helped me understand it more. Still confused? This [video](https://youtu.be/g2WcckBB_q0 )  has helped understand it better.

### 3. ** `debugger`** is your best friend in JavaScript

It’s most likely a personal preference but you should love it more than console.log()! I would not have done this project without these two though! However, `debugger` helps me see what’s happening in my code at that moment in time. I would be blindly troubleshooting and guessing what my code is returning if I had not learned this tool and my project would probably take twice as long without learning to know how to debug. `Debugger` has helped me fix a lot of errors and although it took me a while to fix some of them I would not have done so if there is no tool like it. This video tutorial [video link here](https://developers.google.com/web/tools/chrome-devtools/javascript)  is actually a good start to learn how to use debugger.  


