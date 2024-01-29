<!-- Front of card ===========================================================

    Missing! Card Data

    - Type:
        A question with a [missing] word;

        - A missing function or expression you have to guess,
        - A missing input or output to remember.

    - Docs:
        http://tinyurl.com/anki-missing-card

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
# How would we write the type annotation for `photoArray`?


<!-- -------------------------------------------------------------------------
    ☆ Subtitle

    ⤷ `string` (auto wrapped with a `H2` tag)
-------------------------------------------------------------------------- -->
## Types


<!-- -------------------------------------------------------------------------
    ☆ Syntax (inline code)

    ⤷ `code string` (auto wrapped with <p><code> tag)
-------------------------------------------------------------------------- -->
`Array.fromList`


<!-- -------------------------------------------------------------------------
    ★ Key point (code block or image)

    ⤷ `pre block | image`

      | Requires `markdown` fenced code block;
      | Requires `{{c1::cloze}}` tag(s))

      A markdown fenced code block that will compile to our highlighted
      code with Pandoc. Make sure to add at least one cloze deletion:

        `{{c1::the answer::HINT TEXT}}`

      Here's an example cloze card:

        @ https://codepen.io/testuser-247585903/pen/BabRjvb

      You can add cloze deletion tags to the fenced code block and
      they should work fine in Anki. You can also:

      1. `Toggle HTML Editor ⌘⇧X` (`‹›`) to enable rich text preview
      2. Highlight the text that you'd like to convert to a cloze.
      3. Press the `[...]` or `[...]+` button to add the cloze deletion
-------------------------------------------------------------------------- -->
```elm
import Array exposing (Array)

type alias Photo =
  { url : String }

initialModel : Model
initialModel =
  { photos =
    [ { url = "1.jpeg" }
    , { url = "2.jpeg" }
    ]
  ...
  }

photoArray : Array Photo
photoArray =
  Array.fromList initialModel.photos
```
```terminal
> photoArray
Array.fromList [{ url = "1.jpeg" },{ url = "2.jpeg" }]
    : Array { url : String }
```


<!-- -------------------------------------------------------------------------
    ★ Key point notes

    ⤷ `rich html`
-------------------------------------------------------------------------- -->
Just like a list (`[]`), `Array` acts as a container for stuff. In this case, our "stuff" is a `Photo` type alias, which can also be read as a `List { url : String }`. We've created a shorthand for `Photo` so can write it as an `Array` (of) `Photo`.


<!-- -------------------------------------------------------------------------
    ✎ Other notes

    ⤷ `rich html`
-------------------------------------------------------------------------- -->
`Array` is different from a list. You can't take the index of a list, like `list[0]` (you'd use [`head`](https://package.elm-lang.org/packages/elm/core/latest/List#head) instead). `Array` is also better [at dealing with empty lists](https://package.elm-lang.org/packages/elm/core/latest/Array#get)!


<!-- -------------------------------------------------------------------------
    ✎ Markdown

    ⤷ `raw text`

      Do not add the compiled HTML to your card, rather, use the raw text
      Markdown fenced code block. This makes for easier editing of a card
      later on.

      Please be careful:

        Warning: remove all `{{c1:cloze}}` cloze deletion tags!

      If you save your card with cloze deletion tags in the `★ Markdown`
      field, Anki will throw an error, and you might not be able to save
      your card.
-------------------------------------------------------------------------- -->
false
