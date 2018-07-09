<sub>/ [CSS Documentation](..) / Principles of Object-Oriented CSS</sub>

# Principles of Object-Oriented CSS

## Why would you want to?

## Terminology

When talking about [Object-Oriented CSS][object-oriented-css] it's important to first note the historic usage by Nicole Sullivan for [OOCSS][oocss]. While the names overlap, this document is using the generic meaning of "Object-Oriented" taken from "Object-Oriented Programming".

To further add to the confusion, many OOP languages use the term "class" to refer to a template used to create objects. In CSS "class" typically refers to a selector that selects nodes based on the space-separated list of text in the nodes' class attributes.

To disambiguate the two terms, "class (OOP)" will be used to refer to the OOP concept, and "class (CSS)" will be used to refer to the CSS concept.

<!--
Better terms are needed than "class (OOP)/class (CSS)"

Up for consideration:

 * OOP class/CSS class
 * Object Definitions/classes

Rejected options:

 * Types/classes - "types" is used in CSS specs to refer to element selectors
 * Templates/classes - "templates" are used in HTML and too many other contexts to be useful
-->

## What is an object?

Before we can start applying object-oriented principles to CSS, we need to have a solid understanding of what is an object _really_?

In class-based object-oriented programming paradigms an object is an instance of a class (OOP). These instances are collections of class-members in a shared context which can include:

 * fields
 * variables
 * properties
 * data structures
 * functions
 * methods
 * procedures

Since there are a lot of variations in terminology here, we can simplify things greatly when we [consider all class-members to be functions or special types of functions][cmf].

So really, **objects are collections of functions applied to a shared context**.

And since we're already describing everything as a function, we can consider the constructor to be a function that creates a new context for the collection of functions.

<!-- Insert "Boy, that escalated quickly" gif -->

## So&hellip;how does all of this apply to CSS?

Despite CSS being a declarative language, we can treat CSS [rules][rules] as declaring functions, and their usage within HTML as an invocation of the declared function.

Here is an example of a JS function declaration being invoked by HTML:

```js
// example.js
function example () {
  document.body.style.backgroundColor = 'red'
}
```

```html
<!DOCTYPE html>
<title>Example</title>
<script src="example.js"></script>
<body onload="example()">
</body>
```

Here is an example of a CSS "function" being invoked by HTML:

```css
/* example.css */
.example {
  background-color: red;
}
```

```html
<!DOCTYPE html>
<title>Example</title>
<script src="example.js"></script>
<body class="example">
</body>
```

So with our abstract definition of "object" and our ability to create "functions" in CSS, let's look at some ways we can create collections of functions and new contexts.

## Declaring classes (CSS) to create classes (OOP)

The simplest way to create a collection of "functions" in CSS is to just declare a bunch of classes (CSS):

```css
.a {...}
.b {...}
.c {...}
...
```

That's nice and all, but that doesn't really help us with creating a new context. It's akin to having just declared a handful of functions in JavaScript:

```js
function a () {...}
function b () {...}
function c () {...}
...
```

If we wanted a JS class, we'd do it a bit differently. We'd use a `class` declaration to indicate that the functions share a context:

```js
class Example {
  a () {...}
  b () {...}
  c () {...}
  ...
}
```

Note that the JS example is really syntactic sugar for:

```js
function Example () {...}
Example.prototype.a = function () {...}
Example.prototype.b = function () {...}
Example.prototype.c = function () {...}
...
```

In CSS there's no real restriction on how "functions" are declared or where they're used, so if we want to follow JavaScript's lead we can name our "functions" similarly\*:

```css
.Example {...}
.Example_prototype_a {...}
.Example_prototype_b {...}
.Example_prototype_c {...}
...
```

<sub>\* here `_` is used to replace `.` as period characters would have to be escaped, which would otherwise look something like `.Example\.prototype\.a`. This would certainly be a source of confusion and bugs. Sometimes JS documentation replaces `prototype` with `#` (`Example#a`), which would be convenient if `#` didn't have to be replaced as well (`.Example\#a`).</sub>

Now that we've mimicked the JS format, we can clean things up a bit. `prototype` is redundant and unnecessary:

```css
.Example {...}
.Example_a {...}
.Example_b {...}
.Example_c {...}
...
```

With this simplification, we can generalize the rule for creating a context within CSS.

In object-oriented CSS, plain classes (CSS) can create a new context. Other classes (CSS) prefixed with the given context name create the collection of functions needed to create an "object".

## Using declared classes (OOP)

When a class (OOP) has been declared in JavaScript, using it involves creating an instance before calling any of its functions:

```js
const example = new Example()
example.a()
example.b()
example.c()
...
```

When a class (OOP) has been declared in CSS, using it should involve creating an instance before calling any of its functions:

```html
<div class="Example">
  <div class="Example_a">...</div>
  <div class="Example_b">...</div>
  <div class="Example_c">...</div>
  ...
</div>
```

## SOLID

[**S**ingle Responsibility Principle][S]  
[**O**pen&ndash;Closed Principle][O]  
[**L**iskov Substitution Principle][L]  
[**I**nterface Segregation Principle][I]  
[**D**ependency Inversion Principle][D]

[S]: single-responsibility-principle
[O]: open-closed-principle
[L]: liskov-substitution-principle
[I]: interface-segregation-principle
[D]: dependency-inversion-principle

[cmf]: class-members-as-functions
[object-oriented-css]: ../terms-and-definitions/object-oriented/css
[oocss]: ../terms-and-definitions/oocss
[rules]: ../terms-and-definitions/rules