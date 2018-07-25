
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

```
Class names are Capitalised CamelCase.
Methods and variables are snake_case.
Database tables use snake_case. Table names are plural.
Column names in the database use snake_case, but are generally singular.
For a joint table, the name needs to follow alphabetical order.
E.g. create_cocktails_ingredients.rb  ----> correct
     create_ingredients_cocktails.rb  ----> incorrect

Model class names use Capitalised CamelCase. A Model is singular because it references a single object like User.
Model attributes and methods use snake_case and match the column names in the database.
Model files go in app/models/#{singular_model_name}.rb.

Relations use snake_case and follow the type of relation, so belongs_to is singular while has_many is plural.

Controller class names use CamelCase and have Controller as a suffix. The Controller suffix is always singular.
The name of the resource is usually plural - it is the controls (methods) for the collection of Users. (except Session Controller!).
Controller actions use snake_case and usually match the standard route names Rails defines (index, show, new, create, edit, update, delete).
```

- When should `load` be used in Ruby, as opposed to `require`?

```
Require “loads” the file once and it is usually is for a file not on local machine. For requiring local files, require-relative would be used.
Load will do it each time it is called and it is for local files.

```

- Explain RESTful architecture.

```
RESTful architecture describes the fact that any interaction follows certain paths: GET, PUT, POST, DELETE for looking up, updating, creating or deleting respectively

* Resources being identified by a persistent identifier: URIs are the ubiquitous choice of identifier these days
* Resources being manipulated using a common set of verbs: HTTP methods are the commonly seen case - the venerable Create, Retrieve, Update, Delete becomes POST, GET, PUT, and DELETE. But REST is not limited to HTTP, it is just the most commonly used transport right now.
* The actual representation retrieved for a resource is dependent on the request and not the identifier: use Accept headers to control whether you want XML, HTTP, or even a Java Object representing the resource
* Maintaining the state in the object and representing the state in the representation
* Representing the relationships between resources in the representation of the resource: the links between objects are embedded directly in the representation
* Resource representations describe how the representation can be used and under what circumstances it should be discarded/refetched in a consistent manner: usage of HTTP Cache-Control headers
```

- Explain the difference between empty? and nil?

```
nil? Is a method that can be called on all objects and return “true” for the nil object and “false” for anything else. It tests whether the receiver is the nil object, that is the only instance of calls NilClass, which is often used to indicate an invalid value. This method is defined in class Object, and thus is available for every object.
* needed because nil and false are the only falsy values. 0 and “” are still truthy
* nil? Is the only thing that works on `nil` itself
* “”.nil? -> false


* empty? is a method on some objects like Arrays, Hashes and Strings (i.e. it isn’t defined for all classes). The exact behaviour will depends on the specific object. Usually, empty? Is used to test whether an object is “empty” - it is testing for containers(arrays, hashes) that have nothing in them. For example:

* "".empty?     -> true
* 0.empty?      -> NoMethodError: undefined method `empty?' for 0:Integer
* String#empty? -> returns true if the string contains no characters;
* Array#empty?  -> Return true if the array has no entries.
* Hash#empty?   -> Return true if the hash has no entries.
```

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

```
A destructive method is one that mutates or changes the original object. A nondestructive
method is one that doesn't change the original object but creates a
copy. In Ruby they are often named with an exclamation on the end ... but not in
every case (e.g. "concat").
* Lots of basic array methods are destructive without the ! naming. E.g. shift, unshift,
push, pop, <<<
* Some methods (e.g. assignment =, +=, ...) are always immutable.
```

- What is the Ruby convention for naming methods?

```
Ruby uses snake case for the naming of methods.
Which is all lower case characters with words separated by an underscore.
The only non alphanumeric characters allowed in a method name are _ ? ! =
Methods ending with a ! should indicate dangerous/destructive methods, or methods which modify an object in place. eg arr.reverse vs arr.reverse!
Methods ending with a ? should indicate interrogative/ predecated - booleans methods (questions answered by the method name). .even?
Methods ending with an = should indicate an assignment method, where the return value is ignored and the arguments are returned instead.

eg, method name is "my_method=" (a setter) -> normally uses attr_accessor

def my_method=(arg)
	return "someval"
end

p my_method=('testing')
will return "testing"

```

- What are filters in Rails? Give some examples.

```
Filters are methods that run "before", "after or "around" a controller action. They are inherited
and can be defined on a parent controller.
* "before" filters run before an action and can cause the action to skip altogether. A typical use
case is to check a user is logged in before running an action ( before_action :require_login )
* You can configure a controller action to skip a before action if necessary
( skip_before_action :require_login, only: [:new, :create] )
* An "after" filter runs after an action is successfully completed. It is typically used for logging as
you get access to returns from the action itself. It can modify the response.
* An "around" filter is less common. It is used to wrap an action and it manages the "yield" ... an
example is workflow where an action requires approval before proceeding. Or exception
handling.
* Nice way to DRY up code
```

- Provide an example showing how an iterator is used

```
(map)
iterate 0 to 5 in one line
(0..5).each { |x| p x }

iterate an array of words
['duck', 'bear', 'cat'].each do |x|
   p x
end
```

- What is the difference between an argument and a parameter?

```
* A parameter is defined in the function definition/declaration/prototype. It denotes
information that must be provided when the function is invoked (although they can
be defaulted or ignored in the function logic if not provided).
* An argument is passed to a function when the function is called.
```

# GROUP B
- Explain how sessions work, specifically in relation to cookies.

```
The browser is making a request to the server (eg login)
in response, the server sends a response that has cookie header in it (_session) / if successful (REMEMBER THIS, U EGGY SERVER)

When browser makes official request (by GET), it has header as cookie ? (reminds the server ) (Here is what you ask me to remember)
(Rails guide, how session works)
(cookie scope : the domain name) / cookie can be set to expire
```
- What are the looping structures in Ruby?

```
loop do
end

while
end

until
end

for i in ...... do
end

5.times do |i|
end

.each / .map / .select > < .reject
```

- Compare validations, callbacks and observers in ActiveRecord

```
Validations check that incoming data is in the proper format before being put into the database.

However, a callback is usually a private method which triggers during any time during an object’s life cycle. They are used to add additional logic to actions, or may be common to many actions and used to DRY up code. E.g. Before actions can be used to sanitise inputs.
If some piece of logic is shared by the entire application, then observers can be used to distribute responsibility. If said piece of logic needs to be updated on controllers’ methods, then using observers to run alongside the application.
```

- What are helpers in Rails?

```
(pluralize, helper provides for us) (use inside template)
helper.pluralize 1, 'mouse'
helper.number_to_currency 213
```

- Compare instance and class variables

```
class variable: visible to every instance of some class (@@varible)
instance variable: (@variable) unique to an instance
```

# GROUP C
- Describe the concept of visibility in Rails

```
public, private method (can only be access  within method inside a class), protected (methods accessible from inside a class  (a child class) that is inside another class)
http://www.zenruby.info/
```

- What is meant by DRY?

```
DRY - Don't repeat yourself, clean code, turn repetitive codes into a function. Makes codes more testable, components more reusable
```

- What is the log to check for errors in Rails?

```
development.log (inside the log)
```

- What are GET and POST methods?

```
- GET : send request to a server, to get information (get info), only for asking info, cant change info
- GET : submit a search, wouldnt change database (inside a query string)
- POST : send data to the server, store to the database (post/send info) (url doesnt have the info)
```

- What is YAML?

```
Use for storing API key, environment variable, use it for config file, converts it to a hash/ nested hash
key value pair
```

___

# Interview Questions 3

# GROUP A
- Give some examples of what you could define in a Rails model.

```
* In a model, you can define the association to other models. Eg, you can define if it
is a one-to-one, one-to-many, many-to-many etc.
* In addition, you can define whether the model belongs to another model or if it has
other models.
* If the rails application were a game, the logic of the game could be defined in the
relevant models.
```

- What is ORM in Rails?

```
ORM stands for Object-Relational-Mapping
* It is a technique of connecting the objects to the tables of a Database. We do not
have to call the Database manually and write queries.
* Lets us to interact with the data as normal Ruby object
* Rails provides ActiveRecord to achieve this.
* Eg: SQL query —> SELECT * FROM users
* ActiveRecord -> User.all
```

- What is TDD?

```
* TDD is an iterative software development process where we first write the test with
the idea that it must fail
* Test-first development where we write a test before writing the code. TDD mainly
* The goal of TDD is to write clean code that works.
```

- How can two databases be accessed from the same Rails application?

```
Create a second <somename>.yml file in the config directory with connection
information for the 2nd database. Use a different port to the default database port of
5432.
• Create an initialiser in config/initializers subdirectory for the new database. The initialiser
will read the new .yml file and store its contents in a hash.
• Once the connection and initialiser are done the ActiveRecord establish_connection
method can be used to connect. The best option is to create a base class for any
models that need to use the 2nd database. The base class will inherit from
ActiveRecord::Base and will call establish_connection to the 2nd database. Subsequent
models will inherit from the base class.
• Using a base class reduces the number of connections that need to be established
which is more efficient and scalable.
```

- What is an IP address?

```
An Internet Protocol address, it is a numerical label assigned to each device connected to a computer network, that uses the Internet Protocol for communication. (Main purposes: host or network interface identification and location addressing). Written in human readable notations.
```

# GROUP B
- What are the associations available in ActiveRecord models?

```
belongs_to
has_one
has_many
has_many :through
has_one :through
has_and_belongs_to_many
```

- How does GPS work?

```
Global Positioning System.
a network of about 30 satellites orbiting the Earth at an altitude of 20000km. Once it has information on how far away at least three satellites are, your GPS receiver will pinpoint your location using a process called "Trilateration".
```

- How do you add a method to jQuery?

```
b = $('.bar')
We want to have something like: b.doSomething()
You have to add your function to the $.fn namespace. Please note that inside the function, this will refer to the jQuery object, not a DOM object.
$.fn.doSomething = function () {
this.css('color', 'red');
};
$('.bar').doSomething();
```

- What is browser sniffing? When would you use it?

```
Browser sniffing is the detection of a visitor’s web browser by a website or web application. With detection, a developer can account for the differences in display to provide a more consistent experience.

```

- What's the difference between .call and .apply?

```
var func = function(){ alert('hello!'); };
func.apply();
vs
func.call();
The difference is that apply lets you invoke the function with arguments as an array; callrequires the parameters be listed explicitly. A useful mnemonic is "A for array and C for comma."
Pseudo syntax:
theFunction.apply(valueForThis, arrayOfArgs)
theFunction.call(valueForThis, arg1, arg2, ...)
There is also, as of ES6, the possibility to spread the array for use with the call function, you can see the compatibilities here.
function theFunction(name, profession) { console.log("My name is " + name + " and I am a " + profession +"."); } theFunction("John", "fireman");
theFunction.apply(undefined, ["Susan", "school teacher"]); theFunction.call(undefined, "Claude", "mathematician"); theFunction.call(undefined, ...["Matthew", "physicist"]); // used with the spread operator

```

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
