# Query String

## Structure

No standardised structure, but conventionally

```
https://example.com/pokemon/page?type=fire&level=1

```

- composed of a series of field-value pairs
- field and value separated by `=`
- series of pairs separated by `&` (or semicolon `;` for URLs embedded in HTML and not generated by a `<form>...</form>`)

## URL Encoding

Some characters cannot be part of a URL (for example, the space) some other characters have a special meaning in a URL,e .g, `#` can be used to further specify a subsection

HTML5 Specifications:

- Characters that cannot be converted to the correct charset are replaced with HTML [numeric character references](https://en.wikipedia.org/wiki/Numeric_character_reference)
- SPACE is encoded as `+` or `%20`
- Letters `A-Z` `a-z`, numbers `0-9`, characters `~` `-` `.` and `_` are left as they are
- `+ ` is encoded as `%2B`
- All other characters are encoded as `%HH` [hexadecimal representation](https://en.wikipedia.org/wiki/Hexadecimal)

Reference:
<https://en.wikipedia.org/wiki/Query_string>