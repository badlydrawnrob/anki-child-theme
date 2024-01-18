---
title: Simple Card data
---


## ★ Title

In this example, `viewThumbnail` only takes one argument; `model.selectedUrl`. Yet, it still works! Explain why.


## ☆ Subtitle

A partial function


## ☆ Syntax (inline code)

(viewThumbnail selectedUrl thumb)


## ★ Sample (code block or image)

```elm
..

-- View --
view model =
  ..
    ..
    , div [ id "thumbnails" ]
        (List.map
          (viewThumbnail model.selectedUrl)  -- Apply the function
          model.photos
        )
    ..

-- Helper functions --
urlPrefix =
  "http://elm-in-action.com/"

viewThumbnail selectedUrl thumb =
  img [ src (urlPrefix ++ thumb.url)
      , classList [ ("selected", selectedUrl == thumb.url) ]
      ..
      ] []

-- Model --
{ photos =
    [ { url = "1.jpeg" }  -- Our list of urls
    , { url = "2.jpeg" }
    , { url = "3.jpeg" }
    ]
  , selectedUrl = "1.jpeg"  -- Has the url been selected?
  }
```


## ★ Key point (code block or image)

```elm
viewThumbnail selectedUrl thumb =
  img [ src (urlPrefix ++ thumb.url)
      , classList [ ("selected", selectedUrl == thumb.url) ]
      ..
      ] []
```
```terminal
<function>
    : String -> { a | url : String } -> Html { data : String, description : String }
```
```elm
-- A partial application, or a curried function
viewThumbnail "1.jpeg"
```
```terminal
<function>
    : { a | url : String } -> Html { data : String, description : String }
```


## ★ Key point notes

This is a big chunk of code!!! It's quite simple though:

1. We _partially_ apply `viewThumbnail` passing only one argument (a `"string"`)
2. `List.map` takes a function and a list
    - `model.photos` gives us a list of records
3. `List.map` cycles through the records
4. Each cycle calls the `viewThumbnail` function, **passing a record as the second argument**!
5. Each cycle would look like this:
    - `viewThumbnail "1.jpeg" { url = "2.jpeg" }`
    - Each cycle would pass `viewThumbnail` a different record
6. We now have a list of `img []`, each with it's own url!
7. Our `viewThumbnail` function also checks the `model.selectedUrl`, and adds a `"selected"` class if it matches.



## ✎ Other notes

View the [full program](https://ellie-app.com/q4j6ps87Cj5a1) which consumes the function. Here's some [other curried function examples](https://www.codingexercises.com/guides/quickstart-elm-part-7) too.


## ✎ Markdown

```elm
..

-- View --
view model =
  ..
    ..
    , div [ id "thumbnails" ]
        (List.map
          (viewThumbnail model.selectedUrl)  -- Apply the function
          model.photos
        )
    ..

-- Helper functions --
urlPrefix =
  "http://elm-in-action.com/"

viewThumbnail selectedUrl thumb =
  img [ src (urlPrefix ++ thumb.url)
      , classList [ ("selected", selectedUrl == thumb.url) ]
      ..
      ] []

-- Model --
{ photos =
    [ { url = "1.jpeg" }  -- Our list of urls
    , { url = "2.jpeg" }
    , { url = "3.jpeg" }
    ]
  , selectedUrl = "1.jpeg"  -- Has the url been selected?
  }
```

```elm
viewThumbnail selectedUrl thumb =
  img [ src (urlPrefix ++ thumb.url)
      , classList [ ("selected", selectedUrl == thumb.url) ]
      ..
      ] []
```
```terminal
<function>
    : String -> { a | url : String } -> Html { data : String, description : String }
```
```elm
-- A partial application, or a curried function
viewThumbnail "1.jpeg"
```
```terminal
<function>
    : { a | url : String } -> Html { data : String, description : String }
```
