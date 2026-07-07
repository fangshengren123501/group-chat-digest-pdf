# Group Chat Digest PDF Skill

This is a Codex skill for producing privacy-safe, public-facing PDF digests from authorized multi-person chat exports.

It is designed for community operators, project leads, student groups, online communities, and teams who want to summarize useful group knowledge such as project demos, open-source links, resources, methods, opinions, collaboration opportunities, and member introductions.

## Supported Sources

This skill is source-agnostic. It can work with any authorized exported discussion text, including:

- WeChat groups
- Feishu/Lark groups
- Slack channels
- Discord servers or channels
- Telegram groups
- QQ groups
- Forum or comment threads
- Meeting chats
- Project discussion logs

The user must provide the exported content or an authorized export method. This repository does not include a platform scraper or database reader.

## What This Skill Does

- Helps an agent summarize authorized group chat exports.
- Prioritizes reusable value over raw chronological logs.
- Encourages public-facing wording for all members.
- Requires privacy checks before publishing or uploading results.
- Produces a clean PDF digest when a local PDF renderer is available.

## What This Skill Does Not Do

- It does not include any chat database reader.
- It does not include any platform scraper.
- It does not include any remote-control code.
- It does not include any local machine paths.
- It does not include private group names, private links, account IDs, or personal data.
- It does not automatically access another person's account or device.

## Install

Copy the `group-chat-digest-pdf` folder into your Codex skills directory.

Common location:

```text
~/.codex/skills/group-chat-digest-pdf
```

Then restart Codex or reload skills if your environment supports it.

## Required User-Side Setup

The user must provide one of the following:

- An exported group chat text file.
- A local, user-authorized export CLI.
- Another legally authorized chat or discussion export source.

This skill only describes the summarization workflow. It does not bypass platform security, decrypt private data, or collect data by itself.

## Safety Notes

Before sharing any generated digest:

- Remove local file paths.
- Remove private contact remarks and address-book names.
- Remove phone numbers, account IDs, addresses, payment details, credentials, and private links.
- Use conversation display names instead of private names.
- Do not publish raw logs unless all necessary permissions are confirmed.
- Do not infer image, video, voice, or file content unless text evidence is available.

## Example Prompt

```text
Use group-chat-digest-pdf to summarize this authorized group chat export from 2026-07-01 to 2026-07-07. Generate a public-facing PDF digest for all group members.
```

## License

MIT
