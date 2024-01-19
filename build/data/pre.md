This is a big chunk of code!!! It's quite simple though:

1.  We *partially* apply `viewThumbnail` passing only one argument (a
    `"string"`)
2.  `List.map` takes a function and a list
    -   `model.photos` gives us a list of records
3.  `List.map` cycles through the records
4.  Each cycle calls the `viewThumbnail` function, **passing a record as
    the second argument**!
5.  Each cycle would look like this:
    -   `viewThumbnail "1.jpeg" { url = "2.jpeg" }`
    -   Each cycle would pass `viewThumbnail` a different record
6.  We now have a list of `img []`, each with it's own url!
7.  Our `viewThumbnail` function also checks the `model.selectedUrl`,
    and adds a `"selected"` class if it matches.
