# Contributing a translation

Thank you for helping to bring BlockFactory to more players! You don't need to know how to code. A text editor
and a GitHub account are enough.

## Ways to help

- **Start a new language**, see below.
- **Complete or improve** an existing translation: open a pull request that changes its file.
- **Report a mistake** in any language: open an issue with the key (the part before the `=`) and what is wrong.

`en-US` is copied from the mod with every release, so a pull request that changes it would be overwritten. For
English, please open an issue instead. All other languages, `de-DE` included, are edited right here.

## Before you start

Look at the open issues and pull requests: maybe someone is already working on your language. If not, open an
issue like `[fr-FR] French translation` so others know and can join you.

## Start a new language

1. Fork this repository: only the maintainer can push to it, so a pull request comes from your own copy. If you
   add or edit a file in the browser on GitHub, GitHub creates the fork for you.
2. Copy `ExampleLanguages/example-EXAMPLE/blockfactory.lang` to `Languages/<code>/blockfactory.lang`, for
   example `Languages/fr-FR/blockfactory.lang`.
3. Translate. The lines are in the same order as in `Languages/en-US/blockfactory.lang`, so you can open both
   side by side.
4. Delete every line you have not translated (see the rules below).
5. Add yourself to the list of translators in `README.md`.
6. Open a pull request. Partial translations are welcome, you can continue in a later pull request.

## Folder name

The folder name must be exactly the language code that the Hytale client uses, otherwise the game never
picks up your file.

- The format is `language-REGION`: two lowercase letters, a hyphen, two uppercase letters, for example
  `fr-FR`, `es-ES`, `pl-PL`, `pt-BR`.
- Upper and lower case matter: `fr-fr` does not work.
- Look up the code in the folder names of your Hytale client: `Client/Data/Shared/Language/` inside the
  Hytale installation (on Windows: `%AppData%\Hytale\install\release\package\game\latest\Client\Data\Shared\Language\`).
  If Hytale does not offer your language yet, use the code of the language pack for the Hytale client that
  players of your language use.

## Rules for the file

```text
# A comment
items.BF_Iron_Plate.name = Iron Plate
repair.done = {name} repaired to {percent} %.
```

- **Translate only the text after the `=`.** Never change the key before it.
- **Delete lines you don't translate.** A missing line falls back to the English text; don't leave a value
  empty. Don't add keys that `en-US` does not have.
- **Keep every placeholder in curly braces exactly as it is**, for example `{name}`, `{count}`, `{seconds}`.
  You may move it to wherever it fits in your sentence, but don't translate, rename or remove it. `{{` shows a
  single `{`.
- **Some placeholders choose between forms**, for example `{n, plural, one {# item} other {# items}}`. Translate
  only the words inside the inner braces and keep `n`, `plural`, `one`, `other`. You may add the plural forms
  your language needs (`few`, `many`).
- **Don't translate anything players have to type or that is code:**
  - commands and their options: `/blueprint --import=<name>`, `/tips --off`, `/armor --remove`,
    `/channel --to=all`, `/team`
  - the program language of the Programmable Interface in `circuit.help` and `circuit.placeholder`: `$name`,
    `out`, `if`, `elif`, `else`, `end`, `and`, `or`, `not` and the signal names `grabber`, `boiler`, `pump`,
    `stop`, `lamp`, `on`
  - `#RRGGBB` in `teams.hexPlaceholder`
- **Lines starting with `#` are comments.** A `\` at the very end of a line continues the text on the next line.
- **Save the file as UTF-8** without BOM.

## Style

- **Use the same word for the same thing** throughout the file. A short glossary as comments at the top of your
  file helps you and the next translator:

  ```text
  # Glossary: Belt = …, Grabber = …, Fabricator = …, Research = …
  ```

- **Where Hytale already has a term in your language**, use it.
- **Keep item and machine names short.** They appear in narrow lists and tooltips.
- **Keep tiers, units and numbers as they are:** `T1` to `T4`, `MK1` to `MK3`, `U-235`, `MJ`, `kW`, `MW`, `%`.
- **Short labels may be abbreviated the way your language does it**, for example the compass letters
  `minimap.north` to `minimap.west` (German uses `N`, `O`, `S`, `W`).
- **Story texts** (`terminal.record.*`, scenes, tips) may be translated freely. Keep the mood: the old world is
  gone, and it is quiet and a bit lonely.
- **Machine translation** is fine as a first draft, but please read and correct every line before you submit it.

## Updating a translation after a release

With every release the English file can change. To see what changed, open the history of
`Languages/en-US/blockfactory.lang` on GitHub, or compare it with git:

```sh
git diff <commit-of-your-last-update> -- Languages/en-US/blockfactory.lang
```

- Translate new lines.
- Update lines whose English text changed.
- Delete lines whose key no longer exists in `en-US`.

## Pull request checklist

- [ ] The folder is named exactly like the Hytale language code (`xx-XX`).
- [ ] Only the text after the `=` is translated; no key is changed or added.
- [ ] Untranslated lines are deleted, not left empty.
- [ ] Every placeholder `{…}` of the English line is still there.
- [ ] Commands and code words are not translated.
- [ ] The file is saved as UTF-8.
- [ ] You added yourself to the translators in `README.md`.

The maintainer checks every translation before it goes into the mod and may ask you to change something.

## License

This repository is licensed under the [MIT License](LICENSE). By opening a pull request you agree that your
contribution is licensed under the same terms (see
[GitHub Terms of Service](https://docs.github.com/en/site-policy/github-terms/github-terms-of-service),
section D.6),
and that it is your own work.
