# smalltvstill

Select and send an area from your screen to the Geekmagic Ultra TV

## Dependencies

- KDE / Plasma running on wayland
- slurp
- jq
- graphicsmagick
- curl
- A [Geekmagic Ultra TV](https://github.com/GeekMagicClock/smalltv-ultra) or similar


## Usage


```bash
SMALLTV_URL=http://mysmalltv.home ./still
```

Will give you a rasterized selection (defaulting to 20 pixel steps) of 240 by
240 areas using slurp. Click on one and it will be sent to your smalltv.

```bash
SMALLTV_URL=http://mysmalltv.home ./still free
```

Will give you a freeform selection using spectacle. You should take care that
you select an area that roughly fits a 240x240 area.

"Tune" your TV to show the picture with the name *smalltvstill.jpg*.


## Quality

This is not high quality. Use it as a start for playing around.

I did not find any screenshotting tool that can do both, work on Plasma/Wayland
and capture a specific area that is pre-defined on the command line from the
screen. I tried:

- flameshot
- scrot
- spectacle
- grim
- maim
- magick import
- some AI slop that said it would work via dbus

I ended up doing a full screenshot using spectacle and crop that using
graphicsmagick. Not happy with it because it requires dealing with temporary
files and is much slower.

