# PS1 — "Meri Weight Kahani" · playable ad prototype for steer

> © 2026 Chandra Prakash. Evaluation prototype built for steer. See `LICENSE.txt`. Not licensed for production use.

**Start here:** `USER-INSIGHTS.md` — the research this ad is built on.

## The insight that shaped everything

> **They don't lack information. They lack permission and trust.**

Indians living with excess weight report some of the highest stigma in the world:
- 49% often feel seen as "lazy".
- 82% avoid social or romantic activities.
- 75% still believe diet and exercise alone should fix it.

(Ipsos, 2026, India.) Every failed diet feels like *their* failure. GLP-1 then arrives wrapped in hype ("Mounjaro brides"), judgment ("it's cheating") and confusion (50+ cheap generic brands since March 2026). Two-thirds of users hide their treatment.

So a myth-busting quiz alone won't move them. The ad follows the order the psychology needs:

**mirror their story → lift the shame → answer fears honestly → make it personal → a small, private next step.**

## The three one-liners

- **Trigger:** *"Kitni diets try kar chuke ho?"* Everyone has an answer. They tap their own history (keto, GM diet, jeera paani, "bas ek roti", the gym membership they barely used) and a counter cheers them on. It's a mirror, not an ad.
- **Value:**
  - Relief first: *"Ye aapki galti nahi thi."* The body raises hunger hormones after weight loss, and they stay raised for a year.
  - Then honest, two-sided answers to *their* top 3 GLP-1 fears, every one sourced.
  - They **rate each fear before and after**, and see it drop. For example: "Aapka darr 33% kam hua".
  - An optional private **"doctor's-eye snapshot"** using India's own BMI and waist cut-offs. It can honestly say "you may not need medicine at all".
- **Next step:** one tap opens a **private WhatsApp chat with a doctor**, with their fears and snapshot already typed in. No obligation; "if it's not right for you, they'll say so." A callback form is the fallback, and "just show me sources" is always an exit.

## What's submitted

| File | What it is |
|---|---|
| `index.html` | The playable (mobile, no login, Hinglish-first with an English toggle). This is the protected evaluation build. |
| `index.html?hook=4pm` | **Variant B hook:** "4 baje phir se bhook kyun lagti hai?" It flows into the same fear-and-answer journey. |
| `index.html?debug=1` | Shows the **live warm-lead record** the care team receives, as you play. |
| `ad-creative/A-diets-*` | Ad creative for hook A: an 8.5s Reels/Stories video plus feed, story and thumbnail images. |
| `ad-creative/A-diets-reel-9x16-voiceover.mp4` | The same reel with a **Hinglish voiceover** (ElevenLabs, warm female voice), re-timed so every visual lands on its spoken line. 14s, mixed to -15 LUFS. Works muted too: every spoken line is also on screen. |
| `ad-creative/B-4pm-*` | Ad creative for hook B, for A/B testing. |
| `USER-INSIGHTS.md` | The research: ranked fears, the psychology behind them, design principles, sources. |

## How each research finding became a feature

| Research finding | Design response |
|---|---|
| Shame and the willpower myth (Ipsos: 49% "lazy", 75% "diet alone should work") | The hook mirrors their effort. The first answer is relief: biology, not willpower (Sumithran, *NEJM* 2011). |
| Fear #1 is regain, fear #2 is "forever" | Answered first and honestly: about 2/3 of lost weight returned within a year of stopping. Then: plan the exit before starting. |
| Sceptics distrust one-sided claims | Every answer is two-sided ("Haan, aksar wapas aata hai. Ye sach hai."). Safety names real side effects and who shouldn't take it. |
| Two-thirds hide treatment; fear of judgment | Nothing leaves the phone until they press send. Private WhatsApp. "Doctor ke saath baat private rehti hai." |
| "Is it even for me?" plus Indian thin-fat bodies and PCOS | A snapshot using India's BMI >23 and waist 90/80 cm cut-offs, family diabetes and PCOS flags. It can say "no". |
| Generic flood, trust gap | A dedicated fear card: "Sasta ho gaya hai. Par bina doctor ke nahi." |
| Low protein in Indian diets makes muscle loss worse | Muscle answer: protein from dal, dahi, paneer, eggs, chana, plus strength training. |
| They're tired of being sold to | No drug names, no promises, and an honest "you may not need medicine" outcome. |

## Judging criteria

| Criterion | How we address it |
|---|---|
| **Hook (25%)** | An identity question everyone can answer in one tap, with no wrong answer. Hinglish-first. Two hooks (diet mirror, 4pm hunger) with matching video creatives, ready to A/B test on Meta. The question lands in the first 0.5s of the video. |
| **Value (25%)** | Relief, then honest answers to *their* fears, then a measured drop in worry, then a personal snapshot plus the exact tests a doctor would order. Useful even if they never talk to steer. Core path is about 60s; the snapshot adds about 20s and is optional. |
| **Scientific accuracy (20%)** | 15 sources: *NEJM*, *Lancet D&E*, *JAMA Netw Open*, the FDA label, Ipsos, ICMR-INDIAB, the India Obesity Commission. Every card shows its source, and charts are labelled "illustration". Thresholds match India's guidance exactly (BMI >23, waist 90/80 cm). |
| **Fun (15%)** | Tap-your-history chips with a live counter and reactions ("Asli koshish 💪", "Respect 🫡"), animated charts, worry meters, before/after bars with confetti, and a savable snapshot image. |
| **Handoff (15%)** | WhatsApp-first, pre-filled with fears and snapshot. The lead record includes diets tried, the weight-history outcome, each fear's before→after score, which fears are "still unsure", snapshot flags, language, and a **suggested opening line for the care manager** ("Lead with empathy: not their fault…"). Leads are marked hot, warm or cool. |

## Example lead (what the care team receives)

```json
{
  "hook_variant": "diets", "channel": "whatsapp", "preferred_language": "hinglish",
  "story": {"diets_tried": ["keto","if","jeera","oneroti","gym"], "weight_history": "regain"},
  "fears": [
    {"fear": "regain", "before": 5, "after": 3, "reaction": "got"},
    {"fear": "safety", "before": 4, "after": 4, "reaction": "doubt"},
    {"fear": "forme",  "before": 3, "after": 1, "reaction": "got"}
  ],
  "fear_drop_pct": 33,
  "snapshot": {"bmi": 27.2, "waist": "80", "flags": ["famdm","pcos"], "flag_count": 4},
  "lead_temperature": "hot",
  "suggested_call_opener": "Tried 5 approaches (…), outcome: regain. Lead with empathy: not their fault. Fears (before→after): regain 5→3; safety 4→4 (still unsure); forme 3→1. Snapshot: BMI 27.2, waist 80, famdm/pcos. Speak Hinglish/Hindi. Respect privacy."
}
```

The first call starts with "aapka safety wala doubt", not "what is GLP-1".

## Claims → sources

| Claim | Source |
|---|---|
| After weight loss, hunger hormones rise and "full" hormones fall, still so ~1 year later | Sumithran P et al., *NEJM* 2011, doi:10.1056/NEJMoa1105816 |
| 49% of Indians living with obesity often feel seen as lazy | Ipsos Global Perceptions of Obesity, 2026 (India n=1,000) |
| About 2/3 of lost weight regained within a year of stopping | Wilding JPH et al., STEP 1 extension, *Diabetes Obes Metab* 2022, doi:10.1111/dom.14725 |
| Most common side effects GI (nausea, diarrhoea, constipation), mostly mild–moderate and transient; some discontinue | Wilding JPH et al., STEP 1, *NEJM* 2021, doi:10.1056/NEJMoa2032183 |
| Pancreatitis and gallbladder disease risks; contraindicated with personal/family history of MTC or MEN 2; stop before planned pregnancy | US FDA prescribing information, semaglutide 2.4 mg (2025) |
| ~¼ of diet-induced weight loss is lean mass; 25–40% in GLP-1 trials | Heymsfield SB et al., *Obes Rev* 2014 · STEP 1 DXA · Jastreboff AM et al., SURMOUNT-1, *NEJM* 2022 |
| 60% of urban Indians don't regularly eat protein-rich food | LocalCircles × Country Delight survey, 2026 (self-reported) |
| ~8 in 10 judged users told "easy way out"; 2 in 3 hide treatment | Simple Online Pharmacy UK survey, 2026, via EMJ |
| GLP-1 is a gut hormone that signals fullness; medicines mimic it | Drucker DJ, *Cell Metab* 2018 |
| Obesity in Asian Indians: BMI >23; waist ≥90 cm men / ≥80 cm women | Misra A et al., *Diabetes Metab Syndr* 2025, doi:10.1016/j.dsx.2024.102989 |
| ~4 in 10 Indian adults have abdominal obesity | Anjana RM et al., ICMR-INDIAB, *Lancet Diabetes Endocrinol* 2023 |
| PCOS in 7–20% of Indian women aged 18–40, often with obesity | Ganie MA et al., *JAMA Netw Open* 2024 |
| Semaglutide patent expired in 2026, 50+ brands; "suspiciously low price… red flag" | Outlook Business, 2026 |
| (Hook B) Post-meal glucose dips → more hunger, ~312 kcal more over the day | Wyatt P et al., *Nature Metabolism* 2021 |

## Guardrails
- No drug or brand names in the experience.
- No before/after bodies, no kilos or timelines.
- No fear or shame tactics.
- "Not a diagnosis" on the snapshot, and an explicit "you may not need medicine" outcome.
- steer brand kit throughout. A tiled author copyright watermark is on every screen.

## Tools used
- HTML/CSS/vanilla JS, built with Claude (Anthropic) as research and coding assistant.
- Tested in headless Chromium (Playwright) at a 390×844 phone size: three full paths, the language switch mid-flow, and edge cases.
- Ad creatives: an HTML/SVG animation rendered frame-by-frame with Playwright and encoded with ffmpeg. Voiceover: ElevenLabs (eleven_v4); pauses trimmed and the animation time-warped to the voice.
- Protection: javascript-obfuscator, html-minifier-terser, author watermark, build fingerprint and domain lock.

## 2-minute Loom script
1. **(0:00–0:20) The insight.** "Steer's audience doesn't lack information. They lack permission and trust. Ipsos: half of Indians with obesity feel called lazy, and two-thirds of GLP-1 users hide it. So I built the order their psychology needs."
2. **(0:20–0:40) Hook.** Play the A video. Then, in the playable, tap diets: "Everyone has an answer to this. It's a mirror, not an ad." Pick "wapas aa gaya". "First thing they hear: ye aapki galti nahi thi. With the NEJM study behind it."
3. **(0:40–1:15) Value.** Pick 3 fears and rate them. Show the honest regain answer: "We say the uncomfortable truth, because sceptics trust two-sided answers." Re-rate. "Their worry dropped 33%. That's value we can measure." Show the snapshot: India cut-offs, the tests a doctor would order, and "the answer may be no".
4. **(1:15–1:45) Handoff.** Tap WhatsApp: the message is pre-written. Open `?debug=1`: fears before and after, which ones are still unsure, snapshot flags, and a suggested opener. "The care manager's first call starts at their real doubt."
5. **(1:45–2:00) Scale.** "Two hooks with creatives ready to A/B test. The same file is the website entry point. Hinglish and English. Every claim sourced."
