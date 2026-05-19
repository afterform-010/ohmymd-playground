# Markdown syntax

ohmy.md renders markdown in place as you type. The editor keeps the document as markdown, but common syntax becomes formatted content immediately.

## Headings

`# Heading 1`

`## Heading 2`

`### Heading 3`

The editor supports heading levels one through six.

## Emphasis

Use `*italic*` or `_italic_` for italic text.

Use `**bold**` or `__bold__` for bold text.

Use backticks for `inline code`.

## Lists

Start a bullet list with `- ` or `* `.

Start an ordered list with `1. `.

## Links and images

Use `[label](url)` for links.

Use `![alt](image.png)` for images.

Relative links and image paths are resolved inside the current workspace. If you link to another markdown file in the workspace, clicking the link opens that file. External URLs open as normal links.

Pasting an image into a note saves the image as a workspace asset and inserts a relative markdown image reference automatically.

## Code blocks

Type three backticks on an empty line to start a fenced code block:

```text
code goes here
```

## Quotes and dividers

Type `> ` to start a blockquote.

Type `---`, `___`, or `***` on a line by itself to insert a horizontal rule.

## Tables

The editor supports GitHub-flavored markdown tables:

```markdown
| Name | Value |
| --- | --- |
| Local folder | Files on disk |
| In browser | IndexedDB |
```

You can also type `/table` to insert a table builder and then edit the cells visually.

## Math

Inline math uses dollar signs: `$x^2 + y^2 = z^2$`.

Display math uses double dollar signs:

```markdown
$$
E = mc^2
$$
```

For safer editing with live preview, use `/latex-inline` for inline math or `/latex` for a display equation.