```elm
type Msg
  = ClickedPhoto String
  | ClickedSize ThumbnailSize
  | ClickedSurpriseMe

update : Msg -> Model -> ( Model, Cmd Msg)
update msg model =
  case msg of
    ClickedPhoto url ->
      ( { model | selectedUrl = url }, Cmd.none )
    ClickedSurpriseMe ->
      ( model, Random.generate GotSelectedIndex randomPhotoPicker )
```
```terminal
This `case` does not have branches for all possibilities:

151|>  case msg of
152|>    ClickedPhoto url ->
153|>      { model | selectedUrl = url }
154|>    ClickedSurpriseMe ->
155|>      { model | selectedUrl = "2.jpeg" }

I would have to crash if I saw one of those. Add branches for them!
```

