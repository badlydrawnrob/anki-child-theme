---
title:
  Missing! Card Data
card type: |
  A question with a [missing] word;
  - A missing function or expression you have to guess,
  - A missing input or output to remember.
card key: |
  ★ Required,
  ☆ Optional (recommended),
  ✎ Optional (notes, markdown),
  ⤷ Field Type.
docs:
  http://tinyurl.com/anki-missing-card
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

What kind of function do we call this? What will it output?


<!-- -------------------------------------------------------------------------
    ☆ Subtitle

    ⤷ `string` (auto wrapped with a `H2` tag)
-------------------------------------------------------------------------- -->
## ☆ Subtitle

What do we call this?


<!-- -------------------------------------------------------------------------
    ☆ Syntax (inline code)

    ⤷ `code string` (auto wrapped with <p><code> tag)
-------------------------------------------------------------------------- -->
## ☆ Syntax (inline code)

`(aDifferentAdder num)`


<!-- -------------------------------------------------------------------------
    ★ Key point (code block or image)

    ⤷ `code block | image`

      | Requires `markdown` fenced code block;
      | Requires `{{c1::cloze}}` tag(s))

      A markdown fenced code block that will compile to our highlighted
      code with Pandoc. Once you've compiled your code block, be sure to
      add at least one cloze deletion in your Anki card:

        `{{c1::the answer::HINT TEXT}}`

      Here's an example cloze card:

        @ https://codepen.io/testuser-247585903/pen/BabRjvb

      Here's how to do it in the Anki editor:

      1. `Toggle HTML Editor ⌘⇧X` (`‹›`) to enable rich text preview
      2. Highlight the text that you'd like to convert to a cloze.
      3. Press the `[...]` or `[...]+` button to add the cloze deletion
-------------------------------------------------------------------------- -->
## ★ Key point (code block or image)


```elm
-- This is called a {{c1::curried}} function
aDifferentAdder num = ((*) num)
-- <function> : number -> number -> number
aDifferentAdder 2
-- What will be returned?
```
```terminal
{{c1::<function> : number -> number}}
```
```elm
-- Here we're applying the {{c1::curried}} function
timesByTwo num = aDifferentAdder 2 num
-- <function> : number -> number
timesByTwo 5
-- 10 : number
```


<!-- -------------------------------------------------------------------------
    ★ Key point notes

    ⤷ `rich html`
-------------------------------------------------------------------------- -->
## ★ Key point notes

This is called a **curried function**, or a **partially applied function**. You could also read the procedure output like this `<function> : (number -> number) -> number`; the first two numbers return the output number.

Our partially applied function is given the first number, not the second. We can apply this function _later_ by giving it the second value!


<!-- -------------------------------------------------------------------------
    ✎ Other notes

    ⤷ `rich html`
-------------------------------------------------------------------------- -->
## ✎ Other notes

But _why_ is this useful, I hear you ask? [Here's some examples](https://www.codingexercises.com/guides/quickstart-elm-part-7).


<!-- -------------------------------------------------------------------------
    ✎ Markdown

    ⤷ `raw text`

      Do not add the compiled HTML to your card, rather, use the raw text
      Markdown fenced code block. This makes for easier editing of a card
      later on.

      Please be careful:

        Warning: remove all `{{c1:cloze}}` cloze deletion tags!

      If you save your card with cloze deletion tags in the `✎ Markdown`
      field, Anki will throw an error, and you might not be able to save
      your card.
-------------------------------------------------------------------------- -->
## ✎ Markdown

```elm
-- This is called a {{c1::curried}} function
aDifferentAdder num = ((*) num)
-- <function> : number -> number -> number
aDifferentAdder 2
-- What will be returned?
```
```terminal
{{c1::<function> : number -> number}}
```
```elm
-- Here we're applying the {{c1::curried}} function
timesByTwo num = aDifferentAdder 2 num
-- <function> : number -> number
timesByTwo 5
-- 10 : number
```

<!-- End of card ==========================================================-->
