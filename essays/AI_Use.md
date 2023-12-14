---
layout: essay
type: essay
title: "The Double Edge Sword of AI"
# All dates must be YYYY-MM-DD format!
date: 2023-11-21
published: false
labels:
  - Software Engineering
  - Learning
  - AI

---

## Problem Solving with AI
As of lately AI has been a game changer, things like ChatGPT have really changed the way things are done, especially in the software industry. Before ChatGPT a lot of problems had to be solved using google. Don’t get me wrong, google is definitely still viable, however, it’s much easier to ask ChatGPT for an answer especially if google comes up inconclusive. ChatGPT can also be very useful in understanding things you don't understand. For example take this code block from the Meteor Template 
```javascript
Meteor.publish(Notes.userPublicationName, function () {
  if (this.userId) {
    const username = Meteor.users.findOne(this.userId).username;
    return Notes.collection.find({ owner: username });
  }
  return this.ready();
});
```
When inputted in ChatGPT with the message “Explain this code” here’s what ChatGPT outputs: “This code sets up a publication in Meteor that sends data from the Notes collection to the client based on the currently logged-in user. It filters the Notes collection based on the owner field, which is expected to contain the username of the user who created each note. If there's no logged-in user, the subscription is marked as ready without sending any data.” This makes it truly special when it comes to things you don't understand as you can just input it in ChatGPT and get an answer

## 1. Experience WODs 
With the experience WODs, ChatGPT was able to play a good role in helping me understand things. It has been super beneficial when in the beginning stages and I had a hard time with the syntax, especially when it came to working with HTML, CSS, and JavaScript.
## 2. In-class Practice WODs
While In-class practice WODs were fairly difficult, ChatGPT made it easier by helping me explain what needed to be done. ChatGPT was able to go through the explanations and help me understand what needed to be done in order to finish the practice WOD. 
## 3. In-class WODs
During the in-class WODs, time management was crucial. As it was graded on an all or nothing basis, it was important to do In-class practice WODs and make sure you understood the material. But if you’re like me you tend to forget some things, and ChatGPT was able to help me in these instances where I forgot how something is done. Instead of scouring the internet for an answer and wasting the little time we had, I was able to utilize ChatGPT in the matter of seconds to find an answer to whatever question I had. 
## 4. Essays
On the topic of essays, ChatGPT played a role in writing the essays as it was able to correct simple grammatical errors and even suggest different ways to say something. On top of that, when it comes to naming essays, sometimes I draw a blank and I am not able to figure out a creative name for the essay. I was able to ask ChatGPT for some inspiration on what to name the essay. This helped me get ideas for the essay name as it wasn’t advised to name the essay something basic like the assignment title. 
## 5. Final project
Although the final project is a work in progress, ChatGPT is still playing a vital role in creating the project. Because we moved through material at a rather quick pace, it was easy to forget some things or even miss some things. ChatGPT is able to pick up the missing knowledge that I may have forgotten or help me reinforce my knowledge. As I work on the final project I like to code things out and if I have a question I can quickly ask ChatGPT. It can suggest better ways to code something or optimize the code I am working on. 
## 6. Learning a concept / tutorial
When learning new concepts, ChatGPT is really helpful. For instance, I was struggling to understand Cloudinary and how it works and ChatGPT was able to help me understand how it works. I am also able to ask questions about what it told me to help me reinforce the knowledge it gave. 
## 7. Answering a question in class or in Discord
Whenever I have a question about the material in this class, I always try to utilize ChatGPT first. Most of the time it is able to give me a solid understanding of what it is I don’t know. This lets me avoid having to ask a question and waiting for a response and also avoids wasting someone else’s time to help me.
## 8. Asking or answering a smart-question
As stated in number 7, the same thing follows. If I have a smart-question I am able to avoid asking the question and can utilize ChatGPT.
## 9. Coding example
When given the prompt:
“Give me a small code example of React UseState”
ChatGPT outputs this: 
“Sure, here's a simple code example of how you might use the useState hook in React:”
```markdown
import React, { useState } from 'react';

const Counter = () => {
  // Using useState to declare a state variable 'count' and a function 'setCount' to update it
  const [count, setCount] = useState(0);

  const increment = () => {
    // Updating the 'count' state using the 'setCount' function
    setCount(count + 1);
  };

  const decrement = () => {
    // Updating the 'count' state using the 'setCount' function
    setCount(count - 1);
  };

  return (
    <div>
      <h2>Counter</h2>
      <p>Count: {count}</p>
      <button onClick={increment}>Increment</button>
      <button onClick={decrement}>Decrement</button>
    </div>
  );
};

export default Counter;
``` 
“In this example:

useState is imported from React.
Inside the Counter component, useState is used to declare a state variable count initialized with an initial value of 0.
setCount is a function used to update the count state.
Two functions, increment and decrement, are defined to update the count state using setCount when the buttons are clicked.
The value of count is displayed in the JSX using curly braces {} to render dynamic content.
Clicking the "Increment" button increases the count, and clicking the "Decrement" button decreases it.
This is a basic example demonstrating how useState works to manage state within a React functional component.
“
It gave us a simple example on how to use React useState and explained what it does.

## 10. Explaining code
From the example in number 9, you can clearly see ChatGPT explaining the code it created. This is super helpful when you want to learn something new. 
## 11. Writing code
From the example in number 9, you can see ChatGPT creating code. 
## 12. Documenting code
Just like the others, in example 9, ChatGPT is able to create comments and document code. If you need ChatGPT to document code using Java standards or any known standards it can do so with ease. You can even train ChatGPT to document code a certain way you see fit. 
## 13. Quality assurance
While writing code if you are not well versed with the little things, it can be easy to mess something up and write bad code. This can be partly solved using ChatGPT. ChatGPT is able to turn bad code into quality code, and it can also help you learn how to write quality code. 
## 14. Other uses in ICS 314 not listed
Some other uses for AI or ChatGPT is its ability to answer any type of question in almost any domain. If you have any particular question on data structures or algorithms, ChatGPT can answer it. If you need help planning an itinerary for a trip, ChatGPT can create some good suggestions. The possibilities are endless when it comes to ChatGPT, and AI in general and it can be used by anyone to solve many problems.

