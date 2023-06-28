# Lighthouse Labs | Problem Solving

1. The Learning Cycle
 - [ ] Create a dictionary
 - [ ] Read your Code: "What is this? What happens next?"
 - [ ] Create a Cheatsheet for Each Record
 - [ ] Solve Problems
2. I'm Lost

## The Learning Cycle

There are a variety of strategies and steps you can use in your approach to learning new topics and concepts. Here is the cycle that we recommend for you to make the most of your time with us at Lighthouse Labs:

1. Create a Dictionary of Terms
2. Read your Code: "What is this? What happens next?"
3. Create a Cheetsheet for Each Record in your Dictionary
4. Solve Problems

### 1. Create a Dictionary of Terms

During lectures, it is important to spend most of your time listening and watching opposed to being distracted by note-taking. This may feel counter-intuitive, but it is in your best interest!

Instead of taking detailed notes of every step, it is best to write down new terms. When you have time, revisit this list of terms, and try to write a definition that makes sense to you. If you have trouble writing a definition, consider:

1. Reviewing the lecture repository and seeing if you can describe how the term fits in.
2. Searching the term on a trusted resource like the Mozilla Developer Network (MDN) website to see if it can shed some light on the subject.
3. Asking a mentor to help understand the term with some guidance.
4. Showing up to instructor office hours to ask your instructor about the term.

Remember the goal of this dictionary is to be written in your own words so that it is more likely to make sense to **you** upon revisiting.

Writing hand-written notes can help you build stronger memory on new terms, but can be harder to organize. If you go with a hand-written approach, consider using sticky notes or bookmarks to break-up these notes into categories.

Digital notes are not as effective in helping you build memory, but make for an incredible experience in terms of searchability. You can quickly skip to specific categories or definitions at-will. Depending on your note-taking tool of choice, you may be able to embed images, diagrams, or links to related resources. Consider programs like [Obsidian](https://obsidian.md/) if you'd like a dedicated note-taking application.

### 2. Read your Code: "What is this? What happens next?"

Whether you're reviewing a lecture, reading an exercise, got help from a mentor, or have just written a line of code, take the time to sit with your rubber duck and ask yourself for each keyword, operator, or method:

1. What is this and what does it do? (Review your dictionary if you feel lost.)
2. What will happen next?

Don't read top-to-bottom as if it is a story, or a novel... take the time to read each "word" as if you were the computer. Take into account the order in which you think the code will actually execute, not just the order it is written. This is extremely helpful in learning to make appropriate use of functions, methods, callbacks, asynchronous code, and recursion.

This exercise, especially when learning anything new, will ensure you know what is going on in code you're working with. It will also quickly help you identify, with great specificity, which parts of the code you feel uncertain about; this makes it much easier to research or ask a mentor or instructor for clarifications.

### 3. Create a Cheatsheet for Each Record in your Dictionary

Look for common patterns in your code. See if they can be attached as examples in your definitions! Depending on which unit you're in here at Lighthouse, consider the following examples:

#### Functions

A set of JavaScript instructions that can be executed when called upon (envoked) by name followed by parentheses `()`.

**Parameters:** defines values that can be passed into a function to help customize its functionality.

**Arguments:** values passed into a function when it is called (envoked.)

**Return:** value that is given back by the function, often for assignment to a variable. If the `return` keyword is not used in a function, `undefined` will be provided by default.

Examples:

```JavaScript
/**
 * Writing Functions
 */

// Function declaration
function funcName(one, or, more, params) {
  // code / logic here...
  // we can return something!
}

// Envoking / running the function
funcName('test'); // Can pass in arguments

// Function expression (alternative syntax)
const funcExpression = function(one, or, more, params) {
  // code / logic here...
  // this function is not hoisted
  // we can return something!
};

funcExpression('test2');

// Arrow function expression
const arrowFuncExpression = (one, or, more, params) => {
  // code / logic here...
  // this function is not hoisted
  // `this` keyword is not bound to function
  // we can return something!
};

arrowFunctionExpression('test3');
```
### Express Application

Express is an `npm` package used to write HTTP-based web applications, offering ways for us to write simple request and response handling.

Example:

```JavaScript
/**
 * Writing an Express application
 */

// Set up an express object
const app = require('express')();
const PORT = 8080;

// Listen for requests
app.listen(8080, () => console.log(`Express listening on http://localhost:${PORT}/`));

// Handle a GET request for: 'localhost:8080/'
app.get('/', (req, res) => {
  res.end('<!DOCTYPE html><html><head><title>Hello, World!</title></head><body><h1>Hello, World!</h1></body></html>');
});

// Handle a GET request for: 'localhost:8080/test-params/something'
app.get('/test-params/:myParam'), (req, res) => {
  console.log(req.params); // Value(s) from the URL
  res.end();
});

// Handle a POST request for: 'localhost:8080/submitted'
app.post('/submitted', (req, res) => {
  console.log(req.body); // Values from submitted form fields
  res.end();
});
```

### React Component

A React component is a JavaScript function representing a focused repeatable "module" of HTML, CSS, and JS for the browser. Values can be passed to a component via props, and each component is expected to return valid JSX output.

**Props:** the first parameter in a component function; represents any/all arguments passed into a component when envoked as an object of key-value pairs.

**JSX:** (JavaScript eXtensible markup language) is used to offer us a more HTML-like syntax for preparing component output. Props can be passed to components via a syntax akin to "HTML attributes."

Example:

```JavaScript
/**
 * Writing a React component
 */

// Components generally follow PascalCasing
const MyComponent = (props) => { // Props accepted via single parameter
  console.log(props); // All props available from single object

  // Return valid UI output
  return (
    <>{/* Empty tags are fragments */}
      <h2>Practice Component</h2>
      <p>Hello, World!</p>
    </>
  );
};

// Export for easy use in other files
export default MyComponent;
```

### 4. Solve Problems

While not all problems are made equal, there are consistent steps we can take to approach them efficiently. Solving problems effectively often mimics some of the steps you might take in test-driven development (TDD). Let's review some steps we can take:

1. Identify Inputs
2. Identify Outputs
3. Identify Processing

This is very similar to what we see take place when we *write* a function: input, processing, output.

#### Addition Example

Let's suppose we want to write a simple addition function. This can be handled in a variety of different ways depending on the requirements supplied or our goals. Let's look through our options step-by-step.

What will we need in order to perform addition? It may seem trivial, but this can be an important decision. Let's consider:

* How should we receive inputs?
  * As terminal arguments `process.argv`
  * As standard input `process.stdin`
  * As function arguments
  * From an API (external resource)
  * From a database (external resource)

For addition, any of these approaches may be something we consider on a case-by-case basis. For our case, unless otherwise specified, perhaps we can say we are writing a `function` that can take in two (2) arguments. Note that any changes to this requirment may change how we handle our inputs and how we ultimately code our solution! We might also want to note that we are expecting valud numbers. This is something we would want to check for if we were to write tests for this problem.

```JavaScript
/**
 * Addition function
 *
 * @param {number} first number to add (default zero)
 * @param {number} second number to add (default zero)
 */

// Takes in two numbers:
const addition = (num1 = 0, num2 = 0) => {
};
```

Alright, that's a nice start. We should also decide what our end goal is. Without this in mind, we'll have trouble knowing if our solution is functioning properly:

* What should our output look like?
  * What data-type should we use?
    * String
    * Number (Should there be a specific format?)
      * Decimals? How many?
      * Should zero be allowed?
      * Negatives?
    * Boolean
    * Undefined
    * Null
    * Object (Does the type or format matter?)
      * Array
      * Instance of a `class`?
      * Are certain properties expected to be in the object?
      * Should this be JSON-compatible? String or JS object?

For our example, `Number` is probably the most sensible data-type to use, but again that could very much vary depending on our requirements. Let's proceed with this assumption:

```JavaScript
/**
 * Addition function
 *
 * @param {number} first number to add (default zero)
 * @param {number} second number to add (default zero)
 * @return {number} sum of parameters
 */

const addition = (num1 = 0, num2 = 0) => {
  let result = 0;

  // processing takes place here.

  // Returns a number
  return Number(result);
};
```
In our function we return a Number value. Now if we try to experiment with our function, we can write examples of its use that have input and output. Of course, we are missing the processing, so our results are not correct just yet, but we're able to take strides toward that effect. At this point, you'll want to prepare examples like:

```JavaScript
console.log('addition(0, 0) =',   addition(0, 0));   // Should be 0
console.log('addition(-5, -5) =', addition(-5, -5)); // Should be -10
console.log('addition(2, 3) =',   addition(2, 3));   // Should be 5
console.log('addition(-3, 33) =', addition(-3, 33)); // Should be 30
```

What do we see right now in the terminal?

```Bash
$ addition(0, 0) = 0
$ addition(-5, -5) = 0
$ addition(2, 3) = 0
$ addition(-3, 33) = 0
```

We have input and output. Our output is just **wrong** right now. So, next step is to fix that. Our final step? Processing. The hard part! So, what needs to happen in order for us to receive two numbers and end up with our sum?

* What needs to take place to take our inputs and generate the expected output?
  * Are there any language functions or methods that would help us out?
  * Do we need to iterate over anything? (consider loops)
  * Do we need to make any decisions? (consider `if` or `switch`)

For our example, we'll just need to make use of the addition `+` operator to get the desired result. Consider using a commenting syntax like [JSDoc](https://en.wikipedia.org/wiki/JSDoc) to keep track of each of your steps. Let's give it a shot:

```JavaScript
/**
 * Addition function
 *
 * Takes in two `Number`s as arguments; adds them; returns the sum.
 * @param {number} first number to add (default zero)
 * @param {number} second number to add (default zero)
 * @return {number} sum of parameters
 */

const addition = (num1 = 0, num2 = 0) => {
  let result = 0;

  // Add two numbers together
  num1 = Number(num1);
  num2 = Number(num2);
  result = num1 + num2;

  return result;
};
```

Now that we've attempted a solution, we can run our experiments again and see how it looks:

```JavaScript
console.log('addition(0, 0) =',   addition(0, 0));   // Should be 0
console.log('addition(-5, -5) =', addition(-5, -5)); // Should be -10
console.log('addition(2, 3) =',   addition(2, 3));   // Should be 5
console.log('addition(-3, 33) =', addition(-3, 33)); // Should be 30
```

What do we see in the terminal this time?

```Bash
$ addition(0, 0) = 0
$ addition(-5, -5) = -10
$ addition(2, 3) = 5
$ addition(-3, 33) = 30
```

Much better! Now, these steps scale well for *any* problem you approach. Ensure you do planning in your processing phase... break the problem down into the smallest steps you can. **Do not** worry about doing things the *best* way the first time. Focus on getting your solution *working*. Once it is, commit, and then consider refactoring your code. Your end goal should be legibility of your code so that you and any team members can easily understand it hours, days, weeks, months, or even years down the road.

If it feels like there are a lot of steps in the **process** component of your problem solving, ask yourself if any of this can be further broken down, or might be worth breaking out into their own specialized / helper functions or methods with their own input(s), processing, and output(s).

## I'm Lost

![Not Sure? Ask!](https://github.com/WarrenUhrich/lighthouse-labs-problem-solving-breakout/blob/main/assets/06-how-to-learn-computer-programming.png?raw=true)

Let's say we've gone through our processes and problem-solving steps. If you have broken down the problem(s) and find you are stuck on a particular piece, how can we get out of that bind? We can create a process for this too! Let's have a look at the steps we might take:

1. Ask a Duck
  * Say your problem and any potential solutions out loud, you'll process them again this way.
  * You can talk through it with someone even if they aren't a programmer; again it helps you process the problem or potential solution again.
  * It might give you a new idea!
2. Ask yourself "have I done this sort of thing before?"
  * Do the definitions and examples in your dictionary or cheatsheet give you any ideas?
  * Check previous lectures or exercises, see if you can identify a pattern you can follow to solve your current problem.
  * Consider previous exercises that might have solved the same, or a similar, problem.
  * Programmers are "the ultimate recyclers", don't be afraid to follow your previous examples.
  * Don't expect to have every syntax or pattern memorized, definitely **do** make use of your previous code!
3. Research
  * See if you have any Bookmarks saved in your browser on the topic, these should be resources you understand and trust.
  * Search for information on a function, class, method, operator, or keyword you are trying to use.
    * Include the language in your search (`JavaScript`, `HTML`, `CSS`, `SQL`, `Ruby`.)
    * Include the package or technology name if you're making use of one for this problem (`Mocha`, `Chai`, `Express`, `bcrypt`, `PostgreSQL`, `Node.js`.)
    * Include the name of a trusted web site or resource for this topic (`MDN`, `W3C`, `CSS Tricks`, `PostgreSQL Tutorial`, `Ruby-Lang`.)
4. Ask a Peer
  * Others in your cohort likely have encountered a similar problem, brainstorm together to see what ideas you come up with.
5. Ask a Mentor
  * Take advantage of this service, not all schools have a mentor offering!
  * Don't be shy, mentors are happy to help with concerns both big and small.
  * Feel free to jump into the queue to ask questions about your dictionary.
    * Clarifications on definitions or examples.
    * It can help to have an exercise open related to the topic so there is an example to work with and walk through together.
6. Visit during Instructor Office Hours
  * These hours are here for a reason, ask instructors for clarifications on topics covered in-lecture or on exercises you're working on!