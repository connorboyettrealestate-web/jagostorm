# BandLab Vocal Chain + Claude Chrome Extension Playbook

**Brand:** Jagostorm · **Last updated:** 2026-08-02

How to get **radio-ready vocals in BandLab** using the **Claude for Chrome
extension** as the "hands" inside your logged-in browser. This is the knowledge
layer (the numbers, the order, the guardrails) the extension does not reliably
produce on its own.

Sources verified 2026-08-02:
- BandLab effects overview: https://blog.bandlab.com/bandlab-effects/
- BandLab vocal chain order: https://blog.bandlab.com/vocal-chain-order-for-radio-ready-vocals/
- Claude in Chrome limitations: https://www.usecarly.com/blog/claude-in-chrome-limitations/

---

## Part 1 — How the two Claudes actually connect

There are two separate Claude instances. They are **not** wired together, and
no bridge can be built that merges them:

| | What it is | Strengths | Can't do |
| --- | --- | --- | --- |
| **Claude (brain)** | Chat / Claude Code | Knows pro settings, writes exact recipes and scripts | Cannot see or drive your local Chrome |
| **Claude for Chrome (arm)** | Browser extension in *your* Chrome | Navigates BandLab, clicks, picks presets, types values, records/replays workflows | Struggles to drag canvas knobs/faders; won't take irreversible actions without confirmation |

**The bridge = copy/paste.** The brain writes precise instructions (this doc +
the prompt pack in Part 4). You paste them to the extension. The extension
executes in your logged-in browser. That is the whole "patch."

**The one rule that patches the real gap:** never ask the extension to *drag*.
Make it (a) select a **preset**, (b) use a **One Knobs** macro, or (c) **type a
number into a text field**. Those are DOM-reliable; dragging on canvas is not.

---

## Part 2 — The vocal chain (order + starting values)

Signal flows **top to bottom**. Add each as an effect on the vocal track's FX
chain, in this order. Starting points — adjust by ear.

1. **Noise Gate** — clean up room noise/breaths between phrases.
   - Threshold: start **-40 dB** (raise until only the noise cuts, not words).

2. **Subtractive EQ** — remove problems before adding anything.
   - High-pass filter: **80–100 Hz** (kills rumble/plosives).
   - Cut mud: **-3 dB around 250–350 Hz**.
   - Tame harshness if present: gentle **-2 dB around 2.5–4 kHz**.

3. **Compressor #1** — even out the level.
   - Ratio **4:1**, Attack **~20 ms**, Release **~100 ms**.
   - Threshold: aim for **3–6 dB of gain reduction** on the loudest words.

4. **Additive EQ** — add tone after it's controlled.
   - Presence: **+2 dB around 4–5 kHz**.
   - Air: **+2–3 dB shelf at 10–12 kHz**.

5. **De-ess (only if sibilant)** — dip **6–8 kHz** dynamically.

6. **Saturation (optional)** — a touch of warmth/weight. Low mix.

7. **Delay (send, low mix)** — 1/8 or dotted-1/8, synced to tempo, **~10–15%**.

8. **Reverb — LAST** — use **Vocal Verb** (ducks under the vocal so words stay
   clear). Decay **1.2–1.8 s**, wet **~15–25%**.

9. **Mastering** — on the **master bus**, not the vocal track. Apply a Mastering
   preset at the very end and set loudness to taste.

**Shortcut when moving fast:** BandLab **One Knobs** collapse a whole
EQ+comp+reverb chain into a single macro — great for the extension because it's
one control. Use a One Knob for a quick pass, then fine-tune with steps 2–4.

---

## Part 3 — BandLab-specific notes

- **Where effects live:** open the vocal track → open its **FX chain** panel →
  **+ Add effect** → choose from BandLab's built-in effects (EQ, Compressor,
  Reverb/Vocal Verb, Delay, Noise Gate, plus One Knobs macros).
- **Presets** are the extension's best friend — one click, no dragging.
- **Numeric entry:** where an effect shows a value, click the number and type.
- **Mastering:** applied to the whole song on the master; pick a preset and
  adjust output loudness.
- **Auto-Pitch / tuning:** add early (before compression) if used.
- Effect/preset names shift as BandLab updates — have the extension **read the
  current list first** (Part 4, Prompt 1) instead of assuming names.

---

## Part 4 — Chrome extension prompt pack (copy/paste)

### Prompt 0 — Standing rules (paste once at the start of a session)

```
You are operating BandLab in my logged-in Chrome. Follow these rules:
1. NEVER drag knobs, faders, or EQ nodes on the canvas. Instead: pick a
   preset, use a One Knobs macro, or click a value field and TYPE the number.
2. Before any change, take a screenshot and tell me what you see.
3. After any change, read the value back to confirm it applied.
4. Do NOT publish, export, delete, or overwrite anything without asking me
   first and getting a yes.
5. If a control can only be set by dragging, STOP and tell me — I'll do that
   one by hand.
```

### Prompt 1 — Recon (know the UI before touching it)

```
Open my BandLab project [NAME]. Open the vocal track's FX chain. List every
effect currently on it, and for each, list the available presets and which
parameters have a typeable number field. Screenshot it. Don't change anything.
```

### Prompt 2 — Build the chain (feed it Part 2)

```
On the vocal track, add these effects in this exact order and set them by
choosing the closest preset first, then typing these values into any number
fields available. Do NOT drag anything. Confirm each one back to me before the
next:
- Noise Gate: threshold -40 dB
- EQ (subtractive): high-pass 90 Hz; -3 dB at 300 Hz; -2 dB at 3 kHz
- Compressor: ratio 4:1, attack 20 ms, release 100 ms, aim 3-6 dB reduction
- EQ (additive): +2 dB at 4.5 kHz; +2 dB shelf at 11 kHz
- Vocal Verb (reverb): decay 1.5 s, wet 20%
```

### Prompt 3 — Fast pass with One Knobs

```
Add a One Knobs vocal macro to the vocal track. Set it to about 40%. Screenshot
before and after and tell me the exact percentage it landed on.
```

### Prompt 4 — Master + export (asks first)

```
On the master bus, apply a Mastering preset suited to a modern vocal-forward
mix. Show me the result and the loudness. Do NOT export or publish yet — wait
for my go.
```

See [bandlab-presets.md](bandlab-presets.md) for four genre-tuned preset cards
with their own ready-to-paste prompts.

---

## Guardrails

- No credentials, tokens, or account passwords in this repo or in prompts.
- The extension acts as *you*, in your session — keep the "ask before
  irreversible action" rule (Prompt 0 #4).
- Prompt-injection risk: a malicious page can try to hijack the extension. Only
  run it on BandLab tabs you opened; don't let it wander.
- Note the extension can't act behind logins you're not already signed into,
  and on the Pro plan it may run a lighter model in Chrome (quality gap).

## Known-good settings log

_Record what actually worked, per voice/song, so the next session is faster._

| Date | Song / voice | What worked (presets + values) |
| --- | --- | --- |
|  |  |  |
