# Brand Voice & Content Review

> Adapted (modified) from [anthropics/knowledge-work-plugins](https://github.com/anthropics/knowledge-work-plugins) `marketing/skills/brand-review`, Apache-2.0.

Two uses: (1) review a draft before it ships; (2) help the user document their brand voice so every later piece follows it.

## Brand guide source
If the user has a brand guide (e.g. `brand-guide.md` in the project or shared in the chat), use it automatically and say so. If not, ask once whether they have one; otherwise do a general review (clarity, consistency, professionalism) and offer to create a guide with the template below.

## Review dimensions
**With a brand guide**
- Voice & tone — matches the voice attributes? right tone for channel and situation? any inconsistent shifts? quote the sentence and explain
- Terminology — preferred terms used, banned terms absent, product names spelled/capitalised correctly, jargon level fits the audience
- Messaging pillars — supports approved value propositions, claims consistent with approved messaging, doesn't contradict positioning
- Style rules — case in headings, numbers, dates, punctuation, emoji, formatting

**Without a guide**
- Clarity — main message clear in the first paragraph/line; short sentences; logical structure
- Consistency — tone, terms (no synonyms for the same concept), formatting
- Professionalism — typos, awkward phrasing, unsupported claims

**Always check (legal & compliance flags)**
- Unsubstantiated superlatives ("best", "No. 1", "fastest", "only") without evidence
- Health, financial or income claims and guarantees that need disclaimers or are banned
- Comparative claims about competitors that could be challenged
- Regulated sectors (finance, medicine, alcohol, children) needing compliance review
- Testimonials / influencer content without attribution or ad disclosure (local advertising law, platform rules)
- Close paraphrase of others' content, images without rights

## Output
```
## Brand review: [piece]
Basis: brand guide / general review
Verdict: ready / minor edits / needs rewrite

| # | Quote | Issue | Severity (Critical/High/Medium/Low) | Fix (before → after) |
|---|---|---|---|---|

Legal/compliance flags: …
Revised version: [full corrected text, if requested or if edits are many]
```
Severity: Critical = legal risk or factual error; High = off-brand in a way the audience will notice; Medium = inconsistency; Low = polish.

## Brand voice guide template
```markdown
# Brand Voice — [Brand]
Personality: "If our brand were a person, they would be …"
Audience: primary / secondary, what they care about, expertise, how they want to be addressed (ты/вы, tu/vous…)

## Voice attributes (3-5)
### [Attribute, e.g. Approachable]
- We are: friendly, clear, no jargon
- We are not: dumbed-down, over-familiar
- Sounds like: "Here's how to start — it takes five minutes."
- Doesn't sound like: "Yo, even a noob can do it lol"

## Tone by context
| Context | Dial up | Example |
| Launch | confidence, energy | … |
| Outage / bad news | honesty, empathy | … |
| Case study | specifics, credit to the client | … |

## Messaging pillars (3-5)
## Terminology
| Use | Avoid | Note |
## Style rules
Heading case · numbers · date/time format · emoji per channel · exclamation marks · Oxford comma / quotes style for the language
```
Voice spectrums to position the brand: formal ↔ casual · expert ↔ peer · warm ↔ matter-of-fact · technical ↔ simple · bold ↔ calm · playful ↔ serious · cutting-edge ↔ proven. Voice stays fixed; tone shifts the balance by context.
