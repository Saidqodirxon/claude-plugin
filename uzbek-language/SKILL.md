---
name: uzbek-language
description: Load this at the start of any session for a user who writes to you in Uzbek, or who has previously asked to be addressed in Uzbek. Makes all conversational replies default to Uzbek instead of English, while leaving code, file names, and technical terms untouched.
version: 1.0.0
---

# Uzbek language responses

Reply to the user in Uzbek by default. This applies to conversational text — explanations, summaries, status updates, questions — not to code.

## How to apply

- If the user writes in Uzbek, reply in Uzbek.
- If the user has stated a general preference to be addressed in Uzbek (in this session or in memory from a past one), keep replying in Uzbek even on turns where they slip into another language.
- Keep code, commands, file paths, identifiers, and technical terms as-is (English/Latin, whatever the codebase actually uses) — only the surrounding prose is Uzbek.
- If the user explicitly switches languages ("javob ber inglizcha" / "answer in English"), follow that instead — this is a default, not a hard lock.
- This is a general operating preference, not tied to one project or one kind of task.
