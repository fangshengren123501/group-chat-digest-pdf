# WeChat Group Digest PDF Skill

This is a Codex skill for producing privacy-safe, public-facing PDF digests from authorized WeChat group chat exports.

It is designed for community operators who want to summarize useful group knowledge such as project demos, open-source links, resources, methods, opinions, collaboration opportunities, and member introductions.

## What This Skill Does

- Helps an agent summarize authorized WeChat group chat exports.
- Prioritizes reusable value over raw chronological logs.
- Encourages public-facing wording for all group members.
- Requires privacy checks before publishing or uploading results.
- Produces a clean PDF digest when a local PDF renderer is available.

## What This Skill Does Not Do

- It does not include any WeChat database reader.
- It does not include any remote-control code.
- It does not include any local machine paths.
- It does not include private group names, private links, WeChat IDs, or personal data.
- It does not automatically access another person's WeChat account.

## Install

Copy the `wechat-group-digest-pdf` folder into your Codex skills directory.

Common location:

```text
~/.codex/skills/wechat-group-digest-pdf
```

Then restart Codex or reload skills if your environment supports it.

## Required User-Side Setup

The user must provide one of the following:

- An exported WeChat group chat text file.
- A local, user-authorized WeChat export CLI.
- Another legally authorized chat export source.

This skill only describes the summarization workflow. It does not bypass WeChat security, decrypt private data, or collect data by itself.

## Safety Notes

Before sharing any generated digest:

- Remove local file paths.
- Remove private contact remarks.
- Remove phone numbers, WeChat IDs, addresses, payment details, and private links.
- Use group display nicknames instead of private names.
- Do not publish raw logs unless all necessary permissions are confirmed.
- Do not infer image, video, voice, or file content unless text evidence is available.

## Example Prompt

```text
Use wechat-group-digest-pdf to summarize this authorized group chat export from 2026-07-01 to 2026-07-07. Generate a public-facing PDF digest for all group members.
```

## License

MIT
