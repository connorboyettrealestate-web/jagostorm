# BandLab Vocal Presets (recipe cards)

**Brand:** Jagostorm · **Last updated:** 2026-08-02

Ready-to-apply vocal-chain "presets." Each card lists exact values in chain
order, a fast One-Knobs version, and a **copy/paste prompt** for the Claude
Chrome extension. Rule stays the same: **pick presets / type numbers — never
drag.** Pair with the [Chrome extension playbook](chrome-extension-playbook.md).

Once the extension builds a chain you like, tell it: **"Save this FX chain as a
preset named `<X>`."** After that it's a one-click recall in BandLab.

---

## Preset 1 — Clean Modern Pop (vocal-forward, bright, controlled)

| Step | Effect | Settings |
| --- | --- | --- |
| 1 | Noise Gate | Threshold **-42 dB** |
| 2 | EQ (cut) | HPF **90 Hz**; **-3 dB @ 300 Hz**; **-2 dB @ 3 kHz** |
| 3 | Compressor | **4:1**, attack **20 ms**, release **100 ms**, 4-6 dB GR |
| 4 | EQ (boost) | **+2 dB @ 5 kHz**; **+3 dB shelf @ 11 kHz** |
| 5 | De-ess | only if sibilant, dip **7 kHz** |
| 6 | Delay (send) | 1/8, **12%** |
| 7 | Vocal Verb | decay **1.4 s**, wet **18%** |
| Master | Mastering | modern/universal preset, loud but not clipping |

**Fast version:** One Knobs vocal macro @ **~40%**, then nudge steps 2 & 4.

```
Build a "Clean Modern Pop" vocal chain on the vocal track. Add in this order,
using presets/number fields only (no dragging), confirm each:
Noise Gate -42 dB | EQ: HPF 90 Hz, -3 dB@300, -2 dB@3k | Compressor 4:1,
20ms attack, 100ms release, aim 4-6 dB GR | EQ: +2 dB@5k, +3 dB shelf@11k |
Delay 1/8 12% | Vocal Verb 1.4s 18% wet. Then save it as a preset "Clean Pop".
```

---

## Preset 2 — Rap / Hip-Hop Upfront (tight, aggressive, in-your-face)

| Step | Effect | Settings |
| --- | --- | --- |
| 1 | Noise Gate | Threshold **-38 dB** |
| 2 | EQ (cut) | HPF **100 Hz**; **-4 dB @ 350 Hz**; **-2 dB @ 2.5 kHz** |
| 3 | Compressor | **6:1**, attack **10 ms**, release **80 ms**, 6-8 dB GR |
| 4 | EQ (boost) | **+3 dB @ 4 kHz**; **+2 dB shelf @ 10 kHz** |
| 5 | De-ess | dip **6.5 kHz** if harsh |
| 6 | Compressor #2 | light glue, **2:1**, 2-3 dB GR (optional) |
| 7 | Delay (send) | slap/1/8, **8-10%** |
| 8 | Vocal Verb | short, decay **0.9 s**, wet **10%** (keep it dry) |
| Master | Mastering | loud/hip-hop-leaning preset |

**Fast version:** One Knobs vocal macro @ **~55%**, keep reverb minimal.

```
Build a "Rap Upfront" vocal chain, presets/number fields only, no dragging,
confirm each: Noise Gate -38 dB | EQ: HPF 100 Hz, -4 dB@350, -2 dB@2.5k |
Compressor 6:1, 10ms attack, 80ms release, aim 6-8 dB GR | EQ: +3 dB@4k,
+2 dB shelf@10k | Delay slap 9% | Vocal Verb 0.9s 10% wet. Save as preset "Rap".
```

---

## Preset 3 — R&B / Smooth (warm, lush, silky top)

| Step | Effect | Settings |
| --- | --- | --- |
| 1 | Noise Gate | Threshold **-45 dB** (gentle) |
| 2 | EQ (cut) | HPF **80 Hz**; **-2 dB @ 250 Hz** |
| 3 | Compressor | **3:1**, attack **25 ms**, release **120 ms**, 3-5 dB GR |
| 4 | EQ (boost) | **+1.5 dB @ 4.5 kHz**; **+2 dB shelf @ 12 kHz** (air) |
| 5 | Saturation | subtle warmth, low mix |
| 6 | Delay (send) | dotted-1/8, **15%** |
| 7 | Vocal Verb | lush, decay **2.0 s**, wet **28%** |
| Master | Mastering | smooth/warm preset |

**Fast version:** One Knobs vocal macro @ **~35%**, then push air + reverb.

```
Build an "R&B Smooth" vocal chain, presets/number fields only, no dragging,
confirm each: Noise Gate -45 dB | EQ: HPF 80 Hz, -2 dB@250 | Compressor 3:1,
25ms attack, 120ms release, aim 3-5 dB GR | EQ: +1.5 dB@4.5k, +2 dB shelf@12k |
Delay dotted-1/8 15% | Vocal Verb 2.0s 28% wet. Save as preset "RnB".
```

---

## Preset 4 — Podcast / Voiceover (spoken, broadcast-clean, no reverb)

| Step | Effect | Settings |
| --- | --- | --- |
| 1 | Noise Gate | Threshold **-40 dB** (cut room between sentences) |
| 2 | EQ (cut) | HPF **85 Hz**; **-3 dB @ 300 Hz** (de-mud) |
| 3 | Compressor | **4:1**, attack **15 ms**, release **90 ms**, 4-6 dB GR |
| 4 | De-ess | dip **6.5-7 kHz** (spoken sibilance is common) |
| 5 | EQ (boost) | **+2 dB @ 3.5 kHz** (intelligibility); **+1.5 dB @ 10 kHz** |
| 6 | Reverb | **none** — keep it dry and close |
| Master | Mastering | speech/podcast loudness (consistent, not crushed) |

**Fast version:** One Knobs "spoken/clean" style macro @ **~45%**.

```
Build a "Podcast VO" vocal chain, presets/number fields only, no dragging,
confirm each: Noise Gate -40 dB | EQ: HPF 85 Hz, -3 dB@300 | Compressor 4:1,
15ms attack, 90ms release, aim 4-6 dB GR | De-ess ~7k | EQ: +2 dB@3.5k,
+1.5 dB@10k | NO reverb. Save as preset "Podcast".
```

---

### Notes

- Exact preset/effect names shift as BandLab updates — have the extension run
  the recon prompt first so it maps these steps to what's actually on screen.
- Values are starting points; a screenshot + your ears beat any number.
- Log what worked in the known-good table in the playbook so the next session
  is faster.
