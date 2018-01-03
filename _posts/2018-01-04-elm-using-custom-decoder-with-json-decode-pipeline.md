---
layout: post
title: Optional custom decoder in Elm
date: 2018-01-03 00:00:00 +0000
tags: elm, framework
resources: https://www.brianthicks.com/post/2016/12/29/adding-new-fields-to-your-json-decoder/
category: ''
---
It seems that parsing JSON into Elm's model is not that easy. For start, the package that comes with elm does not let you map more than 8 fields in an object (v 0.18), so they recommend using external package [elm-decode-pipeline](http://package.elm-lang.org/packages/NoRedInk/elm-decode-pipeline/latest){:target="_blank"}. 
My main issue was parsing optional nested model inside the main model. Parent model looks like this:
```elm
type alias Meetup =
    { name : String
    , time: String
    , url: Maybe String
    , coordinates : Maybe Coordinates
    ...
    }
```
and optional (Coordinate) model:
```elm 
type alias Coordinates =
    { latitude : String
    , longitude : String 
    }
```

### Decoding values
In order to properly decode optional values, we need a decoder for both "Model" and "Coordinate" model. They look as following:
```elm
coordinatesDecoder : Decode.Decoder Coordinates
coordinatesDecoder =
    decode Coordinates
        |> required "latitude" Decode.string
        |> required "longitude" Decode.string
 
 
meetupDecoder : Decode.Decoder Meetup
meetupDecoder =
    decode Meetup
        |> required "name" Decode.string
        |> required "time" Decode.string
        |> optional "url" (Decode.map Just Decode.string) Nothing
        |> optional "coordinates" (Decode.map Just coordinatesDecoder) Nothing
        ...
```

### Retrieving coordinate values
When rendering, we need to retrieve keys for coordinate, but they are wrapped in __Just__ elm wrapper.
Parsing function would do the trick:
```elm
getMaybeCoord : Maybe Coordinates -> Coordinates
getMaybeCoord ma =
    case ma of
        Just a ->
            a

        Nothing ->
            Coordinates "" ""
```
 and using it in view would look something like this [^1]:
 ```elm
div [] [ text ((getMaybeCoord meetup.coordinates).latitude ++ " " ++ (getMaybeCoord meetup.coordinates).latitude) ]
```
[^1]: Would be better to extract parsing of coordinated to another function, but for my demo it would suffice