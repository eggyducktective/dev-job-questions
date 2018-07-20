
# Interview Questions PART 1

# GROUP A
- What is Rails?

```
Short for Ruby on Rails which is a web application framework that provides the underlying infrastructure necessary to deploy a website. It's a 'server-side' backend framework.
Framework not a Library = library is a toolkit used to deploy functionality - Framework is more like a whole toolshed.
One of the characteristics of Rails is that it favours 'convention over configuration' - which means that developers have sensible defaults provided out-of-the-box without requiring configuration. Rails is opinionated - someone else's ideas about best practice are baked in - e.g. RESTful routing
Rails makes using common standards easy - such as JSON for data transfer; HTML, CSS and Javascript for front-end components; ActiveRecord for data manipulation.
Rails was one of the 1st frameworks that focused on testing as a cornerstone for development.
```

- What is MVC and what are the components of Rails MVC?

```
MVC = Model-View-Controller
It's a design pattern used for all types of applications but common with web-based applications. It divides a solution into 3 components that are connected:
* Model = back-end component for handling data & business logic
* View = handling user interactions and display
* Controller = is the glue between the View that the user interacts with and the Model where the data and logic is stored.
```

- Explain the different variable scopes in Ruby?

```
Scope refers to where a variable is visible. Important to make debugging easy - variables should be defined on a need to know basis.
* Local Variable = Scope is within the object where the variable is defined. E.g. within a method ... e.g. var = 10
* Global Variable = Visible throughout the entire Ruby script ... e.g. $var
* Instance Variable = E.g. @var ... Visible within an object such as to all methods within a class instance
* Class Variable = E.g. @@var ... Visible within a specific class and any sub-class. Available to any instance that has been instantiated from the class and can subsequently be changed from within any instance of a class
```

- Name a few object-oriented concepts in Ruby?

```
Ruby is about as pure as you can get in terms of being object-oriented as everything is an object, even numbers
Concepts used when describing OO:
* Inheritance = any class will inherit definitions from parent class. Apart from 'mixins' it's not possible for a class to have more than one immediate parent
* Encapsulation = in Ruby data is encapsulated within objects and manipulated via methods which are interfaces to those objects
* Abstraction = The Model abstracts the data layer from the underlying technology used for the database
```

- How would I execute some code for each element in a collection?

```
By looping over the collection. Using:
.each
.map
.filter / .select
.reject
.reduce
Either with an explicit loop such as a "for" that iterates over every element or by calling a method that accepts the collection as an input
```

# GROUP B
- What is meant by convention over configuration?
- What are the Rails naming conventions?
- When should `load` be used in Ruby, as opposed to `require`?
- Explain RESTful architecture.
- Explain the difference between empty? and nil?

# GROUP C
- What is a framework?
- How does MVC work?
- Why would you use Rails rather than another framework?
- What operators are available in Ruby?
- Compare Ruby on Rails and PHP

___

# Interview Questions 2

# GROUP A
- What is a destructive method?
- What is the Ruby convention for naming methods?
- What are filters in Rails? Give some examples.
- Provide an example showing how an iterator is used
- What is the difference between an argument and a parameter?

# GROUP B
- Explain how sessions work, specifically in relation to cookies.
- What are the looping structures in Ruby?
- Compare validations, callbacks and observers in ActiveRecord
- What are helpers in Rails?
- Compare instance and class variables

# GROUP C
- Describe the concept of visibility in Rails
- What is meant by DRY?
- What is the log to check for errors in Rails?
- What are GET and POST methods?
- What is YAML?

___

# Interview Questions 3

# GROUP A
- Give some examples of what you could define in a Rails model.
- What is ORM in Rails?
- What is TDD?
- How can two databases be accessed from the same Rails application?
- What is an IP address?

# GROUP B
- What are the associations available in ActiveRecord models?
- How does GPS work?
- How do you add a method to jQuery?
- What is browser sniffing? When would you use it?
- What's the difference between .call and .apply?

# GROUP C
- How might your prevent name conflicts in Javascript?
- How would you model a coffee shop in Rails?
- Why is it better to serve site assets from multiple domains?
- What is FOUC? How do you avoid FOUC?
- What happens when you enter a URL into your browser?

___

# Interview Questions PART 4

# GROUP A
- How would you make a web page load faster?
- What is the difference between a SPAN and a DIV?
- If you could master one technology this year, what would it be?
- What's the difference between a relative, fixed, absolute and statically positioned element?
- What is a garbage collector and how does it work?

# GROUP B
- What is the role of a router in Rails?
- What is hoisting in Javascript?
- What is your favourite browser and why?
- Explain event delegation
- Explain how `this` works in JavaScript

# GROUP C
- Explain why the following doesn't work as an IIFE: `function foo(){ }();`. What needs to be changed to properly make it an IIFE?
- What is a closure, and how/why would you use one?
- What's a typical use case for anonymous functions?
- Explain AJAX in as much detail as possible.
- What is the difference between == and ===?

___

# Interview Questions PART 5

# GROUP A
- What excites or interests you about coding?
- Can you describe the difference between progressive enhancement and graceful degradation?
- Explain the importance of standards and standards bodies.
- Explain some of the pros and cons for CSS animations versus JavaScript animations.
- What does CORS stand for and what issue does it address?

# GROUP B
- What does a doctype do?
- What are data- attributes good for?
- What is the difference between classes and IDs in CSS?
- What's the difference between "resetting" and "normalizing" CSS? Which would you choose, and why?
- Describe pseudo-elements and discuss what they are used for.

# GROUP C
- What does * { box-sizing: border-box; } do? What are its advantages?
- What's the difference between inline and inline-block?
- Have you played around with the new CSS Flexbox or Grid specs?
- How is responsive design different from adaptive design?
- What's the difference between a variable that is: null, undefined or undeclared? How would you go about checking for any of these states?

___

# Interview Questions PART 6

# GROUP A
- Make this work: `duplicate([1,2,3,4,5]); // [1,2,3,4,5,1,2,3,4,5]`
- Why is it called a Ternary expression, what does the word "Ternary" indicate?
- What is "use strict";? what are the advantages and disadvantages to using it?
- Create a for loop that iterates up to 100 while outputting "fizz" at multiples of 3, "buzz" at multiples of 5 and "fizzbuzz" at multiples of 3 and 5
- Why is it, in general, a good idea to leave the global scope of a website as-is and never touch it?

# GROUP B
- Explain what a single page app is and how to make one SEO-friendly.
- Explain the differences on the usage of foo between function foo() {} and var foo = function() {}
- What are some advantages/disadvantages to testing your code?
- What is the purpose of a code style linting tool?
- What is the value of `foo`: `var foo = 10 + '20';`

# GROUP C
- What does this return: `"i'm a lasagna hog".split("").reverse().join("");`
- What's a cool project that you've recently worked on?
- Who inspires you in the front-end community?
