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
# What do we call this?


<!-- -------------------------------------------------------------------------
    ☆ Subtitle

    ⤷ `string` (auto wrapped with a `H2` tag)
-------------------------------------------------------------------------- -->
## Types


<!-- -------------------------------------------------------------------------
    ☆ Syntax (inline code)

    ⤷ `code string` (auto wrapped with <p><code> tag)
-------------------------------------------------------------------------- -->
false


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
```terminal
type {{c1::alias}} User =
  { name : String
  , age : Int
  }

isOldEnoughToVote : User -> Bool
isOldEnoughToVote user =
  user.age >= 18

isOldEnoughToVote { name = "Heather", age = 32 }
```
```terminal
True
```


<!-- -------------------------------------------------------------------------
    ★ Key point notes

    ⤷ `rich html`
-------------------------------------------------------------------------- -->
1. Our compiler will complain if `isOldEnoughToVote` receives anything other than a `User`.
2. Our `{ record }` must be formatted the same as our `type alias`!
3. Our `User` type alias means we can avoid repetition.
4. Whenever we need to add a type annotation, we can replace a record with `User`.

A `type alias` declaration assigns a name to a type, much as a constant assigns a name to a value. It also means we need fewer `-- comments` to explain what our code does. With well named Types and functions, it's easier to reason about.


<!-- -------------------------------------------------------------------------
    ✎ Other notes

    ⤷ `rich html`
-------------------------------------------------------------------------- -->
More examples of `type alias` [can be found here](https://guide.elm-lang.org/types/type_aliases). See also **[Record constructors](https://guide.elm-lang.org/types/type_aliases#record-constructors)**.


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
```elm
type alias User =
  { name : String
  , age : Int
  }

isOldEnoughToVote : User -> Bool
isOldEnoughToVote user =
  user.age >= 18

isOldEnoughToVote { name = "Heather", age = 32 }
```
```terminal
True
```
