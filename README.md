# SF Symbols Finder

A small [Agent Skill](https://agentskills.io/) that helps coding agents find fitting SF Symbols for Apple-platform apps using SF Symbols 27's semantic search through Apple's CLI.

## Requirement

Install [SF Symbols 27 or newer from Apple](https://developer.apple.com/design/resources/) on your Mac. The skill uses its bundled CLI at `/Applications/SF Symbols.app/Contents/Executables/sfsymbols`.

## Install

```sh
npx skills add mykolaharmash/sf-symbols-finder-skill --skill sf-symbols-finder
```

Once installed, compatible agents should pick up the skill automatically when working on SF Symbols related tasks.
