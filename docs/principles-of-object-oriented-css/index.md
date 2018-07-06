<sub>/ [CSS Documentation](..) / Principles of Object-Oriented CSS</sub>

# Principles of Object-Oriented CSS

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

## What is an Object?

Before we can start applying object-oriented principles to CSS, we need to have a solid understanding of what is an object _really_?

In class-based object-oriented programming paradigms an object is an instance of a class (OOP). These instances are collections of class-members which can include:

 * fields
 * variables
 * properties
 * data structures
 * functions
 * methods
 * procedures

Since there are a lot of variations in terminology here we can simplify things greatly when we [consider all class-members to be functions or special types of functions][cmf].

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