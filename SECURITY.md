# Security And Privacy Review

This repository contains a Codex skill instruction file and metadata only.

## Included

- `SKILL.md`: workflow instructions for summarizing authorized chat exports.
- `agents/openai.yaml`: display metadata for the skill.
- `README.md`: installation and usage notes.

## Not Included

- No executable scraper.
- No WeChat database reader.
- No remote-control code.
- No credentials.
- No API keys.
- No private group names.
- No local file paths.
- No personal chat logs.
- No Feishu, Lark, or other private document links.

## Risk Boundary

The skill can guide an AI agent to read files or run commands only when the user provides an authorized export method in their own environment. It does not grant access by itself.

Users should review any local command before running it, especially commands that read chat databases, upload files, or publish summaries.
