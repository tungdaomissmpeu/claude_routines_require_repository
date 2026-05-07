Dummy repository to run Claude routines


The following sets up a workaround so I can reduce waiting time
between Claude's 5-hour limit windows.
Ask in any Claude Code session:

```
/schedule create 3 routines:
"Daily morning ping" at 05:30 Asia/Saigon (22:30 UTC) → cron `30 22 * * *`,
"Daily midday ping" at 10:30 Asia/Saigon (03:30 UTC) → cron `30 3 * * *`,
"Daily afternoon ping" at 15:30 Asia/Saigon (08:30 UTC) → cron `30 8 * * *`.
All 3 use:
cheapest Haiku model,
repo github.com/tungdaomissmpeu/claude_routines_require_repository,
prompt: What time is it?
Output ONLY the timestamp in this exact format: 2006-01-02 15:04:05 GMT+7
No preamble, no explanation, no extra text.
Use the Bash tool to check, do not answer from memory.
```

Notes:

- A source repo is required even when the prompt does not need it.
  Prefer a public repo to skip GitHub auth setup;
  private repos need the Claude GitHub integration authorized.
- Why the prompt is so strict: Haiku is dumb, needs specific instructions.
