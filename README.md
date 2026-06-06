# messletters

Convert text into 121+ Unicode fancy text styles — math alphabets, scripts, symbols, decorative, encircled, runic, and more. Zero dependencies. Single file.

Extracted from [messletters.com](https://www.messletters.com/en/).

## Install

```bash
hermes skills install gwyntel/messletters/messletters
```

## Quick Start

```python
from messletters import convert, search_styles

# Convert text to a fancy style
convert("Hello World", "Math Sans-serif Bold")
# → 𝗛𝗲𝗹𝗹𝗼 𝗪𝗼𝗿𝗹𝗱

convert("Claire", "Circled")
# → ⓒⓛⓐⓘⓡⓔ

convert("Love you 3000", "Math Fraktur Bold")
# → 𝕃𝖔𝖛𝖊 𝖞𝖔𝖚 𝟯𝟬𝟬𝟬

# Search for styles
search_styles("fraktur")
# → ['Math Fraktur Bold', 'Math Fraktur Bold - Edit', 'Math Fraktur Normal', 'Math Fraktur Normal - Edit']
```

## API

### `convert(text: str, style: str) -> str`
Convert text to a named style. Non-ASCII characters pass through unchanged.

### `list_styles() -> list[str]`
All 121 style names, alphabetically sorted.

### `search_styles(query: str) -> list[str]`
Case-insensitive substring search on style names.

### `preview_styles(text: str = "Hello World") -> list[tuple[str, str]]`
Apply all styles to text. Returns list of `(style_name, converted_text)` tuples.

### `reverse_lookup(char: str) -> list[tuple[str, str]]`
Find which styles map a single ASCII character and what they produce.

### `CATEGORIES`
Dict of `category_name -> list[style_names]` for browsing by type.

### `STYLES`
Raw data dict: `style_name -> (lower_cps_tuple, upper_cps_tuple, digit_cps_tuple)`.

## Categories

- **mathematical** (17) — Math Script, Monospace, Sans-serif Bold, Fraktur, Serif variants
- **enclosed** (6) — Circled, Boxed, Parenthesized, Fullwidth
- **script_cursive** (14) — Lilia, Yas Script, Cute v1/v2/v3, Curly, Ribbon
- **gothic_runes** (5) — Runes, Gothic, Celtic, Black Panther, Etruscan
- **asian_scripts** (14) — Japanese, CJK, Yi variants, Malayalam, Cherokee Mystique
- **decorative** (18) — Messletters, Swirly, Wiggly, Dotted, Strange, Phonetic
- **leetspeak** (1) — 1337
- **regional_scripts** (23) — Greek, Russian, Armenian, Turkish, Vietnamese, African
- **effects** (3) — Strikethrough, Flip
- **fancy_mixed** (20) — Classic, Smooth, Palaeotype, DraKo, Hazy, Love, Twisted

## Sample Output

Input: `Claire`

- **Math Sans-serif Bold:** 𝗖𝗹𝗮𝗶𝗿𝗲
- **Fullwidth:** Ｃｌａｉｒｅ
- **Circled:** ⓒⓛⓐⓘⓡⓔ
- **Circled Black:** 🅒🅛🅐🅘🅡🅔
- **Math Fraktur Bold:** 𝕮𝖑𝖆𝖎𝖗𝖊
- **Math Script (Royal):** 𝒞𝓁𝒶𝒾𝓇𝑒
- **Math Monospace:** 𝙲𝚕𝚊𝚒𝚛𝚎
- **Parenthesized:** ⒞⒧⒜⒤⒭⒠

## Notes

- Non-ASCII characters (punctuation, spaces, emoji) pass through unchanged
- Some styles are **unicase** (upper=lower) — e.g., Japanese, Boxed Black, Runes
- Digits don't map in all styles — they pass through as ASCII
- Strikethrough styles use combining characters — rendering depends on platform/font
- `1337` is a leetspeak substitution cipher (a→4, e→3, i→1, o→0, s→5, t→7, z→2)

## License

MIT © 2026 GwynTel
