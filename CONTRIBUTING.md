# Contributing to Pulse

Thanks for wanting to make Pulse better. Pulse is a community project: it belongs to the people who use it and build on it.

## Ways to help

- **Try it and tell us.** Bugs and rough edges go in [Issues](../../issues/new/choose). A screenshot or a short screen recording helps a lot.
- **Share a session.** Real Claude Code sessions make the best starter tracks. See [starter/README.md](starter/README.md).
- **Pick up an issue.** Issues labelled `good first issue` are small and well described. Comment that you're taking one, so two people don't do the same work.
- **Bigger ideas.** Start a thread in [Discussions](../../discussions) before you build, so we can agree on the shape first. [ROADMAP.md](ROADMAP.md) lists what's wanted.

## How the code is laid out

| Folder | What it is |
|---|---|
| `index.html` | The whole player: one file, no framework, no build step |
| `tracks.js` | Cuts recordings into tracks and packs tracks into share links. No dependencies |
| `api/` | Four small serverless endpoints (ingest, sessions, events, library) on any Postgres |
| `plugin/` | The Claude Code plugin: hooks and one short Bash script |
| `desktop/` | Pulse Disc, the floating desktop disc (Electron) |
| `starter/` | The starter pack, in the `.pulse` format |
| `tools/` | Checks and generators |

## Run it locally

```
npx vercel dev            # with DATABASE_URL pointing at any Postgres
node tools/test-tracks.mjs
desktop/assemble.sh linux-x64   # or win32-x64, then run the app in desktop/dist
```

## House rules

- **Keep it small.** No framework and no build step for the player. A new dependency needs a good reason.
- **Privacy first.** Pulse records event types, tool names and the project folder name, nothing else. Never prompts, code or file contents. Share links carry even less.
- **Lane colours mean their lane** everywhere: in the player, the disc, video and merch. See the brand notes in the README.
- **Plain words** in the interface, sentence case, no exclamation marks.
- One change per pull request, with a line on how you checked it.

By contributing you agree your work is released under the [MIT License](LICENSE) and that you follow the [Code of Conduct](CODE_OF_CONDUCT.md).
