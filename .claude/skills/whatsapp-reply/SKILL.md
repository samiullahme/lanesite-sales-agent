---
name: whatsapp-reply
description: Write the next WhatsApp voice-note/text reply to a business-owner lead for LaneSite. Use for every outreach opener or reply.
---

Input: the lead's details (business_name, type, page observation) and the conversation so far.

Steps, in order:
1. Read CLAUDE.md, context/rules.md, context/offer.md and memory/lessons.md.
2. Check memory/leads-log.md. If the lead is DO_NOT_CONTACT, stop and write nothing.
3. Detect the business type and load niches/<type>.md (use the closest match; "other" → shop.md style).
4. Detect the persona from their last message and load personas/<type>.md. If unsure, use busy.md.
5. If their message is a question, answer it from context/faq.md. If it's an objection, use context/objections.md. If it's neither, follow the pain → fix → proof → ask flow.
6. Write the reply in their language and script, keeping to the length limits. If the FORMAT is voice, also read context/voice.md and write a separate VOICE_SCRIPT: spoken style, punctuation for pauses, numbers as words, no link, at most one allowed audio tag.
7. Send the draft to the reply-checker agent. If it returns FIX, rewrite and check again (at most 2 times).
8. Update memory/leads-log.md: date | business | stage | next step.

Output:
```
REPLY: <message text>
FORMAT: voice | text
VOICE_SCRIPT: <text sent to ElevenLabs, only if FORMAT is voice>
TEXT_FOLLOWUP: <link or text to send after the voice note, if any>
STAGE: opener|interest|demo_sent|objection|closing|won|lost|dnc
NEXT: <action + time>
ESCALATE: no | yes (<reason>)
```
