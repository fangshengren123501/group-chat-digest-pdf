---
name: wechat-group-digest-pdf
description: Export and summarize authorized local WeChat group chats into privacy-safe public digest PDFs. Use when the user asks for daily, weekly, or date-range WeChat group digests, community highlights, reusable knowledge summaries, or PDF reports based on local chat exports.
---

# WeChat Group Digest PDF

Use this skill to turn authorized WeChat group chat history into a public-facing digest PDF. The output should help group members quickly understand what useful information, resources, demos, ideas, and collaboration opportunities appeared in the chat.

## Required Inputs

- Group name, chat identifier, or an exported chat text file.
- Date range and timezone.
- The user's local WeChat export method, if available.
- Output format: PDF by default; optional Markdown or Feishu/Lark document when requested.
- Audience: usually all group members, not only the requester.

## Privacy Rules

- Only process chats the user has the right to access.
- Write from a public, group-facing perspective.
- Use the nickname shown in the group chat. Do not use the user's private contact remarks.
- Do not expose phone numbers, WeChat IDs, private links, private file paths, addresses, payment details, or personal identifiers.
- Do not publish raw chat logs unless the user explicitly asks and confirms they have permission.
- Summarize sensitive or private exchanges at a high level, or omit them if they are not useful to the public digest.
- Do not infer the content of images, videos, voice messages, or files unless their text content is available.
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

Avoid turning the digest into a private recap for one person. The reader should feel: "What useful things did the group produce today, and where can I follow up?"

## Standard Workflow

1. Confirm scope.
   - Identify the group, date range, timezone, output location, and whether the digest is for private review or public sharing.

2. Export or read chat history.
   - If a local WeChat export CLI exists, use its documented command.
   - If only a text or database export is available, read that file directly.
   - Keep original evidence local unless the user explicitly requests upload.

   Example placeholder command:

   ```powershell
   $chat = "GROUP_NAME_OR_ID"
   $start = "YYYY-MM-DD 00:00:00"
   $end = "YYYY-MM-DD 23:59:59"
   $out = Join-Path $env:TEMP "wechat_group_digest_raw.txt"
   & "<path-to-wechat-export-cli>" history $chat --start-time $start --end-time $end --format text --limit 30000 --media | Out-File -FilePath $out -Encoding UTF8
   ```

3. Evidence pass.
   - Extract URLs, file names, repository names, project names, tool names, and repeated topic keywords.
   - Keep speaker nicknames as shown in the group.
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
   - Use any available local PDF renderer that supports Chinese fonts.
   - Verify that the PDF opens, Chinese text renders correctly, and layout is readable on desktop and mobile.

7. Final check.
   - Scan the output for private contact remarks, local file paths, private URLs, and unsupported claims.
   - Report the PDF path and any document link if one was created.

## Suggested Public Digest Structure

```markdown
# Group Chat Digest

Date range: YYYY-MM-DD to YYYY-MM-DD
Scope: Public group chat content only

## Quick Overview
- 3 to 5 important findings from the chat.

## Project Demos And Real Practice
- Nickname: what was shared, why it matters, and how others can follow up.

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
