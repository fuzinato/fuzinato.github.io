---
layout: post
title: 'Elm: Using custom decoder with json-decode-pipeline '
date: 2018-01-03 00:00:00 +0000
tags: elm, framework
resources: https://www.brianthicks.com/post/2016/12/29/adding-new-fields-to-your-json-decoder/
category: ''
---
It seems that parsing JSON into Elm's model is not that easy. For start, package that comes with elm does not let you map more than 8 fields in object (v 0.18), so they recommend using external package [elm-decode-pipeline](http://package.elm-lang.org/packages/NoRedInk/elm-decode-pipeline/latest). 
My main issue was parsing optional nested model inside main model. Main model looks like this:
```elm
type alias Model =
    { day : String
    ...
    , coordinates : Maybe Coordinates
    ...
    }
```
and Coordinate type:
```elm 
type alias Coordinates =
    { latitude : String
    , longitude : String 
    }
```