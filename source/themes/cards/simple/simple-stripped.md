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
# Here's an example of a simple `record`. How do we change the name?


<!-- -------------------------------------------------------------------------
    ☆ Subtitle

    ⤷ `string` (auto wrapped with a `H2` tag)
-------------------------------------------------------------------------- -->
## Record


<!-- -------------------------------------------------------------------------
    ☆ Syntax (inline code)

    ⤷ `code string` (auto wrapped with <p><code> tag)
-------------------------------------------------------------------------- -->
`{ name = "string" }`


<!-- -------------------------------------------------------------------------
    ★ Sample (code block or image)

    ⤷ `pre block | image`

      | Requires `markdown` fenced code block;

      A markdown fenced code block that will compile to our highlighted
      code with Pandoc. What does this code do?
-------------------------------------------------------------------------- -->
```elm
steve = { name = "Wozniak" }  -- Change me!
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
-- Change me!
{ steve | name = "Jobs" }
-- { name = "Jobs" } : { name : String }
steve
-- { name = "Wozniak" } : { name : String }
```


<!-- -------------------------------------------------------------------------
    ★ Key point notes

    ⤷ `rich html`
-------------------------------------------------------------------------- -->
The `|` pipe operator is how we "change" the name of our record. Records are **immutable**, so it doesn't really _change_ it, but returns a **new** record!


<!-- -------------------------------------------------------------------------
    ✎ Other notes

    ⤷ `rich html`
-------------------------------------------------------------------------- -->
View the [full program](https://ellie-app.com/q4j6ps87Cj5a1) which consumes the function. [Here's what `List.map` does](https://elmprogramming.com/list.html#mapping-a-list). Here's some [other curried function examples](https://www.codingexercises.com/guides/quickstart-elm-part-7).


<!-- -------------------------------------------------------------------------
    ✎ Markdown

    ⤷ `raw text`

      Do not add the compiled HTML to your card, rather, use the raw text
      Markdown fenced code block. This makes for easier editing of a card
      later on.

      Warning: may increase card file size
        @ https://github.com/badlydrawnrob/anki/issues/116
-------------------------------------------------------------------------- -->
```elm
..
div [ id "thumbnails" ]
        (List.map -- viewThumbnail string record
          (\photo -> viewThumbnail model.selectedUrl photo)
          model.photos  -- List of `{ url = "1.jpeg" }`
        )
..
```
```elm
(List.map
  (viewThumbnail model.selectedUrl) -- Use a CURRIED function!
    model.photos
)
```
