<p align="center">
  <img src="https://raw.githubusercontent.com/razekmh/manim-arabic/main/assets/logo.svg" alt="manim-arabic logo" width="160">
</p>

# manim-arabic

Arabic text rendering helpers for [Manim](https://www.manim.community/) using XeLaTeX and `fontspec`.

## Install

```bash
pip install manim-arabic
```

Or with uv:

```bash
uv add manim-arabic
```

## Requirements

Besides Python dependencies, you need:

- **XeLaTeX** (via TeX Live, MacTeX, or MiKTeX)
- An Arabic-capable font installed on your system, for example:
  - `Al Bayan` (macOS)
  - `Geeza Pro` (macOS)
  - `Arial Unicode MS` (cross-platform)

## Usage

```python
from manim import Scene, Write
from manim_arabic import create_arabic_text


class ArabicExample(Scene):
    def construct(self):
        label = create_arabic_text("مرحبا", color="arabicblue", font_size=48)
        self.play(Write(label))
        self.wait()
```

### API

- `create_arabic_text(text, color="arabicblue", font_size=34, font_name="Al Bayan")` — returns a Manim `Tex` mobject
- `create_arabic_template(font_name="Al Bayan")` — returns a configured `TexTemplate` if you need lower-level control

### Built-in colors

These LaTeX color names are predefined in the template:

| Name | RGB |
|------|-----|
| `arabicblue` | `(68, 114, 196)` |
| `arabicgreen` | `(112, 173, 71)` |
| `arabicred` | `(192, 0, 0)` |

You can also pass any color name supported by `xcolor`.
