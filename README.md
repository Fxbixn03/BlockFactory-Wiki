# BlockFactory – Translations and Wiki

BlockFactory is a factory-automation overhaul for Hytale, inspired by games like Factorio and Satisfactory.
The mod's source code is not public. This repository holds everything the community can work on: the
**translations** of all texts in the mod, and later the wiki.

Want to translate BlockFactory into your language? Read [CONTRIBUTING.md](CONTRIBUTING.md).

## Languages

| Language | Folder | Status | Maintained by |
| --- | --- | --- | --- |
| English | `en-US` | Reference, always complete | Mod author |
| German | `de-DE` | Complete | Mod author |

Missing your language? Start it! Partial translations are welcome: every line that is not translated yet
shows up in English in the game.

## Layout

```text
Languages/
  en-US/blockfactory.lang        English reference: every key exists here
  de-DE/blockfactory.lang        German
  <code>/blockfactory.lang       one folder per language
ExampleLanguages/
  example-EXAMPLE/blockfactory.lang   empty template for a new language
```

Each line of a `.lang` file is one text: `key = text`. Only the text after the `=` is translated.

## How translations reach the game

- BlockFactory shows its texts in the language selected in the Hytale client. A line that is missing in that
  language falls back to English.
- The mod includes this repository directly: every translation merged here ships with the next release.
- `en-US` is copied from the mod with each release and always describes the latest released version. All other
  languages, `de-DE` included, live only here.

## Translators

Thank you to everyone who helps! Add yourself in your pull request.

<!-- - French (fr-FR): @your-github-name -->

## License

This repository is licensed under the [MIT License](LICENSE). By contributing, you license your contribution
under the same terms (see [CONTRIBUTING.md](CONTRIBUTING.md#license)).
