---
title: Simple Card data
---


## ★ Title

Will this return `True` or `False`?


## ☆ Subtitle

Comparison


## ☆ Syntax (inline code)

== ++


## ★ Sample (code block or image)

```elm
walkies = "taking a walk " ++ "with the dog. The time is"

walkies == 11
```


## ★ Key point (code block or image)

```terminal
-- TYPE MISMATCH ---------------------------------------------------------- REPL

I need both sides of (==) to be the same type:

4|   walkies == 11
     ^^^^^^^^^^^^^
The left side of (==) is:

    String

But the right side is:

    number

Different types can never be equal though! Which side is messed up?

Hint: Try using String.toInt to convert it to an integer?
```


## ★ Key point notes

1. The `++` concatonates strings (and only strings)
2. The `==` comparison operator compares values
    - These values **must** be the same type!



## ✎ Other notes

See on [Beginning Elm](https://elmprogramming.com/comparison.html)


## ✎ Markdown

false
