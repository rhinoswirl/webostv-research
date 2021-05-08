# TV Input Embedding

It is possible to embed live TV content in webOS applications as a HTML 5 video source.

The following code snippet allows the embed of the live feed of the HDMI 1 input:

```
<video autoplay style="width:50%; height:50%">
  <source type="service/webos-external" src="ext://hdmi:1"></source>
</video>
```

## List of options

Below is a list of accepted values for `type` and `src` based on the source input:

| Source to embed       | type                    | src          |
|-----------------------|-------------------------|--------------|
| DTV                   | service/webos-broadcast | tv://        |
| HDMI 1                | service/webos-external  | ext://hdmi:1 |
| HDMI 2                | service/webos-external  | ext://hdmi:2 |
| HDMI 3                | service/webos-external  | ext://hdmi:3 |
| HDMI 4                | service/webos-external  | ext://hdmi:4 |
| Composite / Component | service/webos-external  | ext://comp:1 |
| AV1                   | service/webos-external  | ext://av:1   |
| AV2                   | service/webos-external  | ext://av:2   |


## Compatibility

| Platform   | Compatibilty | Notes |
|------------|--------------|-------|
| Browser    | ?            | -     |
| Web App    | √            | -     |
| Native App | ?            | -     |

## Notes

[@Informatic](https://gist.github.com/Informatic/1983f2e501444cf1cbd182e50820d6c1), webOS 3.8: 
>Only a single external input can be displayed at the same time.


## See also

- [Controlling the TV](controlling-tv.md)
