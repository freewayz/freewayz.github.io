---
layout: post
title: "Using english language to understand some programming language"
modified:
categories: blog
excerpt:
tags: ["python", "java","code", "programming"]
comments: true
date: 2016-11-20
---


Over the years, I have been thinking why did the inventors of different programming language,
did not use natural language *(english)* as a means of writing programs that computer can understand.


## What is a Language 
> Language can be seem as the method of human communication, either spoken or written, consisting of the use of words in a structured and conventional way.


###### Human communication
See programming language as not only communicating to a computer
but also communicating to yourself or another programmer.

###### Spoken or written
Programming language are not spoken but written.

###### Structured and conventional way
Most programming language have it own flow and way things ought to be done. 
Basically we are talking about the programming language *Syntax and  Semantics of the language*

OK, let see how we can use natural english language to make sense of some programming language keywords.

##### `class`
Coming from an OOP background in Java as newbies, I get to ask why is it call `Class`.
> *Class: [natural english language meaning] a set or category of things having some property or attribute in common and differentiated from others by kind, type, or quality*

``` java
        public class Car {          // Car is a thing, OK this make sense
            private String color;  //  Having some property
            private String model;
        }
```

##### **`public` and `private`**
>   *Public*: [natural english meaning] an open view of something  <br/> *Private*  closed to a particular entity, not for every one

```java
    public class Person {
        public String name; // OK this is can been see by another program or class
        private int age; // OK no program or class can touch this.
         /*
                we are saying our `name` property can be modified and visible to any one,
                but the `age` property can't be accessed by anybody but just me alone.
        */
    }
```

##### **arrays []**
> *Array* [natural english meaning]
 - a large group of things or people, especially one that is attractive or causes admiration or has been positioned in a particular way
 - is an impressive display or range of a particular type of thing.

Array a big part of most programming language, almost any 
programming language talk a lot about arrays  
*With this in mind, let see how we build arrays in any programming language, remember it is a large
group of things (also know as collections of things).*

```javascript
var laptops  = ["Mac","HP", "Dell"]
var numbers =  [1,2,3,4,5]
```

```python
friends  = ["Peter","Mary", "Faiz"]
website =  ["github.com", "facebook.com", "meduim.com"]
```

##### **split**
> Split [natural english meaning] dividing a particular object into two or more groups 

In python and javascript we see this programming word `split`, this word is the name  of
a method of a `string` object.

```python
people = "Bob,Alice,James,John,Peter"
names = people.split(',') # OK break this long word into some group of words
print name   # ['Bob', 'Alice', 'James', 'John', 'Peter'] 
``` 

```javascript
var people = "Bob,Alice,James,John,Peter"
var names = people.split(',')
console.log(names)   // ['Bob', 'Alice', 'James', 'John', 'Peter'] 
``` 

> *Conclusion there are thousand of words in any programming language api, we can't dig into all of them, but  knowing the meaning of this word in a natural english language form, can give you more insight on what that particular keyword does and how to use it in any program. So next time I see a word `Thread` I check up the natural english meaning before knowing how it works in any programing language*