# AI agent skills

ohmy.md exposes browser-local workspace routes under `/agent` so an AI agent can inspect and update the current browser profile's workspaces without clicking through the editor UI.

The canonical skills page is:

`/agent/skills`

It returns plain text instructions for the agent.

## Scope

Agent routes read and write the same workspace state used by the app in the current Chrome profile.

In browser storage mode, routes read from IndexedDB.

In local-folder mode, routes read and write through the connected File System Access root. The folder must already be connected in the app before the routes can access it.

These are browser-local routes, not remote server APIs. Write commands mutate local browser or local-folder state.

## Recommended agent flow

1. Read `/agent/skills`.
2. Read `/agent/workspaces` and choose a workspace id.
3. Read `/agent/workspaces/{workspaceId}/tree` to inspect files and folders.
4. Read `/agent/workspaces/{workspaceId}/files/{fileId}` for exact file content.
5. Use write command routes when needed.
6. Re-read the tree or file route to confirm the result.

## Read routes

`/agent/workspaces` lists workspaces.

`/agent/workspaces/{workspaceId}/tree` returns the workspace file tree, including ids and paths.

`/agent/workspaces/{workspaceId}/files/{fileId}` returns file metadata and exact content.

Text files return `encoding: "text"`. Binary files return `encoding: "base64"`.

## Write routes

Create a workspace:

`/agent/workspaces/create?name={workspaceName}`

Rename a workspace:

`/agent/workspaces/{workspaceId}/rename?name={newWorkspaceName}`

Create a folder:

`/agent/workspaces/{workspaceId}/folders/create?name={folderName}`

Create a nested folder by adding `parent_id={folderId}`.

Rename a folder:

`/agent/workspaces/{workspaceId}/folders/{folderId}/rename?name={newFolderName}`

Create a file:

`/agent/workspaces/{workspaceId}/files/create?name={fileName}&content={urlEncodedText}`

Create a file inside a folder by adding `parent_id={folderId}`.

Replace the first matching text span in a file:

`/agent/workspaces/{workspaceId}/files/{fileId}/replace-first?old_text={oldText}&new_text={newText}`

Rename a file:

`/agent/workspaces/{workspaceId}/files/{fileId}/rename?name={newFileName}`

Delete a file:

`/agent/workspaces/{workspaceId}/files/{fileId}/delete`

## Query encoding

Always build query strings with `URLSearchParams` or an equivalent encoder. File names, markdown content, replacement text, and folder names can contain spaces, punctuation, and newlines.

## Confirmation

After a write command, read the affected file or workspace tree again. Successful write responses return JSON with `ok: true`, storage information, and the changed resource.
