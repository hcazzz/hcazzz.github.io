---
layout: essay
type: essay
title: "Design Patterns? Never Heard of Them"
# All dates must be YYYY-MM-DD format!
date: 2023-11-29
published: true
labels:
  - Software Engineering
  - Design Patterns
---

In the realm of Software Engineering, there are many intricacies going on behind the scenes. Many of which, to the untrained eye may not be noticeable. One of these things are design patterns. While one may not know of specific design patterns, it's possible you may be using them without realizing.

Imagine this, you just got hired at a large company as a developer, and you take your first look at the codebase. It’s probable you have never seen something so complex or large. It’s also probable that this behemoth of a codebase can be broken down into much smaller parts. If that company utilizes design patterns, you’ll notice that the scary monster, the codebase is much simper than you thought. Now theres many different types of patterns used in software engineering,

Software Engineering can be quite daunting at first glance, and on top of this, one might stumble upon design patterns which can definitely add onto the complexity. There's so much going on behind the scenes that it's easy to get distracted from little things. To make matters worse, googling different programming lingo might add onto the confusion. Especially when you get more buzzwords such as:
<li>Singletons</li>
<li>Facades</li>
<li>Factories</li>
<li>Observers</li>
<li>Dependency Injection</li>

<br>
When you first come across this you may not know what any of this means, I know I didn’t. It took me a while to finally figure out what a singleton is. It wasn’t until recently I figured out that I was using them in my code without knowing I was. Anyways, it’s important to understand what these random words are actually trying to accomplish and how they relate to software engineering.

In order to talk about design patterns, we first must know their purpose and what they're trying to solve. You can think of design patterns like LEGO bricks, they come in many different forms and colors, but you can combine them in different ways to build something inherently complex. All while reusing some of the basic building blocks. If you have never used LEGOs before, you can think of design patterns like a building blueprint in the real world.



When utilized correctly, design patterns can take your code base from spaghetti that barely works, to something that is maintainable and easy to scale. Code reusability is a big one, would you rather write redundant code that takes hours, or write it once in a way that can be reused with little changes? Let's talk about a simple example, say you needed to find the area of a rectangle in your application. Each time you needed to find the area of a rectangle you coded in the same calculation. For the sake of the example, let's say you coded this calculation a few times, after a certain point you may stop to wonder, is there a better way to do this? The answer is yes, you can simply write your calculation logic and wrap it in a function. Now, whenever you need to figure out the area of a rectangle, you can just call your function. This will lead to much simpler and readable code.


These are basic design principles that one may use while programming. So how do I use them to better my code you may ask, well the answer is it depends. One driving factor is the language at use.

## Singleton? What's That?

In JavaScript, I find myself mostly using the Singleton design pattern, while at first I didn’t know it, as I learned more about design patterns I realized I am. Put it simply, the Singleton pattern is when a class in your program has a single instance but also provides global access to that instance everywhere. An example of this can be found in the <a href="https://github.com/ics-software-engineering/meteor-application-template-react/blob/main/app/imports/api/stuff/Stuff.js">Meteor React Template StuffsCollection</a> which is a collection of stuffs.

```javascript
import { Mongo } from 'meteor/mongo';
import SimpleSchema from 'simpl-schema';

/**
 * The StuffsCollection. It encapsulates state and variable values for stuff.
 */
class StuffsCollection {
  constructor() {
    // The name of this collection.
    this.name = 'StuffsCollection';
    // Define the Mongo collection.
    this.collection = new Mongo.Collection(this.name);
    // Define the structure of each document in the collection.
    this.schema = new SimpleSchema({
      name: String,
      quantity: Number,
      owner: String,
      condition: {
        type: String,
        allowedValues: ['excellent', 'good', 'fair', 'poor'],
        defaultValue: 'good',
      },
    });
    // Attach the schema to the collection, so all attempts to insert a document are checked against schema.
    this.collection.attachSchema(this.schema);
    // Define names for publications and subscriptions
    this.userPublicationName = `${this.name}.publication.user`;
    this.adminPublicationName = `${this.name}.publication.admin`;
  }
}

/**
 * The singleton instance of the StuffsCollection.
 * @type {StuffsCollection}
 */
export const Stuffs = new StuffsCollection();
```

While that is a whole lot of code, we are mostly interested in the very last line of the code, export const Stuffs = new StuffsCollection();

This line creates a ‘Stuffs’ variable which will serve as a singleton instance for the ‘StuffsCollection’ class. The reason this is exported is to allow the accessibility of it in other parts of the application. This allows you to refer to the same instance of ‘StuffsCollection’ anywhere you import it and use it. If we did not use the Singleton pattern here, you would be able to create multiple instances of the ‘StuffsCollection’ and data wouldn’t match up across each instance. This ensures that all data being worked with in this collection happens all on the same instance. 

## Not a Pattern, but Useful

React Hooks are another thing that I have used often in my applications. Hooks allow you to encapsulate and reuse code. While on its own it's not considered a design pattern, it's definitely important to note. However, when paired with other things hooks can become a design pattern. For example, let's take a look at the custom react hook ‘useTracker’. In this code snippet, again from <a href="https://github.com/ics-software-engineering/meteor-application-template-react/blob/main/app/imports/ui/pages/EditStuff.jsx">Meteor React Template, EditStuff</a>

<style>
code .operator {
  color: #3498db; /* Change this color code as desired */
}
</style>

```javascript
const EditStuff = () => {
  // Get the documentID from the URL field. See imports/ui/layouts/App.jsx for the route containing :_id.
  const { _id } = useParams();
  // console.log('EditStuff', _id);
  // useTracker connects Meteor data to React components. https://guide.meteor.com/react.html#using-withTracker
  const { doc, ready } = useTracker(() => {
    // Get access to Stuff documents.
    const subscription = Meteor.subscribe(Stuffs.userPublicationName);
    // Determine if the subscription is ready
    const rdy = subscription.ready();
    // Get the document
    const document = Stuffs.collection.findOne(_id);
    return {
      doc: document,
      ready: rdy,
    };
  }, [_id]);
```

This code snippet is an example similar to Observer design pattern where a subject maintains a list of its observers and notifies them of any state changes by calling one of their methods. In this context, ‘useTracker’ establishes a data connection between the Meteor data source ‘Stuffs’ and this fetches data which allows you to update/edit the data. When the state of the data is changed, it gets updated in the database and re-renders the page.

## How About a Different Language?
When it comes to programming in C# you may come across the Repository pattern which is when you create a layer between an application’s business logic and data storage. You can think of it like a company's HR (Human Resources) department. HR is responsible for managing employee records, and information. They handle a lot of the paperwork involved, now if someone from another department got fired or quit, their boss would interact with HR to process it. In this example, HR can be seen as the repository layer acting as the layer between the business logic, and the data storage. 

Enough analogies, in order to fully understand what we are talking about, its best to see an example, 

```cs
namespace Flashcards.Data
{
    internal class FlashcardRepository
    {
        private readonly FlashcardContext _context;

        public FlashcardRepository(FlashcardContext context)
        {
            _context = context ?? throw new ArgumentNullException(nameof(context));
        }

        internal void AddFlashcard(Flashcard newFlashcard)
        {
            _context.Flashcards.Add(newFlashcard);
            _context.SaveChanges();
        }
    }
}
```

Here is a small example of a FlashcardRepository, in this example, context represents the database sessions that the class will use to interact with the database. In this sample, the repository is capable of adding a new Flashcard into the context or database, and then it saves the changes. The next question is how is this used? Well, we have a few ways to do it, to keep it simple, there would be a user interface that collects the new flashcards data, from there we can pass it to the controller, here's a simple example: 

```cs
namespace Flashcards.Controllers
{
    public class FlashcardController
    {
        private readonly IFlashcardRepository _flashcardRepository;
        private readonly IUserInterface _userInterface;

        public FlashcardController(IFlashcardRepository flashcardRepository, IUserInterface userInterface)
        {
            _flashcardRepository = flashcardRepository;
            _userInterface = userInterface;
        }

        public void AddFlashcard()
        {
            var newFlashcard = _userInterface.GetFlashcardInfo();
            _flashcardRepository.AddFlashcard(newFlashcard);
        }
    }
}
```

So with this Repository design pattern, the repository acts as HR, in the sense that it is the layer between application logic and the database. Like HR, the application supports adding flashcards (adding a new employee). However, it’s important to note that this repository example only involves the addition of flashcards into the database, but in an actual application there would be more logic like removal, update and deletion. All of which HR would be able to do. 

## Why is This Important?

Well, others may have their own opinion on the repository pattern, and find it consulting. But the pattern promotes readability and maintainability, scalability and testability. These are all very important things when writing good code and if used correctly it can optimize your code base. 

## More on Design Patterns

Looking at the above examples, you may notice this code: 

```cs
    private readonly FlashcardContext _context;

        public FlashcardRepository(FlashcardContext context)
        {
            _context = context ?? throw new ArgumentNullException(nameof(context));
        }
    }
```
There is a lot that goes into this and it can take quite a while to understand, I may even not understand it in full but this is an example of another pattern that is used a lot in C#, which is dependency injection. Instead of instantiating the context directly in the class, we can utilize dependency injection through the constructor to get an instance of the database. This allows more flexibility when it comes to things such as testing and promotes modularity. If one wanted to test this code with a sample database context, you can easily swap the contexts and use a mock database instead. 
Dependency injection can take a good amount of time to learn in full. While you can utilize online information, I recommend a good book on Dependency Injection by Mark Seemann, <a href="https://www.manning.com/books/dependency-injection-principles-practices-patterns"> Dependency Injection Principles, Practices, and Patterns</a>. This book goes into great detail on dependency injection and how to use it in C#.



## Is That All?

While design patterns are language agnostic it’s important to know that some patterns may be more common in one language compared to another. For example, it’s more likely you’ll see dependency injection in OOP languages such as C# or Java. 

With that being said, design patterns can be very useful, regardless of the chosen language. But when applied incorrectly, they can definitely do more harm than good. It's important to make sure you actually need to use a certain design pattern and you’re not blindly applying a pattern to every problem you encounter. This can overly complicate and bloat your codebase, leading to spaghetti code. Before utilizing a certain design pattern you should always think about the tradeoffs of using it and if it's actually necessary. You don’t want to run the risk of complicating your code if you don’t need to.





