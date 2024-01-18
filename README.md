---
title: Anki Child Theme
---

An extension of [Anki programming theme](https://github.com/badlydrawnrob/anki)

## Important files

> Make sure you've run `npm run build` first!

- **Demo:**
    - [`simple.html`](../node_modules/anki/build/demo/simple.html)
    - [`missing.html`](../node_modules/anki/build/demo/missing.html)
- **Documentation**
    - [Simple](https://github.com/badlydrawnrob/anki/blob/master/source/docs/highlight/index.md) card
    - [Missing!](https://github.com/badlydrawnrob/anki/blob/master/source/docs/missing/index.md) card
    - [Add color to your code](https://github.com/badlydrawnrob/anki/blob/master/source/docs/highlight/index.md)
    - 🧑‍🎓 [The professional way](https://github.com/badlydrawnrob/anki/blob/master/source/docs/advanced/index.md) (advanced documentation)
- **Anki Card `HTML` templates** (for the Anki app)
    - `node_modules/anki/source/themes/cards/simple/*.moustache`
    - `node_modules/anki/source/themes/cards/missing/*.moustache`
- **Anki `CSS` files** (for the Anki app)
    - `node_modules/anki/source/style/modules/*.less`
    - `node_modules/anki/source/style/partials/*.less`

## Compiling the card data

> 🚀 All systems go!

1. For the default compiler
    - `npm run pandoc`
2. For [the stripped down](https://github.com/badlydrawnrob/anki-child-theme/issues/9) compiler[^1]
    - Add a little more code to `package.json`
    - `npm run pandoc-stripped`


[^1]: The stripped down version compiles a lot less code, so is easier to read. This comes with the trade off that it doesn't look as pretty in the browser (for instance, the code highlighting `.classes` will be added, but you won't be able to preview it in the browser).
