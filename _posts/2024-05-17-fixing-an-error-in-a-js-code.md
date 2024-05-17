---
layout: post
date: 2024-05-17 15:45:00 +1000
title: 12. Fixing an error in a JavaScript code
tags: javascript challenges
---
What is wrong with my below javascript code?

```javascript
var johnDoe = {
    firstName: "John",
    lastName: "Doe",

    greet: function() {
        alert("My name is ") +
        this.firstName + " " +
        this.lastName;
    }
};

```

All this code needs to do is display, "My name is John Doe".

When I executed this in localhost, nothing appeared on the page. Just a blank page!  
I knew it was something simple to fix, but couldn't figure out what the mistake could be.   
Finally, I asked my coding tutor who immediately said I wasn't calling the method I created.

The expression I need to use is `johnDoe.greet()` and its called a **method call**. 

In JavaScript, when a function is a property of an object, it is referred to as a method. 
In this case, `greet` is a method of the `johnDoe` object. Invoking `johnDoe.greet()` executes the `greet` method defined within the `johnDoe` object.

So, I corrected my code:

```javascript
var johnDoe = {
    firstName: "John",
    lastName: "Doe",

    greet: function() {
        alert("My name is ") +
        this.firstName + " " +
        this.lastName;
    }
};

johnDoe.greet()
```  

When I checked again on localhost, I was happy to see an output but there was an issue!  

![Localhost screenshot](/images/name-localhost-issue.png)

The name "Joe Doe" wasn't appearing!  

After a little more troubleshooting, I discovered I had the curved braces (parentheses) in the wrong place! The code should be as follows:  


var johnDoe = {
    firstName: "John",
    lastName: "Doe",

    greet: function() {
        alert("My name is " + this.firstName + " " + this.lastName);
    }
};

johnDoe.greet();

And that produced the below result:  

![Localhost screenshot](/images/correct-display-name.png)  

Success!

As my tutor says, "Having syntax problems isn't a problem, it's going to happen throughout your career - 
the important thing is that you know how to fix those once you realise where the problem is 😉"

---
I highly recommend this book, [Beginning JavaScript by Jeremy McPeak and Paul Wilton](https://amzn.to/3QQnJDb).
