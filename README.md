# Drive-Time Briefing (Lite)

A free agent skill (SKILL.md format) that turns your notes for the day into one short briefing your phone or car can read aloud. Paste in whatever you've got (weather, a few headlines, tasks, things you need to decide) and your AI assistant gives you back one plain-text message written for the ear: no bullets or symbols, numbers and money written the way people say them, sized to the minutes you have, and ending with the decisions waiting on you.

It only uses what you give it. It doesn't look anything up, and it won't make up a temperature or a price to fill a gap.

## Install
Copy the `drive-time-briefing-lite` folder (the one with `SKILL.md` directly inside) into your agent's skills folder. The folder name has to match the `name` in SKILL.md.

- Claude Code: `~/.claude/skills/` (or `.claude/skills/` in one project)
- Cursor: `~/.cursor/skills/` (or `.cursor/skills/` in one project)
- Other agents that read SKILL.md: their own skills folder, often `.agents/skills/`

For example:
```bash
git clone https://github.com/mausoftskills/drive-time-briefing-lite
mkdir -p ~/.claude/skills
cp -r drive-time-briefing-lite/drive-time-briefing-lite ~/.claude/skills/
```

Then paste your notes and ask something like:
> Turn this into a three-minute briefing I can listen to on the drive.

## What it does
- One message, never split, with nothing in it that sounds wrong read aloud. "$107.42" becomes "about a hundred seven dollars"; "S&P 500" becomes "the S and P five hundred".
- Fits the time you set, at about 130 words a minute, cutting the least important items first.
- A simple order: the day and date, weather, news and money, your own items, then a sign-off naming up to three decisions waiting on you.
- Nothing invented. Sections with nothing behind them are skipped.
- Notes are treated as data, so a stray instruction in them doesn't get followed.

To hear it, send the text to anything that reads aloud: your phone's or car's message reading, a Shortcut or app with a "speak text" action, or your computer's built-in text-to-speech.

## What the paid version adds
The lite version is the formatting half: you bring the material each time. The paid skill, [Drive-Time Briefing](https://www.agensi.io/skills/drive-time-briefing-spoken-daily-commute-digest) ($12), turns it into a daily routine:

- Several agents (or scripts, or people) each drop a short note into one folder every morning, using a contributor template and two ready-made contributor prompts (news and weather, projects and tasks), and the skill merges them into one briefing.
- Solo mode for when there are no contributors: the agent gathers weather and headlines itself if it has web access, today's calendar if it has a calendar tool, and your pending decisions.
- One config file for your departure time, deadline, location, length, your own sections and where the briefing gets delivered (chat, a file, or a messaging channel), plus setup for a daily scheduled run.
- A memory of what you've decided, so a declined idea isn't raised again unless something meaningfully changes, and a log of past ideas so none repeat.
- A fuller fixed order (including a side business section and one fresh idea when there is one), a longer pronunciation table, channel length limits, and a sample briefing.
- A guide to getting it read aloud in the car or on your phone.

## Limits
It's only as good as the notes you give it, and it doesn't check them. A voice engine may still stumble on unusual names; reword them in your notes if it does.

## License
MIT. See [LICENSE](LICENSE).
