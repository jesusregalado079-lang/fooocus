# QUICKSTART — Your First AI Short, Start to Finish

> The hands-on companion to `CONTENT_PIPELINE.md`. That doc is the map (where we're going);
> **this doc is the "do this now" walkthrough** to get from zero to your first published Short —
> no coding, no paid tools, no new hardware. Works from a Mac or laptop.

---

## The whole thing needs only TWO tools

1. **Fooocus** (run free in your browser via Google Colab) → makes the images.
2. **CapCut** (free app) → does everything else: voiceover, motion, captions, music, export.

Total time for your first Short: ~1 hour. Total cost: **$0**.

---

## PART A — Run Fooocus in your browser (~10 min, first time only)

1. Go to **colab.research.google.com** and sign in with a Google account (free).
2. **File → Open notebook → GitHub tab.** Paste `lllyasviel/Fooocus` and open **`fooocus_colab.ipynb`**.
3. **Runtime → Change runtime type → choose "T4 GPU" → Save.**
   *(This is the free GPU. Nothing works without it.)*
4. Click the **▶ play button** on the code cell. It installs Fooocus and downloads models —
   **wait 5–10 minutes** (first run only).
5. A link ending in **`.gradio.live`** appears. **Click it** to open the Fooocus screen.

> If it stalls during download, just re-run the cell — the free tier sometimes times out and resumes.

**Note:** Colab sessions are temporary. Closing the tab shuts Fooocus down, and next time you
repeat Part A. Fine for testing; upgrade later (see "Going permanent" below).

---

## PART B — Generate your images (~10 min)

In the Fooocus screen:

1. Tick the **"Advanced"** checkbox (bottom-right) to reveal options.
2. **Advanced tab → Aspect Ratios → pick a vertical `9:16`** ratio (for Shorts).
3. In the **prompt box**, type one scene from your script, e.g.
   `a lone astronaut on a red desert planet, two moons in the sky, cinematic lighting`
4. Click **Generate**. Wait ~1–2 min; two images appear.
5. Change the prompt to the next scene and Generate again.
   **Make 5–6 images** — about one per 3–5 seconds of narration.
6. **Right-click each image → Save image.** Put them all in one folder, e.g. `short1`.

**Test both styles:** use the **preset dropdown** at the top to switch between **anime** and
**realistic**, and generate the same scene in each to compare.

**Consistency tip:** to reuse a character, open **Input Image → Image Prompt**, upload a saved
reference of that character, and generate the new scene — it keeps the look. Add **FaceSwap**
(Image Prompt → Advanced) to lock the face.

---

## PART C — Assemble the Short in CapCut (~20 min)

Download **CapCut** (free; desktop version recommended). Then:

1. **New Project → Import** your `short1` image folder.
2. Drag images onto the timeline in order; set each to ~3–4 seconds.
3. **Voiceover (free, built in):** **Text → add your script as text → "Text to speech" →** pick a
   voice. CapCut narrates it. (Upgrade to ElevenLabs later if you want premium voices.)
4. **Motion:** select a clip → enable **Ken Burns** or add **keyframes** to slowly zoom/pan each
   image so stills feel alive.
5. **Captions:** **Text → Auto captions** — it subtitles your voiceover automatically (big
   retention boost).
6. **Music:** **Audio → Music →** add a royalty-free track; lower its volume beneath the voice.
7. **On-screen title/hook:** add your hook text here in CapCut.
   **Never bake text into the AI image** — SDXL garbles text; overlay it in CapCut instead.

---

## PART D — Export & publish (~5 min)

1. **Export → 1080p, 9:16.** Save the file.
2. **YouTube → Create → Upload.** A vertical clip under 60s is auto-detected as a **Short**.
3. Add a hook title, short description, a few tags. Publish.

Done — a complete Short for $0.

---

## Do it twice

Make **one anime** Short and **one realistic** Short on the same topic. Post both. After ~a week,
check which has better **average view duration / retention** in YouTube Studio. That's your winner —
then repeat this process for volume using the checklist in `CONTENT_PIPELINE.md` (Section 7).

---

## Going permanent (later, when you're posting regularly)

- **Colab Pro (~$10/mo):** faster GPU, longer sessions, less waiting. Easiest upgrade.
- **Install Fooocus locally (free, permanent):** more technical on Mac (needs git + conda/python).
  Ask for the Mac local-install walkthrough when you're ready.
- **Buy a GPU:** only in Phase 3 (episodes), once revenue justifies it — see `CONTENT_PIPELINE.md`
  Section 2.

---

## If you get stuck

- **No `.gradio.live` link / errors:** confirm Runtime type is **T4 GPU**, then re-run the cell.
- **Images look generic:** add detail to the prompt (setting, lighting, mood, camera angle).
- **Character changes between shots:** use **Image Prompt + FaceSwap** with a saved reference.
- **Text in the image is garbled:** expected — add all text in CapCut, not in Fooocus.
- **Colab too slow:** switch to Colab Pro, or generate fewer, higher-value images per video.
