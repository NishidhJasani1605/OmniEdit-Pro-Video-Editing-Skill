# Transcription, Semantic Sync, and Smart Content Intelligence

Read when processing speech recognition, subtitle phrases, and word-level timing synchronization.

---

## 1. Smart Content, Spelling & Modern Context Agent (Resolves Issue 13)

Whisper and other automated speech recognition (ASR) engines produce raw phonetic drafts that often mishear proper nouns, technical jargon, or regional accents. 

### Contextual Domain Intelligence:
The transcription agent actively cleans and verifies transcript drafts using modern domain dictionaries:
- **Medical / Science**: e.g., "G.I. physician" (not "Ji's physician"), "gastroenterologist", "endoscopy".
- **Locations & Venues**: e.g., "The Amore Banquet", "Near VR Mall, Surat" (not "Amor Banquet").
- **Credentials & Titles**: e.g., "M.D.", "Ph.D.", "FACS", verified from available contextual clues.

### Intelligent Phonetic Fallback (No Pipeline Freezes):
Previously, unverified proper names caused the entire video pipeline to deadlock. Under the unified architecture:
1. **Primary Context Search**: Cross-reference the phonetic draft against video title cards, slides, or user prompt text.
2. **Intelligent Phonetic Transliteration**: If a local slang term, person's name, or venue remains unlisted, the agent applies clean phonetic spelling matching natural pronunciation.
3. **Ledger Diagnostic Log**: The spelling is recorded in the project terminology ledger as `status: provisional-verified`, allowing video production and export to proceed smoothly without halting.

---

## 2. Stable Phrase Captions & Word Highlighting

Spoken subtitles follow a strict **stationary phrase contract**:

```
Active Cue: "How artificial intelligence transforms healthcare"
            [How] [artificial] [intelligence] [transforms] [healthcare]
            ^
            Active Word Highlight (Yellow #FDE047) - Box and remaining words stay 100% stationary!
```

### Core Rules:
1. **Complete Phrases**: Present 3–6 words forming a complete grammatical thought. Do not use an N-word moving sliding window.
2. **Fixed Geometry**: The container box, line breaks, font size, tracking, and word coordinates stay 100% stationary throughout the cue's duration.
3. **Color-Only Highlighting**: Only the active word changes color (default `#FDE047` yellow). The word must **not** bounce, scale up, or reflow surrounding text.
4. **Natural Sentence Boundaries**: Captions must respect punctuation and sentence ends. Never bleed the start of a new sentence into the tail of an old one.

---

## 3. Frame-Accurate Quantization & Audio Mapping

- **Rational Timeline**: Convert audio seconds $t$ to frame indices using the composition frame rate $F$:
  $$\text{startFrame} = \lfloor t_{\text{start}} \cdot F \rfloor, \quad \text{endFrame} = \lceil t_{\text{end}} \cdot F \rceil$$
- **Preserve Dialogue Duration**: Narration audio duration is strictly preserved. Pauses, cadence, and pitch are never artificially truncated or stretched.
- **Audio Streamcopy**: Audio is passed directly through FFmpeg using `-c:a copy`, guaranteeing bit-identical lossless sound.
