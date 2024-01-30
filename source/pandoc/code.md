```elm
viewThumbnail selectedUrl thumb =
  img [ src (urlPrefix ++ thumb.url)
      , classList [ ("selected", selectedUrl == thumb.url) ]
      ..
      ] []
```

