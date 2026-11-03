# Open Language - English

The English coursebook from Open Language: grammar, concepts, writing and vocabulary articles, each with listening examples. It starts at A1.

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

- **Two languages per coursebook.** Every coursebook has a target language, the one taught, and a coursebook language, the one its prose and translations are written in. In German they are German and English; here both are English. The package only knows the first (`language_code`) and assumes the second is English: the `:title-en:` option, the `Translation` entry in its `CONTEXT.md`, the `english_filename` rule. The app's per-interface-language translations (open-language-app ADR 0004) are a separate question, still to be worked out.
- **Prose checks per coursebook language.** The checks measure English prose: sentence length, stock openers, the reader addressed as "you". A coursebook written in another language needs them for that language.
- **Italics in headings.** `ol validate` takes any heading word that appears in the examples but not in the prose as a word of the language taught, and asks for italics. When the target and coursebook languages are the same, ordinary heading words such as *course* or *how* trip it, so some headings here are worded around it.
- **`lang` attributes.** Authors never declare a language: the `stack` role reads the target language from `open-language.yml` and tags the phrase with it. The translation beneath gets no tag, because the package has no coursebook language to give it.

## Reporting a problem

Found a wrong example, a typo or a confusing explanation? [Open an issue](https://github.com/OpenLanguageStudio/english/issues).
