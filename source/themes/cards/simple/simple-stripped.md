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
# What's so special about a higher order function?


<!-- -------------------------------------------------------------------------
    ☆ Subtitle

    ⤷ `string` (auto wrapped with a `H2` tag)
-------------------------------------------------------------------------- -->
## Higher order functions


<!-- -------------------------------------------------------------------------
    ☆ Syntax (inline code)

    ⤷ `code string` (auto wrapped with <p><code> tag)
-------------------------------------------------------------------------- -->
`List.map`


<!-- -------------------------------------------------------------------------
    ★ Sample (code block or image)

    ⤷ `pre block | image`

      | Requires `markdown` fenced code block;

      A markdown fenced code block that will compile to our highlighted
      code with Pandoc. What does this code do?
-------------------------------------------------------------------------- -->
```elm
guardians = [ "Star-lord", "Groot", "Gamora", "Drax", "Rocket" ]
-- Cycle through the list
List.map String.length guardians
-- [9,5,6] : List Int
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
-- Store our Guardian's lengths in a variable
lengths = List.map String.length guardians
-- Now let's get the lengths that are less than 6!
-- Remember, everything in `()` is an ANONYMOUS function
List.filter (\x -> x < 6) lengths
-- [5] : List Int
```


<!-- -------------------------------------------------------------------------
    ★ Key point notes

    ⤷ `rich html`
-------------------------------------------------------------------------- -->
Higher order functions _take a function_ as one of their arguments.

- `List.map`cycles through the list
- For every cycle it calls `function`
- When it's done, `List.map` outputs another list!


<!-- -------------------------------------------------------------------------
    ✎ Other notes

    ⤷ `rich html`
-------------------------------------------------------------------------- -->
`List.map` and `List.filter` are both examples of **Higher Order Functions**. These are functions **that take other functions as arguments**.Some more examples in [Elm lang](https://learnyouanelm.github.io/pages/06-higher-order-functions.html), and [Racket lang](https://beautifulracket.com/appendix/glossary.html#higher-order-function)


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
guardians = [ "Star-lord", "Groot", "Gamora", "Drax", "Rocket" ]
-- Cycle through the list
List.map String.length guardians
-- [9,5,6] : List Int
```
```elm
-- Store our Guardian's lengths in a variable
lengths = List.map String.length guardians
-- Now let's get the lengths that are less than 6!
-- Remember, everything in `()` is an ANONYMOUS function
List.filter (\x -> x < 6) lengths
-- [5] : List Int
```
