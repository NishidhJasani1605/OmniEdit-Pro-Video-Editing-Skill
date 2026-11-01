# Dynamic Speech-Synchronized Motion Design

Read when implementing animated text, cards, diagrams, callouts, or transitions. Use visual planning from [visual-planning.md](visual-planning.md) and layout geometry from [layouts-effects.md](layouts-effects.md).

---

## 1. Speech-Synchronized Dynamic Pacing (Calibrated to Real-World Reference)

In professional high-retention video (calibrated against `Dr_Rajiv_AI_Invitation_Premium_Vertical_9x16.mp4`), graphics follow the presenter's natural conversational tempo:

```
Audio Syllable Anchor:  "First..."       "Second..."       "Third..."
                        |                |                 |
Dynamic Animation:      [Card 1 Springs] [Card 2 Springs]  [Card 3 Springs]
                        \---------------------------------------------------/
Persistent Context:     Cards stay visible in a stacked list (Ample Reading Hold)
```

### Dynamic Micro-Transitions (Resolves Issue 6):
When speakers present 3–4 concepts rapidly (e.g., within 4–6 seconds):
- **Responsive 0.15s Spring Animations**: Replace stiff 0.3s fades with snappy 0.15s spring/slide reveals tied to spoken syllable onsets.
- **Persistent Multi-Item Stacking**: Instead of forcing each card to exit before the next arrives (which causes a reading hold deadlock), cards **accumulate into a stacked vertical list**.
- **Cumulative Reading Hold**: The viewer reads all introduced points together throughout the multi-card passage, providing comfortable reading time without forcing unnatural pacing onto the speaker's speech.

---

## 2. Reveal One Small Semantic Unit at Its Spoken Anchor

1. **Semantic Units**: Split complex explanations into discrete items (e.g., single bullet, short headline, or icon badge).
2. **Anchor to Speech**: The first visible frame of a new idea occurs on or immediately after the speaker speaks that specific word or phrase.
3. **Hide Future Information**: Future bullets or answers must not be visible on screen before they are spoken. Pre-revealing future items and then highlighting them later is prohibited.
4. **Stable Captions**: Explanatory cards develop dynamically, while spoken subtitles remain stationary in complete grammatical phrases.

---

## 3. Motion Curves and Continuity

- **Easing Formula**: Smooth, non-overshooting motion ramps use cubic Hermite easing:
  $$u = \text{clamp}\left(\frac{\text{frame} - a}{b - a}, 0, 1\right)$$
  $$\text{ease}(u) = u^2 \cdot (3 - 2u) \quad \text{or} \quad u^3 \cdot (u \cdot (6u - 15) + 10)$$
- **Spring Parameters**: For snappy UI pops and category badges, use spring physics with `mass=1`, `damping=12`, `stiffness=180` for a crisp, responsive feel without excessive bounce.
- **Continuous Handoffs**: When replacing content in the same visual slot, fade the outgoing item completely out before the incoming item appears. Never overprint two readable bodies of text.

---

## 4. Typography, Diagrams, and Callouts

- **Headings & Titles**: Centered inside content boxes based on measured glyph bounds via Pillow (`PIL.ImageFont`).
- **Badges & Pills**: Carried on padded background plates with minimum 24px horizontal padding (scaled to canvas width).
- **Diagrams & Highlights**: Connectors, progress bars, and arrows animate from the same rational frame clock, reinforcing the verbal explanation.
