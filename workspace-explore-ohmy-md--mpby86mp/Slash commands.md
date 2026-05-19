# Slash commands

Type a slash command in the editor and press space to insert a special block or inline tool.

## /ai-write

`/ai-write` inserts an AI writing block. Type the request in the block, then use **Send** or **Shift+Enter**. The AI streams a proposed markdown draft. Use **Accept** to insert the draft into the document, **Redo** to return to the prompt, **Stop** to stop streaming, or **Reject/Delete** to remove the block.

The writing block can inspect the current workspace, choose relevant files, and show the agent thought and included files while it works. A Gemini API key must be saved in Settings.

## /ai-draw

`/ai-draw` inserts an AI image-generation block. Describe the image, send the request, then accept the result to save the generated image into the workspace and insert a markdown image reference.

The draw block can also inspect workspace context before generating. A Gemini API key must be saved in Settings.

## /latex

`/latex` inserts a display equation editor. Type LaTeX, preview the rendered equation, then click **Done** or press **Shift+Enter**. The saved markdown uses standard `$$...$$` display math.

## /latex-inline

`/latex-inline` inserts an inline equation editor. Type LaTeX, preview the rendered equation, then click **Done** or press **Shift+Enter**. The saved markdown uses standard `$...$` inline math.

## /table

`/table` inserts a table builder. Edit the cells visually; the document saves as a GitHub-flavored markdown table.

## AI comment rewrite

The AI comment tool is a selection command, not a slash-inserted block. Select text, then click **Ask AI to rewrite** or press **Command+K** on macOS or **Ctrl+K** on Windows/Linux. Choose a preset or type an instruction, then accept or reject the suggested replacement.