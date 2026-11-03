# Open Language - English

The English coursebook from Open Language: concepts, grammar, writing and vocabulary articles, each with sentences to listen to. Anyone can report a problem or suggest a change.

## Report a problem or ask for an article

Found a wrong example, a typo or a confusing explanation, or missing a topic? [Open an issue](https://github.com/OpenLanguageStudio/english/issues) and choose the form that fits:

- **Report a problem in an article**: name the page and quote what is wrong.
- **Request an article**: name the topic and its level.

## Change a page

Each article is one Markdown file:

```
<level>/<category>/<name>.md    one article, one topic
<level>/<category>/index.md     the list of a category's articles
```

Levels are `a1` to `b2`. Categories are `concepts`, `grammar`, `writing` and `vocabulary`.

1. Read the [authoring rules](https://github.com/OpenLanguageStudio/open-language/blob/main/docs/reference/authoring-rules.md) and the [page standard](https://github.com/OpenLanguageStudio/open-language/blob/main/docs/reference/page-standard.md). Every article follows them.
2. Install the tools with [uv](https://docs.astral.sh/uv/): `uv sync`.
3. Start a new article from its template. `uv run ol templates` lists them, and `uv run ol templates grammar-article.md` prints one.
4. Check the change with `uv run ol check`, and preview the site with `uv run ol docs`.
5. Open a pull request. The same checks run on it, and it is merged once they pass and a reviewer has read it.
