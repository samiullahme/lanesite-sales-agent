# Voice notes with ElevenLabs: natural, not dramatic

Goal: it should sound like a normal young Pakistani shopkeeper or businessman recording a quick WhatsApp voice note. It should not sound like an actor or a radio ad.

## Settings (set once in the backend, not by the agent)
- Model: `eleven_v3` (the only model that supports audio tags). Voice notes don't need to be real-time, so v3's slower speed is fine.
- Stability: **Natural, ~0.5–0.6**. Below 0.4 it gets dramatic and can make strange sounds. At 0.75 or above it sounds flat, like reading a book.
- Similarity: ~0.75. Style: 0. Speed: 1.0 (0.95–1.05 at most).
- Use one fixed voice for every lead, so it's always the same "person".
- Generate 2 takes and send the better one. v3 output varies from take to take.

## Script vs Roman
- Test both with your voice. Urdu script (اردو) usually sounds more correct than Roman Urdu. Brand names stay in English: "LaneSite", "website", "link".
- Write numbers as words: "paanch hazaar" / "پانچ ہزار", not "5000" or "Rs.5k".
- Don't use emojis, URLs, ALL CAPS, or abbreviations (Rs, PKR, etc.) in voice text. Send the link in a separate text message.

## Making it sound human (these matter more than tags)
1. **Spoken language, not written.** Use short pieces with natural joins: "acha", "dekhein", "matlab", "to", "ji". At most one or two per note.
2. **Punctuation controls rhythm.** A comma is a short pause, "..." is a thinking pause, a full stop finishes a thought. Don't use "!!".
3. **A small imperfection helps:** an occasional "umm" or a restart ("main ne... matlab aapke liye") at most once per note.
4. **Keep the energy at a calm, normal-conversation level.** No sales excitement.

## Audio tags (v3): use rarely
Allowed, at most **one tag per note**, and only where the words already support it:
- `[warmly]`, a friendly greeting at the start
- `[softly]`, when apologising or ending politely ("koi baat nahi")
- `[chuckles]`, a light laugh, only if the customer joked or said something light
- `[thoughtful]`, before answering a tough question
- `[short pause]`, a natural break

Never use: `[excited]`, `[shouting]`, `[laughs]` / `[laughing]` (too big), `[whispers]`, `[crying]`, `[sarcastic]`, or accent tags. Never stack two tags.

## Example
Bad (dramatic):
`[excited] Assalam o Alaikum!!! Aapke liye ZABARDAST offer hai!`

Good (human):
`[warmly] Assalam o Alaikum... ji, {business_name} ka page dekha tha. Acha, ek baat poochni thi, shaam ko inbox mein log zyada tar menu aur price hi poochte hain na?`

## Honesty (unchanged)
Sounding natural is the goal. Lying is not. If someone asks "aap AI ho?", say yes, as rules.md says.
