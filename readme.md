# Intro to Javascript

## Learning Objectives
* Describe the role Javascript plays alongside HTML and CSS.
* List and describe the primitive data types.
* Describe uses of mathematical operators in Javascript.
* Define type coercion.
* Define and use complex data types.
* Explain the difference between `prompt` and `console.log`
* Practice proper JS syntax and semantic variable naming.
* Differentiate between true & false && truthy & falsey
* Describe why control flow is utilized in computer programming
* Write an if, else if, and else statement in JS
* Write a for loop and while loop in JS and differentiate between them
* Utilize loops to iterate through complex data types

## HTML, CSS and Javascript (20 min, 0:20)

**What are the main components of front-end web development?**  
> HTML, CSS and Javascript.

**What roles do HTML and CSS play in a web site or application?**
> HTML: Structure  
> CSS: Styling  
> JS: What do the web sites we have build so far lack?  

### Think-Pair-Share: Identify JS Features in Cookie Clicker

**Think:** Spend three minutes playing around with Cookie Clicker and think about the following questions...
* What Cookie Clicker features are powered by Javascript?
* What categories of functionality does Javascript give a web app?
* Why would you say a particular feature is powered by Javascript as opposed to HTML or CSS?  

**Pair:** Spend another three minutes discussing and comparing your findings with a partner.  

**Share:** We'll discuss our findings as a class.  

#### Findings

**Interactivity**
* Click something, something happens.
* Javascript defines what happens on a page depending on how you interact with it.

**No Refreshes / User Experience**
* When I click a cookie, CC is able to increment and update the counter on the page without a hard refresh.
* Gives the page a much smoother user experience compared to a static page that doesn't have this sort of functionality.

**Storage / Communication with a Server**
* Javascript is telling the browser that (a) a user has done something, (b) it should save the result of that interaction and (c) display the results of that interaction to the user whenever he or she is at the site.
* In the case of Cookie Clicker, that information is saved in local storage using -- ironically -- cookies.
* We can also use Javascript to communicate with a server.

This is not an exhaustive list of Javascript properties, but we'll go over these and more in more detail later on in the course.  

So, to sum up the main three components of front-end web development up in one word each...
* HTML: Structure
* CSS: Styling
* Javascript: Behavior

## Javascript: The Client-Side Programming Language of the Web (5 minutes, 0:25)

**Brief history:** Created in 10 days by Brendan Eich, of Mozilla. *Not* related to Java in any way but its name.
* "Java" is to "Javascript" as "ham" is to "hamster"

**Q:** What's a programming language?  
* What can it do that a markup language like HTML can't?
* It let's us do things! It lets us act on information, manipulate it, display it, pretty much whatever we want.

Javascript enables us to do all that in a browser.  
* Using the tools you learned in the pre-work (e.g., data types, loops, functions).

### Why is it the dominant programming language of the web?

Barriers to entry for learning Javascript are very low.
* No additional software required to run it. Just a text editor and a browser.
* You can even run it directly in the browser via its Javascript console.
  * Ex. Hide images on the GA website.
* On top of that, it's supported by all web browsers.

Javascript has evolved since its creation.
* One of the biggest additions to JS was AJAX, which allows use to reload parts of a page without refreshing the entire thing (just like on Facebook). Big implications for User Experience.

A lot of frameworks and libraries -- like Backbone and jQuery -- have emerged that enable us to do so much more -- and do it quickly -- with Javascript.

# Setting up our environment (5 minutes, 0:30)

## First, create your HTML and JS

```bash
# In Terminal..
$ touch index.html script.js
```

```html
<!-- index.html -->

<!DOCTYPE html>
<html>
  <head>
    <title>Yo</title>
    <script src="script.js"></script>
  </head>
  <body>

  </body>
</html>
```

## Next, open the site in Chrome and open the Dev Tools

Open the Javascript console in the browser using the following shortcut: `Command + Option + I`

The "Console" is a REPL (`Read-Eval-Print Loop`)
* What's that? A programming environment that lets us run Javascript code one line at a time.
* What does it do?
  1. (R)eads our code.
  2. (E)valuates it.
  3. (P)rints it to the console.
  4. Then it (L)oops back to the beginning, ready to (R)ead the next line of code we feed it.
* Try running some simple lines of code (e.g., `2+2`) in the console!

> `⌘ + ⌥ + i` enters you in the the Chrome dev tools. Here you can do a bunch of stuff like inspect elements and looks at the html. More importantly for this class though, is it allows you to access the console which interacts with the JS you loaded to your page. In our case we'll see that interaction with the code below  

We can also run whatever code is located in the `script.js` that is referenced in `index.html`. Try putting the following code in `script.js` and reload the page...

```js
// script.js

console.log( "hello world" )
```
> `console.log()` is just a way to log or print something, in this case our REPL.  

# Exercises

Today's class is dedicated to solidifying your knowledge of Javascript fundamentals (i.e., things you covered in the course pre-work!). Because of that, the structure of the remainder of the class is going to be exercised-based. It will give you a chance to practice what you've already learned and dive in a bit deeper into the subject matter.

### [Data Type Exercises](https://github.com/ga-wdi-exercises/js-data-types) (30 minutes, 1:00)
An assorted grouping of Javascript exercises that test your knowledge of Javascript data types, conditionals and loops.

### Break (10 minutes, 1:10)

### Check-In (15 minutes, 1:25)

### [Temperature Converter](https://github.com/ga-wdi-exercises/temperature_converter) (30 minutes, 1:55)
This exercise will tie together everything you practiced in the previous exercise (and more). If you finish this with time to spare in the lesson, start working on the homework.

### Break (10 minutes, 2:05)

### Check-In (15 minutes, 2:20)

# Some Things To Keep In Mind

### Type Coercion

Javascript will try to make sense of any strange operations you throw at it.
* By "strange", I mean subtracting a number from a string, or multiplying `null` by 100.
* It does this through something called "type coercion" -- converting data types.

You might encounter this when dealing with numerical values but for whatever reason some of them are in string form.
* **Q: What are the return values of the following code examples?**

```js
// In some cases Javascript is helpful and converts strings to numbers in the correct way.
"3" - "2"
=> 1

// ...but sometimes it doesn't. In this example, the + operator acts as if it's concatenating two strings.
"3" + "2"
=> 32

// And this?
"five" * 5;
=> NaN
```

When in doubt, convert data types that should be numbers using `parseInt()`.

```js
// parseInt converts a string to a number value, if available.
parseInt( "3" );
=> 3

parseInt( "burrito" );
=> NaN
```

There are other examples of type coercion, but the point here isn't to remember them all. Just be aware that sometimes Javascript will fire weird results back at you with no explanation. Sometimes, type coercion might be the culprit.

### Escape sequences

Sometimes you will need to use special characters or formatting in strings that can't be entered the same way as you would in a word processor. In these cases, you use "escape sequences".
* Syntax: backslash + letter (e.g., `"\n"`).

```js
// "\n" = new line
"Hello\nGoodbye"
=>"Hello"
=>"Goodbye"

// "\t" = tab
"\tOnce upon a time..."
=> "     Once upon a time..."
```
> You can check out more escape sequence examples [here](http://www.javascriptkit.com/jsref/escapesequence.shtml).  

### Undefined & Null

Values that indicate the lack of a meaningful value.
* Anybody else find that weird? How is there more than one data type for nothing?
* **Q: What's the difference?**

`undefined`: automatically applied to a variable with no value.  

```js
// A primitive data type of type undefined with only one value: "undefined".
typeof undefined;
=> "undefined"

// Any property that has not been assigned a value is "undefined".
var nothing;
=> undefined

// A function with no defined return value has a return value of "undefined".

// You won't find yourself assigning "undefined" to a value. That's where "null" comes in.
var nothing = undefined;
```

`null`: an explicitly-assigned non-value.
* Javascript will never set anything to `null` by itself. `null` only appears when you tell it to.
* If I'm not mistaken, the only thing that's inherently `null` in Javascript is `null` itself!
* **Q: Can you imagine a situation where that would be useful?**
  * Placeholder for a variable that you know will be replaced with an actual value later on.

So the main difference between `undefined` and `null` is intention. Other than that, they're both...nothing.  

### Syntax

Variable syntax
* Variables should be named using camelCase lettering.
  * First letter of first word lowercase. First letter of remaining words uppercase.
  * No spaces or punctuation between words.

```js
var pizzaTopping = "pepperoni";
```

Semicolons
* General practice is to end every line with a semi-colon.
* Usage depends on the developer.

Comments
* **Q: Why would you use comments?**
  * Use to explain the purpose or reasoning behind a piece of code.
  * Help out other developers and future you.
    * If anything, it will help us out when grading your projects!

```js
// Single line

/*
  Multiple
  line
  comments
*/
```

### Prompt

We've learned a lot about basic data types, but it'd be nice if we had a way of getting user input into our browser! We'll learn some ways to use forms and such later in the course, but for now, we'll be getting user input using the `prompt()` function.

At any point in our JS code, if we write `prompt()` a pop up box will open in our browser for a user to enter in text.

```js
// prompts user and stores value in the variable
var valueOfPrompt = prompt()
// logs value stored
console.log(valueOfPrompt)
```

You can also pass in a string as an argument to have the pop up box contain that string as a ... prompt.  

```js
var age = prompt("How old are you?")
```

### "Truthiness" and "Falsiness"
So we all know the boolean values of `true` and `false`. But there is also a concept of "truthy" and "falsey". In Javascript, the following things are "falsey"...
* `false`
* `0` (zero)
* `""` (empty string)
* `null`
* `undefined`
* `NaN` (a special Number value meaning- Not-a-Number!)
> Everything else is "truthy". Why might we need this programmatic concept of "truthy" and "falsey"? (ST-WG)

# Homework

**[Choose Your Own Adventure](https://github.com/ga-wdi-exercises/choose_your_own_adventure_js)**

# Review Questions

* When would you use an array over an object? And vice-versa?
* What is the difference between `undefined` and `null`?
* Provide an example of a semantically-named variable. Explain your choice.
* What role does Javascript play on a website?
* What are the five primitive data types?
* What are the two composite data types? When would you use each?
* What is an example of type coercion?
* What is an example of a semantically-named variable?
