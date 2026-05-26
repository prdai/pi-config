# pi config

My personal [pi](https://pi.dev) coding agent configuration — extensions, skills, settings, and themes. Sync across devices via git.

## Setup on a new device

```bash
# 1. Clone into your home directory
git clone https://github.com/prdai-archive/pi-config.git ~/.pi

# 2. Authenticate with an API key (or use /login inside pi)
export ANTHROPIC_API_KEY=sk-ant-...
# or export OPENAI_API_KEY=sk-...

# 3. Install npm dependencies (extension deps)
cd ~/.pi/agent/npm && npm install

# 4. Start pi
pi
```

After first launch, run `/login` to authenticate or use the API key env var above.

## What's included

| Directory | Contents |
|-----------|----------|
| `agent/extensions/` | bash-guard, filechanges, google-image-search, memory, subagents, video-extract, web-fetch, web-search, youtube-search, and more |
| `agent/skills/` | orchestrator, pdf-reader, reddit, stop-slop |
| `agent/themes/` | custom themes |
| `agent/settings.json` | global pi settings |

## What stays local

The following are gitignored and never pushed:

- `agent/auth.json` — API keys and credentials
- `agent/sessions/` — chat history
- `agent/spar/` — spar conversation history
- `**/node_modules/` — installed dependencies

## Update across devices

```bash
# Pull latest config
cd ~/.pi && git pull
```

On the device where you made changes:

```bash
cd ~/.pi && git add -A && git commit -m "update config" && git push
```
