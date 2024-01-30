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
# We have a `Msg` and `viewThumbnail` and our `onCLick` event calls the `ClickedPhoto` type variant (which looks like a function). What happens next?


<!-- -------------------------------------------------------------------------
    ☆ Subtitle

    ⤷ `string` (auto wrapped with a `H2` tag)
-------------------------------------------------------------------------- -->
## Types


<!-- -------------------------------------------------------------------------
    ☆ Syntax (inline code)

    ⤷ `code string` (auto wrapped with <p><code> tag)
-------------------------------------------------------------------------- -->
`Msg`


<!-- -------------------------------------------------------------------------
    ★ Sample (code block or image)

    ⤷ `pre block | image`

      | Requires `markdown` fenced code block;

      A markdown fenced code block that will compile to our highlighted
      code with Pandoc. What does this code do?
-------------------------------------------------------------------------- -->
```elm
type Msg
  = ClickedPhoto String
  | GotSelectedIndex Int
  | ClickedSize ThumbnailSize
  | ClickedSurpriseMe

viewThumbnail : String -> Photo -> Html Msg
viewThumbnail selectedUrl thumb =
  img [ ...
      -- #1a: Click event creates a `Msg`
      , onClick (ClickedPhoto thumb.url)  -- "1.jpeg"
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
-- Update takes a `Msg`,
-- Runs a `case` expression for each branch
-- And returns a tuple of `Model, Cmd Msg`
update : Msg -> Model -> ( Model, Cmd Msg)
update msg model =
  case msg of
    GotSelectedIndex index ->
      ...
    ClickedSize size ->
      ...
      -- #1b: Change `selectedUrl` in our `Model` ...
    ClickedPhoto url ->
      ( { model | selectedUrl = url }, Cmd.none )
      -- ... And continue with our branches
    ClickedSurpriseMe ->
      ...
```


<!-- -------------------------------------------------------------------------
    ★ Key point notes

    ⤷ `rich html`
-------------------------------------------------------------------------- -->
We can **destructure** our type variant by using `case`. Our `update` function takes a `Msg` from our `onClick` event which looks like `(ClickedPhoto thumb.url)` — a `ClickedPhoto String`.

We simply set our `Model` record (passed through to the parameter `model`) to reset the `selectedUrl` to the image that we've just clicked!

<!-- -------------------------------------------------------------------------
    ✎ Other notes

    ⤷ `rich html`
-------------------------------------------------------------------------- -->
Here's [a simpler version of `case` expression](https://github.com/badlydrawnrob/elm-playground/blob/fd8bcb29bc0c6fc345b8dbc51b6dd16a7d95d33a/elm-in-action/03/src/PhotoGroove.elm#L125-L133) with just a `Msg` (no commands)

<!-- -------------------------------------------------------------------------
    ✎ Markdown

    ⤷ `raw text`

      Do not add the compiled HTML to your card, rather, use the raw text
      Markdown fenced code block. This makes for easier editing of a card
      later on.

      Warning: may increase card file size
        @ https://github.com/badlydrawnrob/anki/issues/116
-------------------------------------------------------------------------- -->
false
