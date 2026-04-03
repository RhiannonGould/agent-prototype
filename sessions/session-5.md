# Session 5

Create a claude settings that will allow any bash commands and other helpful comments like read, etc, without my approval.
update-config skill
Let me read the existing global settings file first.

Read settings.json
The file is empty. I'll set defaultMode to bypassPermissions so all tools run without prompting.

Write settings.json
6 lines
{
  "permissions": {
    "defaultMode": "bypassPermissions"
  }
}
Done. ~/.claude/settings.json now has defaultMode: bypassPermissions, which skips approval prompts for all tools — Bash, Read, Write, Edit, Glob, Grep, and everything else — globally across all projects.

settings.local.json
Add bash(.*) so it can run bash commands in local project directory only
Read settings.local.json
Edit settings.local.json
Added 1 line
Added Bash(.*) to the allow list in .claude/settings.local.json. This permits all bash commands within this project without prompting
