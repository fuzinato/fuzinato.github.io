---
layout: post
title: Function Currying in Elm
date: 2017-12-29 00:00:00 +0000
category: Theory
tags: Elm, functional programming
resources: ''
---
While learning [http://elm-lang.org](Elm) I came across concept common in functional programming called Currying, where you partially execute some function and return a function that composes the first one.

Here is an example in Elm:

Lets say there is a function that divides 2 numbers and returns string:
```elm 
divideNumbers: Float -> Float -> String
divideNumbers divisor divident = 
  divident / divisor
  	|> toString
```
Now lets say there we want to make a function that always divides by 2 (divisor = 2). We could compone new function from `divideNumber`:
```elm
divideBy2: Float -> String
divideBy2 =
	divideNumbers 2
```
  