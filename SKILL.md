---
name: group-chat-digest-pdf
description: Summarize authorized multi-person chat exports into privacy-safe public digest PDFs. Use for daily, weekly, or date-range group chat digests, community highlights, reusable knowledge summaries, and PDF reports from exported chats such as WeChat groups, Feishu/Lark groups, Slack, Discord, Telegram, QQ groups, forums, or project discussion threads.
---

# Group Chat Digest PDF

Use this skill to turn authorized multi-person chat exports into public-facing digest PDFs. The output should help members quickly understand the useful information, resources, demos, ideas, decisions, and collaboration opportunities that appeared in the discussion.

## Required Inputs

- Chat platform or source, such as WeChat, Feishu/Lark, Slack, Discord, Telegram, QQ, forum comments, meeting chat, or project discussion thread.
- Group name, channel name, conversation identifier, or an exported chat text file.
- Date range and timezone.
- The user's authorized export method, if available.
- Output format: PDF by default; optional Markdown or shared document when requested.
- Audience: usually all group members, not only the requester.

## Privacy Rules

- Only process chats the user has the right to access and summarize.
- Write from a public, group-facing perspective.
- Use the display name or nickname shown in the conversation. Do not use private contact remarks or local address-book names.
- Do not expose phone numbers, account IDs, private links, private file paths, addresses, payment details, credentials, or personal identifiers.
- Do not publish raw chat logs unless the user explicitly asks and confirms permission.
- Summarize sensitive or private exchanges at a high level, or omit them if they are not useful to the public digest.
- Do not infer the content of images, videos, voice messages, or files unless reliable text evidence is available.
- If uploading to a shared document or public link, remove local paths, private remarks, and private defaults before publishing.

## Digest Priorities

Prioritize reusable value over chronological completeness:

1. Project demos, product links, open-source repositories, prototypes, and real examples.
2. High-value resources, tutorials, documents, datasets, courses, prompts, and tools.
3. Methods and workflows that others can reuse.
4. Good ideas, opinions, debates, and decision points.
5. Collaboration opportunities, events, job or internship information, and member requests.
6. New member self-introductions when they are relevant to community connection.
7. Important group operations, announcements, and follow-up actions.

Avoid turning the digest into a private recap for one person. The reader should feel: "What useful things did this group produce, and where can I follow up?"

## Standard Workflow

1. Confirm scope.
   - Identify the platform, group or channel, date range, timezone, output location, and whether the digest is for private review or public sharing.

2. Export or read chat history.
   - If a local export CLI or platform export exists, use its documented command.
   - If only a text, CSV, JSON, Markdown, HTML, or database export is available, read that source directly.
   - Keep original evidence local unless the user explicitly requests upload.

   Example placeholder command:

   ```powershell
   $source = "GROUP_OR_CHANNEL_NAME"
   $start = "YYYY-MM-DD 00:00:00"
   $end = "YYYY-MM-DD 23:59:59"
   $out = Join-Path $env:TEMP "group_chat_digest_raw.txt"
   & "<path-to-authorized-export-cli>" export $source --start-time $start --end-time $end --format text | Out-File -FilePath $out -Encoding UTF8
   ```

3. Evidence pass.
   - Extract URLs, file names, repository names, project names, tool names, and repeated topic keywords.
   - Keep speaker names as displayed in the conversation.
   - Separate factual evidence from interpretation.

4. Value screening.
   - Remove greetings, duplicate jokes, one-word reactions, and low-context small talk unless they explain an important interaction.
   - Keep concrete shares, practical methods, strong opinions with reasons, and follow-up opportunities.

5. Draft the digest.
   - Use concise headings.
   - Group content by value category or date, depending on the user's instruction.
   - Include enough context for readers who did not follow the original chat.
   - Avoid exposing unnecessary personal details.

6. Render PDF.
   - Use any available local PDF renderer that supports the language of the source chat.
   - Verify that the PDF opens, text renders correctly, and layout is readable on desktop and mobile.

7. Final check.
   - Scan the output for private contact remarks, local file paths, private URLs, unsupported claims, and raw sensitive content.
   - Report the PDF path and any document link if one was created.

## Suggested Public Digest Structure

```markdown
# Group Chat Digest

Date range: YYYY-MM-DD to YYYY-MM-DD
Source: platform, group, channel, or exported discussion source
Scope: Public group discussion content only

## Quick Overview
- 3 to 5 important findings from the discussion.

## Project Demos And Real Practice
- Display name: what was shared, why it matters, and how others can follow up.

## High-Value Resources And Tools
- Resource or tool name: use case, target reader, and link or file name.

## Methods And Workflows
- Method name: what problem it solves, how to use it, and caveats.

## Opinions And Discussions
- Topic: main views, disagreements, and reusable conclusions.

## Member Connection And Opportunities
- New member introductions, collaboration opportunities, events, and requests.

## Follow-Ups
- Concrete next actions.
```

## Quality Bar

- The digest must be useful to people who did not read the full chat.
- Claims should be traceable to chat evidence.
- Do not over-summarize high-value shares into vague phrases.
- Do not invent missing details.
- Keep the final PDF clean, searchable where possible, and free of garbled characters.
