# Saving on disk and in browser

ohmy.md can keep workspaces in two writable storage modes: **Local folder** and **In browser**. Pick the mode before creating or opening a workspace from the start screen.

## Local folder

Local folder mode saves through the browser's File System Access API. Choose a root folder, then ohmy.md creates one folder per writespace inside it. Each writespace folder contains your markdown files, pasted images, and a small `.ai-md-editor-workspace.json` manifest. The root also contains `.ai-md-editor-index.json`, which records the list of workspaces and the active workspace.

Use this mode when you want real files on disk, sync through tools such as iCloud Drive or OneDrive, or commit the workspace to a GitHub repository. A Chromium-based browser is required. After you grant access, ohmy.md remembers the folder handle in the current browser profile and reconnects on reload when permission is still available.

## In browser

In browser mode saves the same workspace data in IndexedDB for the current browser profile. Nothing appears as normal files on disk while you work. This is convenient for quick writing, private drafts, and browsers where you do not want to grant folder access.

Browser storage is tied to the browser profile and device. Clearing site data or using a different profile can make the workspace unavailable. Use **Export archive** from the start screen when you want a portable zip that matches the local-folder layout.

## GitHub workspaces

ohmy.md can also open a public GitHub repository with a route like:

`/github/{owner}/{repo}/{branch}`

When the repository contains exported or local-folder workspace metadata, ohmy.md shows those workspaces. If no metadata is found, it can infer a read-only workspace from the repository tree. GitHub workspaces are read-only in the app; the top bar shows that changes will not be saved.

## Which mode to choose

Use **Local folder** for long-lived documentation, files you want to back up, or work you plan to publish in GitHub.

Use **In browser** for temporary exploration or notes that do not need to leave the current browser profile.

Use **GitHub** when you want to browse published markdown workspaces without granting local disk access.