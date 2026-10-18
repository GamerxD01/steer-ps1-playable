# PS1 · "Meri Weight Kahani": a GLP-1 playable ad for steer

© 2026 Chandra Prakash · evaluation prototype · see `LICENSE.txt`

A 60–90 second Hinglish playable for Meta (Reels/Stories → playable). It mirrors the user's diet history, lifts the shame, answers *their* top GLP-1 fears honestly with sources, measures how much the worry dropped, and hands them to a steer doctor on WhatsApp.

## How to open
- **▶ Play it live (phone or desktop):** https://gamerxd01.github.io/steer-ps1-playable/ — hook B: `?hook=4pm` · English: `?lang=en` · lead preview: `?debug=1`
- **Playable:** open `index.html` in Chrome. Use phone view (DevTools → device toolbar, 390×844), or open the file on a phone.
  - `index.html?hook=4pm` opens hook B.
  - `index.html?lang=en` opens the English version.
  - `index.html?debug=1` shows the live lead record the care team receives.
- **Walkthrough:** `WALKTHROUGH.md` (10 annotated screens).
- **Ad creatives:** the `ad-creative/` folder has the Reels video with Hinglish voiceover, plus feed and story images for hooks A and B.

## Target device / browser
Mobile first: Android or iOS phones at 360–430 px width, in Chrome, Safari or the Instagram/Facebook in-app browser. It's a single self-contained HTML file with no login and no install. It also works on desktop Chrome and Edge.

## Completion status
- **Complete, working prototype.** The full flow runs: hook → history → relief → fears → answers → re-rate → snapshot → WhatsApp handoff, plus the sources page.
- It's in Hinglish with an English toggle and has two hooks with matching video creatives.
- It was tested on three full paths in a 390×844 phone viewport.
- **Not done yet:**
  - WhatsApp uses a placeholder number.
  - The lead endpoint and Meta Pixel ID still need steer's real values.
  - It hasn't been deployed as a live Meta ad. The brief says this is optional.

## Trigger · Value · Next step
- **Trigger:** *"Kitni diets try kar chuke ho?"* The user taps their own diet history (keto, jeera paani, "bas ek roti"…) and a live counter cheers them on. It's a mirror, not an ad.
- **Value:**
  - *"Ye aapki galti nahi thi."* Weight loss raises hunger hormones for about a year (NEJM 2011).
  - Two-sided, sourced answers to the user's top 3 fears (regain, safety, "is it for me").
  - A before/after worry score, e.g. "Aapka darr 33% kam hua".
  - A private snapshot using India's own cut-offs (BMI >23, waist 90/80 cm) that can honestly say "you may not need medicine".
- **Next step:** one tap opens a private WhatsApp chat with a steer doctor, with the user's fears and snapshot pre-filled. A callback form is the fallback. The care team gets a warm lead with a suggested opening line.

## Files
| File | What |
|---|---|
| `index.html` | The playable (protected evaluation build) |
| `WALKTHROUGH.md` + `walkthrough/` | Screen-by-screen walkthrough |
| `SOURCES.md` | Every claim and its source |
| `USER-INSIGHTS.md` | The user research behind the design |
| `SUBMISSION.md` | Full write-up: judging criteria, example lead, guardrails |
| `ad-creative/` | Reel videos (with and without voiceover) and feed/story images, hooks A and B |
