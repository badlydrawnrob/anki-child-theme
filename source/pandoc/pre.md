<!-- Front of card =============================================================

    - Type:
        What's the answer?
        A simple question->answer card; we're asking the question: "what does this code do?", e.g:

        - A function with an output you have to guess.
        - A class with a method that you need to call.

    - Docs:
        https://github.com/badlydrawnrob/anki/tree/master/source/docs/simple/index.md

    - Key:
        ★ Required
        ☆ Optional (recommended)
        ✎ Optional (notes, markdown)
        ⤷ Field Type

============================================================================ -->


<!-- ---------------------------------------------------------------------------
     ★ Title: ⤷ `string` (auto wrapped with a `H1` tag)
---------------------------------------------------------------------------- -->
# In this example, `viewThumbnail` only takes one argument; `model.selectedUrl`. Yet, it still works! Explain why.


<!-- ---------------------------------------------------------------------------
     ☆ Subtitle: ⤷ `string` (auto wrapped with a `H2` tag)
---------------------------------------------------------------------------- -->
## A partial function


<!-- ☆ Syntax (inline code): ⤷ `code string` (auto wrapped with <p><code> tag) -->
Already wrapped in a `<p><code>` tag. A one liner: Some very short text for syntax.


<!-- ★ Sample (code block or image): ⤷ `pre block | image` -->
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
```


<!-- Back of card ============================================================== -->


<!-- ★ Key point (code block or image): ⤷ `pre block | image` -->
```elm
viewThumbnail selectedUrl thumb =
  img [ src (urlPrefix ++ thumb.url)
      , classList [ ("selected", selectedUrl == thumb.url) ]
      ..
      ] []
```


<!-- ★ Key point notes: ⤷ `rich html` -->

This is a big chunk of code!!! It's quite simple though:

1. We _partially_ apply `viewThumbnail` passing only one argument (a `"string"`)
2. `List.map` takes a function and a list
    - `model.photos` gives us a list of records
3. `List.map` cycles through the records


<!-- ✎ Other notes: ⤷ `rich html` -->

View the [full program](https://ellie-app.com/q4j6ps87Cj5a1) which consumes the function. Here's some [other curried function examples](https://www.codingexercises.com/guides/quickstart-elm-part-7) too.


<!-- ✎ Markdown: ⤷ `raw text` (commit this uncompiled!) -->

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
```
