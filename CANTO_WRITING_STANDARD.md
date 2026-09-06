# Srimad Bhagavatam Study App — Writing & Build Standard

Paste this at the top of any session that adds a chapter or a canto architecture guide. It is the locked standard for Cantos 6–12. Follow it exactly.

---

## 0. The locked reference

**The voice is Canto 1 Chapter 5 ("Narada's Instructions on Srimad-Bhagavatam for Vyasadeva"). Every chapter and every architecture guide matches it.** When unsure, read that chapter and match its cadence, not a general idea of "devotional writing."

Theological frame: Gaudiya Vaishnava as established by Srila Prabhupada and ISKCON. Krsna is svayam Bhagavan; bhakti is the soul's constitutional nature; the soul is eternal, conscious, individual. Doctrine is demonstrated through narrative, never argued for.

Transliteration: Krsna not Krishna, Bhagavatam not Bhagavata, Prabhupada's romanised spellings, no diacritical marks in running text (e.g. Rsabhadeva, Pariksit, Vaisnava, Visnudutas).

---

## 1. Writing voice — with measurable targets

Warm, devotional, flowing, honest. Not academic, not sentimental, not preachy. Name grief, love, fear, awe directly — never melodramatically.

Cadence is not optional. These are the measured targets from the reference chapter; a section that misses them is not in voice:

- **Average sentence length ≈ 12 words.** If a chapter averages ~20+, it has drifted into literary long-form and must be broken up.
- **Fragments for emphasis — roughly 2 per 100 words.** "Not solemn, not lecturing. Smiling." "Truthful. Clean." "It rises. The fog is gone." Short beats carry the weight.
- **Em-dashes, liberal — roughly 3–4 per 100 words.**
- **Closing italic sentences present throughout** — most sections end on one (see Rule Two).

Never: moralise, hedge, use empty intensifiers, explain a metaphor after using it, or compare Bhagavatam to other traditions unless the text itself does. Avoid the words "genuinely," "honestly," "actually." No bullet points in narrative — ever.

---

## 2. The four unbreakable prose rules

**One — Commentary lives inside the narrative paragraph, not after it.** Never follow a narrative paragraph with a standalone italic or bold paragraph that explains what it just said. Test: if you can delete it and the narrative paragraph still stands complete, the commentary paragraph must not exist.

**Two — Closing italics are part of the voice.** A single italic sentence at the close of a paragraph — the sharpest possible formulation of what the paragraph just demonstrated — is correct and present throughout. It is not commentary. It is the sentence the paragraph was always moving toward.

**Three — Every section opens already inside the moment.** Never announce ("Having described X, we now turn to Y"). Arrive mid-scene. The first line of prose is already at the thing. (A landmark sub-heading may sit above that first line — the label is fine; the prose underneath must still open in the moment.)

**Four — No standalone quote blocks that restate the prose.** A quote block appears only when an exact formulation — a specific image, name, or claim — must stand alone or be lost. Never write a quote block and then a sentence explaining it. It stands on its own or does not appear.

---

## 3. Chapter section format

Each chapter has **4–6 sections, divided by narrative movement, not verse count.** Each section object has four fields:

- **title** — narrative, not theological (e.g. "The Elephant's Bath," "Three Came, and Then Four").
- **texts** — the verse range (e.g. `Texts 9&ndash;19`).
- **gist** — 1–2 sentences describing what the section contains. Descriptive, not theological. Written at creation time. Mandatory for every section. Appears **only in the index screen**, never in the reading view.
- **content** — the HTML string (below).

### Landmark every text group — including the opening one

**This is the rule most often broken. Fix it before saving.** Every section's *first* text group gets its own `Texts X–Y — Label` sub-heading, exactly like the groups after it. Do not fold the opening verses into an unlabeled opening paragraph. When you scan a section's sub-headings top to bottom, the labels must run continuously from the section's first verse to its last, with no gap.

- Wrong: section covers Texts 9–19, first sub-heading is "Texts 11–12." (9–10 look skipped.)
- Right: first sub-heading is "Texts 9–10 — [label]," then 11–12, then 13–15…

The one allowed exception: the **opening section of a new canto** may begin with a single unlabeled bridge sentence that connects explicitly to where the previous canto ended (canto continuity), before its first landmark.

### Content order inside a section

1. Opening paragraph — mid-scene; the first section of a chapter names who is speaking and to whom.
2. `sub-heading` landmarks (Cinzel) for each verse group.
3. Quote blocks — sparingly (see §6).
4. Narrative prose — never bullet points.
5. Sit With This — always last (see §5).
6. SAP toggle — below Sit With This, only when SAP content exists (second pass).

### Second person

Second person ("you," "your") appears **only in character dialogue and in the Sit With This.** The narrative body stays third person. No "Hold that picture in your mind," no generalized "you would fail the way you…" in narration — recast to third person.

### Exact HTML patterns

Sub-heading:
```
<p class="sub-heading">Texts 9&ndash;10 &mdash; Pariksit's Objection</p>
```

Quote block (paraphrase, under 15 words):
```
<div class="quote-block"><p>Such a soul never meets the men of death &mdash; not even in a dream.</p></div>
```

Sit With This (icon `&#x1F54A;`, closes with 🙏 `&#x1F64F;`):
```
<div class="sit-with-this"><div class="sit-title">&#x1F54A; Sit With This</div><p>…question…? &#x1F64F;</p></div>
```

Use `&mdash;` for em-dashes, `&ndash;` for en-dashes in ranges, `<em>…</em>` for italics. Straight apostrophes are fine inside backtick `content` strings; in double-quoted `title`/`gist` fields use `&rsquo;` for apostrophes.

---

## 4. Content coverage standard

Every verse or small verse group must be addressed in the section that covers it. Before writing a section: (1) note what each verse contains; (2) write; (3) confirm every distinct image, name, event, argument, or turning point is present in the prose. Thin/transitional verses fold into the nearest paragraph. Substantive verses get their own treatment. The check is never "how many headings?" but: read the source verses, read the section — is everything there?

---

## 5. Sit With This

One at the end of every section. Begins from a **specific moment or image** in that section — not a general principle. Asks a genuine question, not rhetorical. Speaks directly as "you." Connects the ancient text to present-day lived experience. One question is better than two; two is the maximum. Conversational — like a real question from a friend who has just been in the text with you. Ends with 🙏. Never moralises.

---

## 6. Copyright / paraphrase

- All verse content is paraphrased in original wording. **Never quote Prabhupada's translations or purports verbatim**, and never echo his distinctive phrasings (e.g. do not reuse "a reservoir of good character" — reword it).
- Quote blocks are paraphrases: **under 15 words, one per source, at most 2 per chapter, standalone.**
- The Vedabase link is the app's pointer to the originals — generated automatically per canto by `setVedabaseLink(cantoNum, ch.num)`, pointing to `vedabase.io/en/library/sb/{canto}/{chapter}/`.

---

## 7. Architecture guide format (per canto) — match Canto 1

**The architecture guide is a full multi-section guide, not one paragraph.** It maps the whole canto (all chapters), in the same voice as the chapters, and uses **CSS variables only — never hardcoded hex.** Structure:

**Intro box** — italic, orienting the reader to the canto's real design:
```
<div style="background:var(--bg-darker);border-left:4px solid var(--maroon);padding:20px 24px;margin-bottom:28px;font-size:19px;line-height:1.85;color:var(--text-mid);font-style:italic;">…</div>
```

**Section 1 — The Overall Design.** The canto broken into its movements, one full explanatory paragraph each, under `sub-heading` labels. Use the standard section-block shell:
```
<div class="section-block">
  <div class="section-header" style="cursor:default;">
    <div class="section-num">Section 1</div>
    <div class="section-name">…</div>
    <div class="section-texts">…</div>
  </div>
  <div class="section-body" style="display:block;">…</div>
</div>
```

**Section 2 — Chapter by Chapter: The Thread.** One "The Connection" card per major transition — dense enough to trace the canto's spine end to end (Canto 1 has ~11; match that density where the narrative supports it, never with filler). Each card:
```
<div style="margin:20px 0;padding:14px 18px;background:var(--bg-darker);border-left:3px solid var(--gold);">
  <div style="font-family:Cinzel,serif;font-size:10px;color:var(--gold-dark);letter-spacing:0.16em;text-transform:uppercase;margin-bottom:6px;">The Connection</div>
  <div style="font-size:17px;font-weight:700;color:var(--gold-dark);font-family:EB Garamond,serif;margin-bottom:8px;">Chapter X &rarr; Chapter Y</div>
  <p>…full paragraph, in voice, ending on a strong beat…</p>
</div>
```

**Section 3 — The Single Thread.** The one argument running under the whole canto, opened with a centered thesis box:
```
<div style="margin:0 0 20px;padding:16px 20px;background:var(--bg-darkest);border:1px solid var(--border);font-style:italic;font-size:19px;color:var(--text-mid);">…the thesis…</div>
```

**Section 4 — The Crescendo Finale.** The canto's structural "aha," built like Canto 1's "Arrow and the Target": `sub-heading` landmarks, at most one paraphrased quote block (under 15 words), a centered landing line, and an inline italic closer:
```
<div style="margin:20px 0;padding:16px 20px;background:var(--bg-darkest);border:1px solid var(--border);font-style:italic;font-size:19px;color:var(--text-mid);text-align:center;">…the line that lands…</div>
```

Each canto uses its **own** `archNContent` block — never reuse another canto's.

---

## 8. Design, technical & build rules

**Palette (locked, never changes):** `--bg #e9c89a`, `--bg-darker #deba85`, `--bg-darkest #cb9356`, `--maroon #9c2a18`, `--maroon-dark #7a1e10`, `--gold #835627`, `--gold-dark #6a4418`, `--text #060302`, `--text-mid #2a1508`, `--text-muted #6a4520`, `--border #c8a060`, `--border-light #d8b878`. **Fonts:** EB Garamond (body/narrative/quotes/SAP) and Cinzel (labels/headers/nav). **Never hardcode hex — always use the CSS variables.**

**Script-safety rules:**
- Total backtick count in any file must be **even** (backtick parity).
- No backtick nesting; SAP strings use string concatenation, not template literals.
- `.section-block` must **not** have `overflow:hidden`.
- SAP toggle `onclick` must include `event.stopPropagation()`.
- All SAP paragraph CSS uses `!important` to override the `.section-body p` rule.

**New-canto setup checklist (do before adding any chapter):** new `cantoXChapters` array; dedicated `#cantoXhome` screen; `openCXChapter`; `renderCantoXHome`; wire the canto-card `onclick`; update `goHome`; give the canto its own `archXContent` and wire it into `openArchitecture`; add `renderIdxCantoX` rendering into a dynamic placeholder `<div id="idx-cantoX-block">` (never static HTML); update `getCantoChapters`, `findChapterTarget`, `goToChapter`, `renderChapterNav`; confirm `setVedabaseLink(X, ch.num)` is called in the chapter-opening function (one call covers every chapter in the canto).

**Deliverable / build architecture (this is what caused the repeated "cantoN is not defined" errors — get it right):**
- The **GitHub deliverable is a single combined `index.html`** with all canto data inlined in **one** `<script>` block. Separate `<script src="cantoN.js">` tags fail in the in-chat preview and in some sandboxes because top-level `const` bindings are not shared across `<script>` blocks — so everything goes in one block.
- Keep the multi-file sources (`index_multifile.html` shell + `cantoN.js`) as the working copies, edit those, then **regenerate the single-file** by inlining all `cantoN.js` into the shell's one script block.
- Verify the single file has: 0 external `src="canto"` refs, exactly 1 `<script>` block, array definitions before first use, and that it passes a JS syntax check.

**Validation before every save:**
1. Backtick parity even: `python3 -c "c=open('FILE').read();print(c.count(chr(96)), 'EVEN' if c.count(chr(96))%2==0 else 'ODD')"`
2. `node --check` on the canto file and on the extracted single-file script block.
3. Coverage check: read the source verses, read the section — is every distinct item present?
4. Landmark check: every section's first sub-heading starts at that section's first verse.
5. Style check: every section opener is mid-scene; no explanatory paragraphs; no explained quote blocks; no reader-address in narrative bodies (only dialogue + Sit With This).
6. Cadence check: average sentence length near 12 words, fragments present.
7. Save a timestamped backup before each change: `cp index.html index_pre_[desc]_YYYYMMDD_HHMMSS.html`.

---

## 9. SAP framework (second pass — after the story layer for all cantos is done)

Per section, keyed by canto/chapter/section index (0-based) in a separate `sapContent` object:
- **Sambandha** (relationship) — 2–3 paragraphs + a centred italic Key Insight; maroon pill, bg-darker body → nested bg-darkest for the Key Insight.
- **Abhideya** (practice) — ends with **Today's Practice**: one specific, doable thing, gold left border, italic; gold pill, bg body.
- **Prayojana** (fruit) — 1–2 paragraphs; gold-dark pill, bg-darkest body.

---

## 10. Per-chapter workflow

1. Source for the chapter is provided first — do not write from memory.
2. Timestamped backup.
3. Write to this standard: mid-scene openers, every text group landmarked, punchy cadence, quote blocks sparing, one Sit With This per section, all verse content covered, no reader-address in narrative, no verbatim/echoed Prabhupada phrasing.
4. Run the full validation checklist.
5. Regenerate the single-file `index.html`; keep sources in sync.
6. Present the file(s).

---

## 11. App architecture reference (screens, cards, index, SAP object)

**Five screens:** `#cantos` (master canto grid — the opening screen), `#cantoXhome` (per-canto chapter list, one per canto), `#chapter` (breadcrumb + accordion), `#architecture` (the static guide of §7), `#index` (study index).

**Master screen (`#cantos`):** a hero header — *om namo bhagavate vasudevaya*, the app title, the mantra line, and a ☰ Index button — above a canto-card grid.

**Canto cards:** header = canto number + name; body = chapter count + one-line description + a badge. Badges: `badge-complete` (maroon), `badge-progress` (gold-dark), `badge-coming` (grey). A progress bar shows *X of 335* chapters complete. A card becomes clickable (`class="available"` + `onclick="openCanto(X)"`) once its canto is set up.

**Index screen (`#index`):** reached via ☰ Index. All 12 cantos as an expandable accordion — canto → chapters → sections. Each section row shows title (Cinzel), verse range (small caps), gist (italic EB Garamond). Rendered dynamically: one `renderIdxCantoN` per canto, each calling the shared `renderIdxCantoGeneric(blockId, cantoNum, cantoName, chapters)`, which reads `s.gist` into an `idx-sec-gist` span. Every canto's block is a dynamic placeholder `<div id="idx-cantoN-block">` filled by its function — **never static HTML.** Coming cantos are non-expandable. The index is a study map — **no SAP, no Sit With This appears here.**

**SAP object:** SAP lives in a separate `sapContent` object keyed by **canto → chapter → section index (0-based)** — never inline in the section content. (Added in the second pass; see §9.)

---

**Progress state to maintain:** update the canto card ("N of M complete"), the master progress band ("Cantos … complete · Canto X in progress · N of 335 chapters"), and the progress-bar fill width (N/335) with every chapter added. Total chapters across the twelve cantos = 335.
