[![License](https://img.shields.io/badge/licence-MIT-green.svg?style=flat)](LICENSE)
[![Wikipedia](https://img.shields.io/badge/Wikipedia-000000?style=flat&logo=wikipedia&logoColor=white)](https://en.wikipedia.org/wiki/Thor_Vector_Graphics)
[![Discord](https://img.shields.io/badge/Community-5865f2?style=flat&logo=discord&logoColor=white)](https://discord.gg/n25xj6J6HM)
[![OpenCollective](https://img.shields.io/badge/OpenCollective-84B5FC?style=flat&logo=opencollective&logoColor=white)](https://opencollective.com/thorvg)

# ThorVG CLI Tools

<p align="center">
  <img width="550" height="auto" src="https://github.com/thorvg/thorvg.site/blob/main/readme/logo/animated_brand.svg">
</p>

ThorVG CLI Tools is a collection of command-line utilities built on top of the ThorVG graphics engine. These tools provide simple and practical ways to render and convert vector graphics and animations directly from the command line.</br>
</br>
Currently available tools include:</br>
- **tvg-svg2png**: Converts SVG files to PNG images.</br>
- **tvg-lottie2gif**: Converts Lottie animations to GIF files.

## Build and Installation

The CLI tools require Meson, Ninja, a C++14-compatible compiler, and an installed ThorVG library.

To build all tools:

```sh
meson setup builddir
meson compile -C builddir
```

To install the built executables:

```sh
meson install -C builddir
```

## Lottie to GIF

> [!IMPORTANT] This tool requires ThorVG to be built with the **Lottie loader** and **GIF saver** enabled.

ThorVG provides an executable `tvg-lottie2gif` converter that generates a GIF file from a Lottie file.

To use the `tvg-lottie2gif`, you must turn on this feature in the build option:
```
meson setup builddir -Dtools=lottie2gif
```
The usage examples of the `tvg-lottie2gif`:
```
Usage:
    tvg-lottie2gif [Lottie file] or [Lottie folder] [-r resolution] [-f fps] [-b background color]

Flags:
    -r set the output image resolution.
    -f specifies the frames per second (fps) for the generated animation.
    -b specifies the base background color (RGB in hex). If not specified, the background color will follow the original content.

Examples:
    $ tvg-lottie2gif input.json
    $ tvg-lottie2gif input.json -f 30
    $ tvg-lottie2gif input.json -r 600x600 -f 30
    $ tvg-lottie2gif lottiefolder
    $ tvg-lottie2gif lottiefolder -r 600x600
    $ tvg-lottie2gif lottiefolder -r 600x600 -f 30 -b fa7410
```

## SVG to PNG

> [!IMPORTANT] This tool requires ThorVG to be built with the **SVG loader** enabled.

ThorVG provides an executable `tvg-svg2png` converter that generates a PNG file from an SVG file.

To use the `tvg-svg2png`, you must turn on this feature in the build option:
```
meson setup builddir -Dtools=svg2png
```
The usage examples of the `tvg-svg2png`:
```
Usage:
    tvg-svg2png [SVG files] [-r resolution] [-b bgColor]

Flags:
    -r set the output image resolution.
    -b set the output image background color.

Examples:
    $ tvg-svg2png input.svg
    $ tvg-svg2png input.svg -r 200x200
    $ tvg-svg2png input.svg -r 200x200 -b ff00ff
    $ tvg-svg2png input1.svg input2.svg -r 200x200 -b ff00ff
    $ tvg-svg2png . -r 200x200
```

[Back to contents](#contents)
<br />
