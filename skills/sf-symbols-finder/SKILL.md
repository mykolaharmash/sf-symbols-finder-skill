---
name: sf-symbols-finder
description: Find and verify SF Symbols for Apple-platform app interfaces using the SF Symbols CLI's semantic search. Use when choosing an icon or replacing an unclear symbol.
---

# SF Symbols Finder

Use the CLI bundled with SF Symbols 27 or newer. This is a requirement for searching on the Mac, not a minimum deployment target for the app being built. If the CLI is missing, direct the user to [download SF Symbols from Apple](https://developer.apple.com/design/resources/).

```sh
sf_symbols_cli="/Applications/SF Symbols.app/Contents/Executables/sfsymbols"
```

## Find candidates

The default `search` uses semantic search. Describe the meaning of the interface element in ordinary words, even if those words do not appear in a symbol's name. Limit the shortlist, then compare meaning and appearance rather than automatically choosing the first result. Use `--show-glyph` when the terminal can display SF Symbols.

```sh
"$sf_symbols_cli" search --limit 10 --show-glyph "celebrate achievement"
"$sf_symbols_cli" search --limit 10 "save for later"
"$sf_symbols_cli" search --limit 10 "protect privacy"
```

On SF Symbols 27, these find `party.popper`, `bookmark`, and several lock or shield symbols, respectively. If a query returns nothing useful, try shorter descriptions, the underlying object or action, and synonyms. Keep searching until you find a relevant candidate; do not settle for an unrelated result or invent a symbol name.

## Check compatibility

Filter for every platform's minimum deployment version, then inspect the JSON availability for the rendering mode the app uses. Replace these example versions with the project's actual targets:

```sh
"$sf_symbols_cli" search --limit 10 --json --min-platform iOS16 --min-platform macOS13 "protect privacy"
```

Use the returned `name` in app code. A filtered result may contain a historical `name` and a newer `modernName`; the historical name is the one available on the requested older OS. If no suitable built-in symbol exists after rephrasing, say so.
