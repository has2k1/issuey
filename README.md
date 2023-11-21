# Create links to issues and pull requests in quarto using shortcodes

This issue extension is for quarto and quartodoc.

## Installing

```bash
quarto add has2k1/issuey
```

This will install the extension under the `_extensions` subdirectory.
If you're using version control, you will want to check in this directory.

## Using

Create a `.qmd` file (or project) with configuration for `issuey`. e.g.

```md
---
title: "Issue Example"

issuey:
   issue-url: "https://github.com/has2k1/plotnine/issues/%id"
   issue-text: "#%id"
   issue-title: "Issue: #%id"
   pull-request-url: "https://github.com/has2k1/plotnine/pulls/%id"
   pull-request-text: "PR%id"
   pull-request-title: "Pull Request: #%id"
---

## Heading

{{< issue 123 >}}

{{< pr 684 >}}
```
Where the issue / pull-request id are substituted for `%id`.

- `*-url` is the link
- `*-text` is link text
- `*-title` is link title (What comes up when you hover over the link).
  The title(s) is optional.

The above snippet would create the following html

```html
<a href="https://github.com/has2k1/plotnine/issues/123" title="Issue: #123">#123</a>

<a href="https://github.com/has2k1/plotnine/pulls/684" title="Pull Request: #684">PR684</a>
```


## Example

Here is the source code for a minimal example: [example.qmd](example.qmd).
