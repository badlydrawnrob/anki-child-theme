<!-- Front of card ===========================================================

    Simple Card Data

    - Type:
        What's the answer?
        A simple question->answer card;
        we're asking the question: "what does this code do?", e.g:

        - A function with an output you have to guess.
        - A class with a method that you need to call.

    - Docs:
        http://tinyurl.com/anki-simple-card

    - Key:
        ★ Required
        ☆ Optional (recommended)
        ✎ Optional (notes, markdown)
        ⤷ Field Type

    - Notes:
        View compiled file in your text editor or a Chrome-type browser.
        The `## H2` titles represent Anki text fields, with the contents below.

========================================================================== -->


<!-- -------------------------------------------------------------------------
    ★ Title

    ⤷ `string` (auto wrapped with a `H1` tag)
-------------------------------------------------------------------------- -->
# Here `viewThumbnail` takes one argument; `model.selectedUrl`. Yet it should expect two. Why does this code still work?


<!-- -------------------------------------------------------------------------
    ★ Subtitle

    ⤷ `string` (auto wrapped with a `H2` tag)
-------------------------------------------------------------------------- -->
## ..


<!-- -------------------------------------------------------------------------
    ☆ Syntax (inline code)

    ⤷ `code string` (auto wrapped with <p><code> tag)
-------------------------------------------------------------------------- -->
Already wrapped in a `<p><code>` tag. A one liner: Some very short text for syntax.


<!-- -------------------------------------------------------------------------
    ★ Sample (code block or image)

    ⤷ `pre block | image`

      | Requires `markdown` fenced code block;

      A markdown fenced code block that will compile to our highlighted
      code with Pandoc. What does this code do?
-------------------------------------------------------------------------- -->
```elm
..

-- View --
view model =
  ..
    ..
    , div [ id "thumbnails" ]
        (List.map  -- Loop through list of url
          (viewThumbnail model.selectedUrl)  -- APPLY FUNCTION
          model.photos  -- list of `{ url = "1.jpeg" }`
        )
    ..

-- Helper functions --
..

viewThumbnail selectedUrl thumb =
  img [ src (urlPrefix ++ thumb.url)  -- urlPrefix = "http://link.com"
      , classList [ ("selected", selectedUrl == thumb.url) ]
      ..
      ] []
```


<!-- Back of card ======================================================== -->


<!-- -------------------------------------------------------------------------
    ★ Key point (code block or image)

    ⤷ `pre block | image`

      | Requires `markdown` fenced code block;

      A markdown fenced code block that will compile to our highlighted
      code with Pandoc. The output or answer to the above question.
-------------------------------------------------------------------------- -->
```elm
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
It's quite simple:

1. `viewThumbnail` gets partially applied (with one argument)
2. This is also called a **curried function**
3. `List.map` will pass `viewThumbnail` it's second argument


<!-- -------------------------------------------------------------------------
    ★ Other notes

    ⤷ `rich html`
-------------------------------------------------------------------------- -->
View the [full program](https://ellie-app.com/q4j6ps87Cj5a1) which consumes the function. [Here's what `List.map` does](https://elmprogramming.com/list.html#mapping-a-list). Here's some [other curried function examples](https://www.codingexercises.com/guides/quickstart-elm-part-7).


<!-- -------------------------------------------------------------------------
    ★ Markdown

    ⤷ `raw text`

      Do not add the compiled HTML to your card, rather, use the raw text
      Markdown fenced code block. This makes for easier editing of a card
      later on.

      Warning: may increase card file size
        @ https://github.com/badlydrawnrob/anki/issues/116
-------------------------------------------------------------------------- -->
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
