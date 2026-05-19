# Explore ohmy.md

This workspace documents how a person uses **ohmy.md**, a quiet markdown editor with workspaces, live markdown rendering, local or browser-backed storage, GitHub workspace browsing, and AI-assisted writing tools.

## Start here

1. Open [Saving on disk and in browser](Saving%20on%20disk%20and%20in%20browser.md) to choose the right storage mode.
2. Open [Markdown syntax](Markdown%20syntax.md) for the markdown that renders in place while you type.
3. Open [Slash commands](Slash%20commands.md) for AI blocks, LaTeX, and tables.
4. Open [AI agent skills](AI%20agent%20skills.md) if an AI agent needs to read or update an ohmy.md workspace through URL routes.

## What ohmy.md does

ohmy.md stores writing in **workspaces**. Each workspace has notes, folders, image assets, search, and a markdown editor. The editor shows formatted headings, lists, links, images, code, math, and tables as you type, while still saving the content as markdown.

The file sidebar lets you create notes and folders, rename or delete items, drag items to reorder them, search by file name or note content, and open image files for preview. The top bar shows the current path, save state, token estimate, Markdown guide, raw markdown copy, and Settings.

## Saving and publishing

Use **Local folder** when you want real files on disk. This is the best mode for a documentation workspace that will later become a GitHub repository.

Use **In browser** when you want the workspace stored only in the current browser profile. You can export it later as an archive that matches the local-folder layout.

Use a GitHub route to browse a published repository:

`/github/{owner}/{repo}/{branch}`

GitHub workspaces are read-only in the app, so edit the source repository when you want durable changes.

## AI tools

Save a Gemini API key in Settings to enable AI writing and drawing. Use `/ai-write` for generated markdown, `/ai-draw` for generated images, and the selection rewrite tool for improving existing text. The AI context agent can inspect the workspace, include relevant files, and show which files were used.

## Agent access

Agents should not operate the editor UI to modify content. They should read `/agent/skills`, inspect the workspace through `/agent/workspaces`, and use the documented `/agent` write routes. Those routes update the same browser-local or connected-folder workspace that the app displays.