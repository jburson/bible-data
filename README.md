# bible-data
JSON formatted data for building innovative Bible apps. Use with permission of the copyright holders.

### Versions Included
- CSB
- ESV
- KJV
- NASB
- NIV
- NKJV

## Bible Text
- Filename: `data/VERSION/VERSION.json`.
- Properties of each item:
  - `o`: (number) The order number of the item, starting with 1.
  - `r`: (string) The reference, including the version, book, chapter, and verse. Example: `csb:Genesis:1:1`. 
  - `h`: (number) The header size of section titles (1 through 4). 
  - `t`: (string) The text of the verse or title.
    - If a word contains a `*`, then all following characters indicate features of that word.
      - `p` - Start a new paragraph.
      - `l` - Start a new line.
      - `n` - Start a new indented line.
      - `d` - Start a new doubly-indented line.
      - `c` - Start a new centered line.
      - `g` - Start a new right-aligned line.
      - `e` - Start a new left-aligned line.
      - `s` - Render with smallcaps.
      - `i` - Render with italics.
      - `b` - Render with bold.
      - `r` - Render as a redletter word of Christ.
    - For example, a verse text might be: `For*pn the Lord*s watches over the way of the righteous, but*ln the way of the wicked leads to ruin.`
      - The first word (`For`) should start a new paragraph and be indented.
      - The third word (`Lord`) should be rendered with smallcaps.
      - The eleventh word (`but`) should start a new line and be indented.

## Bible Footnotes
- Filename: `data/VERSION/VERSION-footnotes.json`.
- Properties of each item:
  - `o`: (number) The order number of the corresponding item in `VERSION.json`, starting with 1.
  - `r`: (string) The reference, including the version, book, chapter, and verse. Example: `csb:Genesis:1:1`.
  - `t`: (string) The text of the footnote.
    - If a word contains a `*`, then all following characters indicate features of that word.
      - `r` - Indicates that the word is a cross-reference.
      - `i` - Render with italics.
    - For example, a footnote text might be `2:2*r Or anointed one`.
      - The first word is a cross-reference that can be linked be `2:2` within the current book.
  - `w`: (number) The word index within the verse (starting at 0).
  - `c`: (string) Cross-references.
    - Each cross-reference is separated by `;`.
    - If a cross-reference contains a `*`, then the following number indicates the order number of the link corresponding to `VERSION.json`.  
  - `a`: (string) A title that can be used to render the footnote (`a`, `b`, `c`, etc).

## Interlinear
- Strongs filename: `data/interlinear/strongs.json`.
- Interlinear filename: `data/VERSION/VERSION-interlinear.json`.
