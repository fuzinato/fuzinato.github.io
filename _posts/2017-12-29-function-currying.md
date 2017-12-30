---
layout: post
title: Function Currying in Elm
date: 2017-12-29 00:00:00 +0000
category: Theory
tags: Elm, functional programming
resources: ''
---
While learning [Elm](http://elm-lang.org) I came across concept common in functional programming called __Currying__, where you partially execute some function and return a function that composes the first one.

Here is an example in Elm:

Let's write  a function that divides 2 numbers and returns difference as a string:
```elm 
divideNumbers: Float -> Float -> String
divideNumbers divisor dividend = 
  dividend / divisor
    |> toString
```
Now lets say there we want to make a function that always divides by 2 (divisor = 2). We can create a new function using `divideNumber` fn:
```elm
divideBy2: Float -> String
divideBy2 =
  divideNumbers 2
```

Currying should not be confused with __composition__. To quote [reply form stackoverflow](https://stackoverflow.com/a/36275509):
> Currying is a way of constructing functions that allows partial application of a function’s arguments.

> Compose should return a function that is the composition of a list of functions of arbitrary length. Each function is called on the return value of the function that follows.