# Open Language - English

The English coursebook from Open Language: grammar, concepts, writing and vocabulary articles, each with listening examples. It starts at A1, with German translations.

## Layout

```
<level>/<category>/         articles, one topic each
index.md, conf.py           the site's home page and its build settings
open-language.yml           the language's settings
glossary-terms.yml          the grammar terms this coursebook adds to the shared list
```

Levels are `a1` to `b2`; only `a1` exists so far. Categories are `concepts`, `grammar`, `writing` and `vocabulary`.

## Working on the content

Install with [uv](https://docs.astral.sh/uv/):

```
uv sync
```

Check everything the way CI does:

```
uv run ol check
```

That runs the article checks and a strict build of the site. Build and preview locally with `uv run ol docs`.

New articles start from a template. `uv run ol templates` lists them and `uv run ol templates grammar-article.md` prints one.

## Why this repository exists now

It is the second language repository, after German, so that the `open-language` package can be built and tested for more than one language. Its first job is to show where the package still assumes German. The questions it raises so far:

- **Translation language.** The package treats a translation as English. Here the language taught is English, so the translations are in German. The app stores a translation per interface language, with English as the fallback (open-language-app ADR 0004), which does not fit a course whose language taught is English.
- **Prose language.** The checks measure English prose: sentence length, stock openers, the reader addressed as "you". A course written for German speakers in German would need those checks per prose language.
- **Italics in headings.** `ol validate` takes any heading word that appears in the examples but not in the prose as a word of the language taught, and asks for italics. When the language taught and the prose are both English, ordinary heading words such as *course* or *how* trip it, so some headings here are worded around it.
- **`lang` attributes.** The `stack` role marks the phrase with the language code, but not the translation beneath it, so German text is served without `lang="de"`.

## Reporting a problem

Found a wrong example, a typo or a confusing explanation? [Open an issue](https://github.com/OpenLanguageStudio/english/issues).
