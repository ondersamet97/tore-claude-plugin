# töre for Claude Code

A Claude Code plugin for [töre](https://github.com/ondersamet97/tore), a local notebook that turns your AI conversations into decisions, open questions and tasks you review yourself.

With the plugin, Claude Code can:

- **Continue from a topic.** Say "continue from my töre topic X". Claude reads that topic's adopted decisions and opinions, open tasks and open questions, and picks up where you left off.
- **Leave a proposal.** `/tore:propose <text>` leaves a task result, decision, question, task, note or objection in töre's inbox (**Gelen kutusu**). Nothing is adopted until you review it in töre.

## What it can and cannot see

- **The plugin contains no data.** It is a few text files and a launcher script. After you install it, it connects to the töre on your own computer and your own notebook. Nobody else's notebook is involved, and nothing is uploaded by the plugin.
- Claude sees only the topics you opened to the connected AI tool in töre, and only adopted decisions and opinions, open tasks and open questions of those topics.
- Claude cannot change your notebook. Proposals wait in the inbox; you accept or dismiss them, and only you close a task.
- What Claude Code then does with the text it read (sending it to its model provider) is governed by Claude Code and your account.

## Requirements

- töre 0.15.0 or newer, built on your computer: clone [the töre repository](https://github.com/ondersamet97/tore), then run `bash scripts/build.sh` in it and start it once with `bash Başlat.command`. A new installation starts with an empty notebook.
- In töre, open at least one topic to the connected AI tool: **Konularım**, then **Bağlı AI aracı**. Allow proposals for a topic if you want `/tore:propose` to work there.
- Claude Code. Verified on macOS only.

## Install

In Claude Code:

```
/plugin marketplace add ondersamet97/tore-claude-plugin
/plugin install tore@tore
```

When asked, enter your **töre folder**: the absolute path of your töre checkout (the folder that contains `Başlat.command`). Leave the notebook folder empty unless you keep your notebook somewhere other than `<töre folder>/.demo-data/runtime`. Despite its name, that folder is your real notebook.

Check the connection with `/mcp`: the server is listed as `plugin:tore:tore`.

## Use

- "What is open in töre?"
- "Continue from my töre topic Neighbourhood library."
- `/tore:propose The volunteer rota draft is ready for review.`

## Troubleshooting

- **"töre is not built yet"**: run `bash scripts/build.sh` in your töre folder.
- **"no notebook found yet"**: start töre once with `Başlat.command`.
- **After updating töre**: run `/mcp`, choose `plugin:tore:tore`, then Reconnect.

## Licence

AGPL-3.0-only, like töre. See [LICENSE](LICENSE).
