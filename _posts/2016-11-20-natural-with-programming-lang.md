---
layout: post
title: Why you should use natural english language to grasp some concept in any programming language
comments: true
date:   2016-11-20
categories: programming english python java javascript
---
One might think why did the creators of different programming language, did not use
natural language as a means of communicating to computers.
First let see the definition of a language.

> Language can be seem as the method of human communication, either spoken or written, consisting of the
use of words in a structured and conventional way.


# Human communication
Always see programming as a way not only communicating to a computer
but also communicating to yourself and another programmer


# Spoken or written
Programming language are not spoken but written

# Structured and conventional way
All programming language comes with tons of  words and a conventional way in which  this
word must be structured. Basically we are talking about the programming language
**Syntax and  Semantics**



Let see how we can use natural english language meaning to understand 
some weird name in programming language

### Programming word `class`.
Coming from an OOP background in Java newbies get to ask why is it call `Class`


> *Class*: [natural english language meaning]
    a set or category of things having some property or attribute in common and
    differentiated from others by kind, type, or quality.

In java this is how we construct a Class 

``` java
public class Car{          ----------> Car is a thing
    private String color;  ----------> Having some property
    private String model;
}
```
### Programming word `public` and `private`

> *Public*: [natural english meaning]
  an open view of something 
  *Private*  closed to a particular entity, not for every one

In most program we frequently hear the word private and public. 
Simply when we construct this sample

```java

public class Person{
    public String name;
    private int age;
}
```
we are saying our `name` property can be modified and visible to any one,
but my `age` property can't be accessed by anybody but just me alone.


### Programming word `Array`
> *Array* [natural english meaning]
 - a large group of things or people, especially one that is attractive or causes admiration or has been positioned in a particular way
 - is an impressive display or range of a particular type of thing.

If you have done a little bit of programming you would been wondering why is Array
a big part of most programming language, almost any programming language talks, a lot
about arrays 

With this in mind, let see how we build arrays in any programming language, remember it is a large
group of things (also know as collections of things).

```javascript
var laptops  = ["Mac","HP", "Dell"]
var numbers =  [1,2,3,4,5]
```

```python
friends  = ["Peter","Mary", "Faiz"]
website =  ["github.com", "facebook.com", "meduim.com"]
```

### Programming word `split`
> Split [natural english meaning] dividing a particular object into two or more groups 

In python and javascript we see this programming word `split`, normally this word is one of
method of a `String` object

```python
people = "Bob,Alice,James,John,Peter"
names = people.split(',')
print name   # result is [Bob, Alice, James, John, Peter] 
``` 

```javascript
var people = "Bob,Alice,James,John,Peter"
var names = people.split(',')
console.log(names)   //result is ['Bob', 'Alice', 'James, John, Peter] 
``` 

> *Conclusion there are thousand of words in any programming language api, we can't dig into all of them, but 
knowing the meaning of this word in a natural english language form, can give you more
insight on how this word were created by the programming language api authors and how to structured 
them in the programming language conventional way.*