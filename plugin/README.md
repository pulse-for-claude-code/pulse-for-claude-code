# Pulse for Claude Code

Hear and see Claude Code work. Pulse turns every Claude Code session into a track of rhythm, graphics and sound: a kick drum on every prompt, a note on its own lane for every tool call, a chord when Claude finishes a turn. Watch it live while Claude works, or replay it later on any device.

This plugin is the recorder. The player is a free web app you host yourself on your own Vercel and Postgres (Neon, Supabase or any Postgres), set up with one click from the main repository.

## How to use it

1. Deploy your own Pulse player: https://github.com/pulse-for-claude-code/pulse-for-claude-code#record-your-own-in-one-click
2. Install this plugin in Claude Code:

   ```
   /plugin install pulse --marketplace pulse-for-claude-code/pulse-for-claude-code
   ```

3. In your player, press **Copy Claude Code setup**, paste it into Claude Code once and restart. Your sessions now appear in the player.

Without a player address the plugin only keeps the local copy described below and sends nothing.

## What it records, and where it goes

Pulse records the rhythm of a session, never its content. For each Claude Code event it writes one short line:

- the time of the event (milliseconds)
- the kind of event: session start, prompt sent, tool started, tool finished, subagent finished, turn ended, waiting for you, context compacted, session ended
- for tool events, the tool's name (for example `Edit` or `Bash`)
- once per session: the start time, the name of the project folder, and the first 8 characters of the session id

It never records your prompts, Claude's replies, file contents, file paths, commands or tool inputs and outputs.

These lines are saved on your own computer in `~/.claude/pulse/` and sent only to the Pulse player address you configured yourself in `~/.claude/pulse/cloud`, authenticated with your own key. Pulse has no central server, no analytics and no third parties. Data stays in your own database and in that local folder until you delete it there.

## License

MIT. Made by Kevin Ivarsson, Durellem Ltd.
