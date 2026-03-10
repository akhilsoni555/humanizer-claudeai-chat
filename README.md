# 🧹 Humanizer Skill for Claude

A Claude skill that removes AI-generated writing patterns and makes text sound natural and human. Built for [claude.ai](https://claude.ai) chat.

Based on Wikipedia's [Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing) guide, maintained by WikiProject AI Cleanup.

---

## What it does

AI-generated text has tells — patterns that appear so consistently they've been catalogued by Wikipedia editors cleaning up LLM-generated articles. This skill teaches Claude to detect and fix all of them.

It goes beyond stripping bad words. For conversational and editorial writing, it also injects personality — varied rhythm, specific details, actual opinions — because voiceless writing is just as obvious as slop.

---

## Patterns covered (26 total)

### Content
1. Undue emphasis on significance and legacy
2. Undue emphasis on notability and media coverage
3. Superficial analyses with -ing endings
4. Promotional and advertisement-like language
5. Vague attributions and weasel words
6. Formulaic "Challenges and Future Prospects" sections

### Language & Grammar
7. Overused AI vocabulary words (delve, pivotal, underscore, tapestry...)
8. Copula avoidance — "serves as" instead of "is"
9. Negative parallelisms ("It's not just X, it's Y")
10. Rule of three overuse
11. Elegant variation / synonym cycling
12. False ranges ("from X to Y")
13. Passive voice stacking *(new in v3.0)*

### Style
14. Em dash overuse
15. Overuse of boldface
16. Inline-header vertical lists
17. Title Case In Headings
18. Emojis in content
19. Curly quotation marks

### Communication
20. Collaborative communication artifacts ("I hope this helps!")
21. Knowledge-cutoff disclaimers
22. Sycophantic/servile tone

### Filler & Hedging
23. Transitional filler — "Moving forward", "In today's landscape", "It's worth noting" *(new in v3.0)*
24. General filler phrases
25. Excessive hedging
26. Generic positive conclusions

---

## How to use

### In claude.ai

1. Go to **Settings → Claude Skills** (or your skills directory)
2. Add the contents of `humanizer-skill-claudeai-chat.md` as a new skill
3. Claude will automatically apply it when you ask to humanize, edit, or rewrite text

### Example prompt
```
Humanize this: [paste your AI-generated text]
```

---

## Behavior

| Situation | What Claude does |
|---|---|
| Text has many AI patterns | Full rewrite with summary of changes |
| Text is already clean | Says so briefly, offers light suggestions |
| Short text (< ~100 words) | Direct rewrite + one-line note |
| Formal / technical / legal writing | Pattern removal only — no personality injection |
| Conversational / editorial writing | Pattern removal + voice and personality added |

The self-audit ("what still makes this sound like AI?") runs internally — Claude fixes remaining tells silently rather than narrating the process.

---

## Changelog

### v3.0.0 (current)
- Added **passive voice stacking** pattern (#13)
- Added **transitional filler** pattern (#23): "moving forward", "in today's landscape", "it's worth noting"
- "Add soul" section now gated to conversational/editorial writing only — no personality injection on formal text
- Self-audit runs internally; only surfaces findings if notable
- Added explicit "no changes needed" case
- Output format now scales to text length (short texts skip the multi-stage output)
- Fixed curly quotes example (was rendering identically to straight quotes)
- Removed duplicate Process section
- Removed dead `allowed-tools` Claude Code frontmatter
- Bumped version 2.2.0 → 3.0.0

### v2.2.0
- Initial public release
- 24 patterns based on Wikipedia's Signs of AI writing guide
- Self-audit loop: draft → AI audit bullets → final rewrite

---

## Reference

- [Wikipedia: Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing)
- [WikiProject AI Cleanup](https://en.wikipedia.org/wiki/Wikipedia:WikiProject_AI_Cleanup)

---

## License

MIT — use freely, contributions welcome.
