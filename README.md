# SF Symbols Finder

<p align="center">
  <img src="assets/logo.png" alt="SF Symbols Finder icon" width="160">
</p>

A small Agent Skill that helps agents find better SF Symbols for your app UIs on Apple platforms.

* Uses semantic search instead of just static SF Symbol names
* Chooses the best symbol from multiple search results
* Rephrases the search prompt until it finds a match
* Makes sure symbols are compatible with your app's minimum target

## Requirement

Install [SF Symbols 27](https://developer.apple.com/design/resources/) on your Mac. The skill uses its bundled `sfsymbols` CLI.

## Install

```sh
npx skills add mykolaharmash/sf-symbols-finder-skill --skill sf-symbols-finder
```

Once installed, compatible agents should pick up the skill automatically when working on SF Symbols-related tasks.

## Check also 👇

* [Notelet](https://github.com/mykolaharmash/notelet) — SwiftUI package for showing rich release notes in iOS apps.
* [AppView](https://appview.dev) – Website template for iOS apps
