---
title:
  Simple Card Data
card type: |
  A simple `question->answer` card;
  we're asking the question: "what does this code do?", e.g:

  - A function with an output you have to guess,
  - A class with a method that you need to call.
card key: |
  ★ Required,
  ☆ Optional (recommended),
  ✎ Optional (notes, markdown),
  ⤷ Field Type.
docs:
  http://tinyurl.com/anki-simple-card
notes:
  View compiled file in your text editor or a Chrome-type browser.
  The `## H2` titles represent Anki text fields, with the contents below.
css: ../../node_modules/anki/build/style/main.css
---


<!-- -------------------------------------------------------------------------
    ★ Title

    ⤷ `string` (auto wrapped with a `H1` tag)
-------------------------------------------------------------------------- -->
## ★ Title

In this example, `viewThumbnail` only takes one argument; `model.selectedUrl`. Yet, it still works! Explain why.


<!-- -------------------------------------------------------------------------
    ☆ Subtitle

    ⤷ `string` (auto wrapped with a `H2` tag)
-------------------------------------------------------------------------- -->
## ☆ Subtitle

A partial function


<!-- -------------------------------------------------------------------------
    ☆ Syntax (inline code)

    ⤷ `code string` (auto wrapped with <p><code> tag)
-------------------------------------------------------------------------- -->
## ☆ Syntax (inline code)

`(viewThumbnail selectedUrl thumb)`


<!-- -------------------------------------------------------------------------
    ★ Sample (code block or image)

    ⤷ `code block | image`

      | Requires `markdown` fenced code block;

      A markdown fenced code block that will compile to our highlighted
      code with Pandoc. What does this code do?
-------------------------------------------------------------------------- -->
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


<!-- -------------------------------------------------------------------------
    ★ Key point (code block or image)

    ⤷ `code block | image`

      | Requires `markdown` fenced code block;

      A markdown fenced code block that will compile to our highlighted
      code with Pandoc. The output or answer to the above question.
-------------------------------------------------------------------------- -->
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


<!-- -------------------------------------------------------------------------
    ★ Key point notes

    ⤷ `rich html`
-------------------------------------------------------------------------- -->
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


<!-- -------------------------------------------------------------------------
    ✎ Other notes

    ⤷ `rich html`
-------------------------------------------------------------------------- -->
## ✎ Other notes

View the [full program](https://ellie-app.com/q4j6ps87Cj5a1) which consumes the function. Here's some [other curried function examples](https://www.codingexercises.com/guides/quickstart-elm-part-7) too.


<!-- -------------------------------------------------------------------------
    ✎ Markdown

    ⤷ `raw text`

      Do not add the compiled HTML to your card, rather, use the raw text
      Markdown fenced code block. This makes for easier editing of a card
      later on.

      Warning: may increase card file size
        @ https://github.com/badlydrawnrob/anki/issues/116
-------------------------------------------------------------------------- -->
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

<!-- End of card ==========================================================-->
