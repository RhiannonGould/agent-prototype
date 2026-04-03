# Session 2 - Create Claude skills

Glob output (o9yped)
Acting as an expert Claude Code Engineer create actual Claude skills out of the files that are in the .claude/skills directory
Bash List .claude/skills directory contents
IN
ls -la /Users/rhiannnon/Documents/GitHub/agent-prototype/.claude/skills/ 2>/dev/null && echo "---" && ls -la /Users/rhiannnon/Documents/GitHub/agent-prototype/.claude/ 2>/dev/null

OUT
total 0
drwxr-xr-x  7 rhiannnon  staff  224 Apr  3 10:04 .
drwxr-xr-x  5 rhiannnon  staff  160 Apr  3 10:01 ..
drwxr-xr-x  3 rhiannnon  staff   96 Apr  3 10:03 flourishing-prompt
drwxr-xr-x  3 rhiannnon  staff   96 Apr  3 10:04 gratitude-inventory
drwxr-xr-x  3 rhiannnon  staff   96 Apr  3 10:02 reframe
drwxr-xr-x  3 rhiannnon  staff   96 Apr  3 10:01 session-start
drwxr-xr-x  3 rhiannnon  staff   96 Apr  3 10:02 want-examination
---
total 16
drwxr-xr-x  5 rhiannnon  staff   160 Apr  3 10:01 .
drwxr-xr-x  6 rhiannnon  staff   192 Apr  3 10:04 ..
-rw-r--r--  1 rhiannnon  staff  2013 Apr  2 16:29 settings.json
-rw-r--r--  1 rhiannnon  staff   215 Apr  3 09:31 settings.local.json
drwxr-xr-x  7 rhiannnon  staff   224 Apr  3 10:04 skills
Globpattern: ".claude/**/*"
Found 7 files
Read SKILL.md
Read SKILL.md
Read SKILL.md
Read SKILL.md
Read SKILL.md
Read settings.json
I can see the skills are already registered with Claude Code, but there are naming mismatches between the directory names (which Claude Code uses as skill identifiers) and the name fields in the SKILL.md frontmatter, plus all the cross-references use the wrong names. Let me fix these.

The mapping of issues:

Directory want-examination → SKILL.md says usage-examination
Directory reframe → SKILL.md says boundary-setting
Directory flourishing-prompt → SKILL.md says alternative-prompt
Directory gratitude-inventory → SKILL.md says reflection-inventory
session-start routes to /usage-examination, /boundary-setting, /alternative-prompt, /reflection-inventory — none of which match the actual directory-based skill names
Let me fix all of these now.

Edit SKILL.md
Modified
Edit SKILL.md
Modified
Edit SKILL.md
Modified
Edit SKILL.md
Modified
Now fix the cross-references in all skills. Starting with session-start which routes to the other skills:

Edit SKILL.md
Modified
Now fix the cross-references in the other skills:

Edit SKILL.md
Modified
Edit SKILL.md
Modified
Edit SKILL.md
Modified
Edit SKILL.md
Modified
All 5 skills are now properly configured and functional. Here's what I fixed:

Naming alignment — the name field in each SKILL.md now matches its directory name (which is what Claude Code uses as the skill identifier):

Directory	Old name field	Fixed to
want-examination	usage-examination	want-examination
reframe	boundary-setting	reframe
flourishing-prompt	alternative-prompt	flourishing-prompt
gratitude-inventory	reflection-inventory	gratitude-inventory
Cross-references — updated all slash command references across all 5 skills to use the correct skill names (e.g. /boundary-setting → /reframe, /alternative-prompt → /flourishing-prompt, etc.)

The skills are already live and visible in the system — you can invoke them with /session-start, /want-examination, /reframe, /flourishing-prompt, and /gratitude-inventory.