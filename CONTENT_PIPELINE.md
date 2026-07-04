# AI Video Content Pipeline — Fooocus-Powered YouTube Playbook

> Working playbook for producing YouTube **Shorts** now, expanding to **5–15 min episodes** later,
> using **Fooocus** as the image engine. Built for a starting budget of **~$0–15/month** on a
> Mac/laptop, scaling hardware only when revenue justifies it.

---

## 0. The one thing to remember

**Fooocus makes still images, not video.** Your video is built by:

```
Script  →  Voiceover  →  Images (Fooocus)  →  Motion  →  Edit + Captions  →  Publish
```

For now, "motion" = panning/zooming still images (Ken Burns) + a few true image-to-video
clips where a shot genuinely needs to move. True per-frame AI animation is a later, paid upgrade.

---

## 1. Strategy: test BOTH looks, cheaply

We are trying things out, so produce a small batch in **each** style and let watch-time decide.

| | **Anime / Cartoon** | **Semi-Realistic Illustrated** |
|---|---|---|
| Best for | Stories, mythology, fiction, "storytime", explainers with characters | Documentary, facts, history, drama, reaction/commentary |
| Hides AI flaws? | Excellent — stylization reads as intentional | Good, as long as you avoid full photoreal faces |
| Character consistency | Easiest | Medium |
| Fooocus preset | `run_anime.bat` | `run_realistic.bat` |
| Risk | Niche audience if too generic | Uncanny-valley if pushed toward photoreal |

**Rule of thumb:** the more stylized, the more forgiving the tech. Only go fully photoreal for
specific hero shots once the channel is earning.

---

## 2. Phase plan (spend follows proof, never precedes it)

### Phase 1 — Shorts, NOW (~$0–15/mo, your current Mac/laptop)
- Produce **20–30 Shorts** split across both styles.
- Everything runs on hardware you already own (Fooocus via Mac MPS, or free/cheap Colab).
- Goal: find which style + topic gets watch-time. Buy **nothing**.

### Phase 2 — Add selective true motion (still ~$0–30/mo)
- Once a style is working, use **cloud image-to-video free credits** (Kling / Luma / Hailuo)
  for the 2–3 shots per video that need real movement.
- Still no hardware purchase — pay per clip only.

### Phase 3 — Episodes, ONLY once earning
- 5–15 min episodes make cloud per-clip fees add up. *Now* a GPU pays off.
- Buy a **used NVIDIA RTX 3090 24GB (~$700–900)** or **4090 (~$1,600)** for local image +
  local video generation (Wan / Hunyuan Video).
- Trigger to buy: you're spending **more on cloud video per month than the GPU costs**, OR
  episode volume makes local batch generation a real time-saver.

**Do not skip to Phase 3.** Buying a GPU before the channel earns is the #1 money-losing mistake.

---

## 3. The tool stack (all Mac-compatible)

| Step | Primary tool | Cost | Backup / notes |
|---|---|---|---|
| Script | Claude / ChatGPT | free–$20/mo | You already have the content plan |
| Voiceover | **Kokoro TTS** (free, local) | $0 | **ElevenLabs** ($5–11/mo) for premium voices |
| **Images** | **Fooocus** | free | Mac MPS (~1–3 min/image); **Google Colab Pro** ($10/mo) if too slow |
| Motion (stills) | **CapCut** keyframe zoom/pan | free | DaVinci Resolve also free |
| True motion (select shots) | Kling / Luma / Hailuo free credits | $0 to start | Only when a shot must move |
| Edit + captions | **CapCut** or **DaVinci Resolve** | free | Auto-captions boost retention |
| Thumbnails | **Fooocus** (16:9) | free | Same engine, different aspect ratio |

---

## 4. Fooocus setup

### Install / launch
- **Anime track:** launch with the **anime preset** (`run_anime.bat`, or `--preset anime`).
- **Realistic track:** launch with the **realistic preset** (`run_realistic.bat`, or `--preset realistic`).
- On Mac: run via the standard install; generation uses Apple MPS (slower but works).
- On Colab: use the official `fooocus_colab.ipynb` with
  `!python entry_with_update.py --share --always-high-vram --preset anime` (or `realistic`).

### Aspect ratios
- **Shorts:** 9:16 (vertical) — set in Advanced → Aspect Ratios.
- **Episodes / thumbnails:** 16:9 (horizontal).

### Features you'll use most
- **Styles** — lock one style across a whole series so every video matches.
- **Image Prompt** — feed a reference image to keep a character consistent shot-to-shot.
- **FaceSwap** (Image Prompt → Advanced) — keep a character's face identical.
- **Inpaint / Outpaint** — fix a hand, extend a scene to fill the frame.
- **Upscale (2x)** — sharpen final frames before editing.

---

## 5. Commercial-safe checkpoints (verify current license before selling output)

Because YouTube monetizes your output, only use checkpoints whose license permits **commercial
use of generated images**. Always re-check the model's license page before relying on it.

**Semi-realistic:**
- **Juggernaut XL** — commercially friendly, strong all-rounder.
- **RealVisXL** — photoreal-leaning, permissive.
- **DreamShaper XL** — versatile semi-real/illustrated.

**Anime / cartoon:**
- **Fooocus built-in anime preset model** — ships with the anime edition.
- **Animagine XL** — popular, high quality; confirm license terms for commercial output.
- Avoid checkpoints whose Civitai license restricts selling generations or hosting the model.

> Rule: if a model's license page restricts commercial use of outputs, don't build a monetized
> channel on it. When unsure, prefer Juggernaut XL (real) and the built-in anime model (anime).

---

## 6. Character consistency (the make-or-break for episodes)

Shorts tolerate loose consistency; episodes do not. Build the habit now:

1. **Design the character once** in Fooocus and save the seed + prompt + style.
2. Save 2–3 clean reference images per character.
3. For every new shot, use **Image Prompt** with the reference + **FaceSwap** for the face.
4. Keep a **character sheet** (prompt, seed, style, reference files) per character.
5. Later (Phase 3): train a **LoRA** per main character for locked consistency.

Keep the **Style** setting identical across every shot in a series so lighting/linework/palette match.

---

## 7. Per-video production checklist

```
[ ] Script written + hook in first 2 seconds
[ ] Voiceover generated (Kokoro/ElevenLabs)
[ ] Shot list: 1 image per ~3–5 seconds of narration
[ ] Style + aspect ratio locked in Fooocus (9:16 Shorts / 16:9 episodes)
[ ] Characters use saved reference (Image Prompt + FaceSwap)
[ ] Images generated + upscaled 2x
[ ] Images imported to CapCut; keyframe zoom/pan added
[ ] (Optional) 2–3 hero shots animated via cloud i2v free credits
[ ] Music + SFX (royalty-free)
[ ] Auto-captions added + styled
[ ] Thumbnail generated in Fooocus (16:9)
[ ] Export 1080p (Shorts 1080x1920)
[ ] Title + description + tags
```

---

## 8. Monthly cost snapshot

| Phase | Monthly cost | What you're paying for |
|---|---|---|
| Phase 1 (Shorts) | **$0–15** | Optional Colab Pro + optional ElevenLabs |
| Phase 2 (+ motion) | **$0–30** | Cloud video credits for select shots |
| Phase 3 (episodes) | one-time **$700–1,600** GPU, then ~free | Local image + video generation at volume |

**Break-even vs. subscriptions:** a used RTX 3060 (~$300) for images, or later a 3090/4090 for
video, beats paying Midjourney/API fees forever — but only buy once volume proves it out.

---

## 9. Honest limitations to plan around

- **SDXL is older.** Great for stylized/photoreal art; **bad at text inside images** (titles,
  signs) and complex multi-object scenes. Add on-screen text in CapCut, not in the image.
- **Fooocus can't do video.** It's the image stage only; motion comes from CapCut or i2v tools.
- **For cutting-edge quality or Flux**, switch the image engine to **Forge** or **ComfyUI**
  (same family, steeper learning curve, needs a strong NVIDIA GPU) — a Phase 3 consideration.
- **The real bottleneck is consistency + workflow speed, not raw image quality.** Systematize
  Section 6 early.

---

## 10. Next actions

1. Install Fooocus; launch the **anime** preset and the **realistic** preset once each.
2. Generate one character + 3 scenes in **each** style (9:16).
3. Cut two 20–30s test Shorts (one per style) in CapCut with narration + motion.
4. Post both; compare retention after ~1 week.
5. Double down on the winning style; repeat Section 7 for volume.
