# Voice Leader

An interactive SATB (soprano/alto/tenor/bass) voice-leading trainer. Pick a key and a chord progression, place each voice's notes on the staff, and get checked against the standard rules of four-part writing — the same way a theory instructor would mark it.

## What it does

- **Pick the key from a circle of fifths.** Majors on the outer ring with their accidental counts, relative minors inside; click a wedge to choose the key and the mode in one move, and the hub spells out the signature. The six o'clock wedge carries the enharmonic pair — click it again to flip F♯/G♭ or D♯m/E♭m. Minor automatically raises the leading tone in V and vii°, no manual accidentals needed.
- **Build a progression.** Chain together any of the seven diatonic triads — I ii iii IV V vi vii° in major, i ii° III iv V VI vii° in minor — in whatever order you want, up to eight chords. Each numeral shows its own spelling in the current key before you add it, and presets cover the common shapes (I–IV–V–I, ii–V–I, I–V–vi–IV).
- **Place notes directly on the staff.** Hover near the correct system and a faded preview snaps to the nearest valid pitch; click to drop it in. Already placed a note? Click and drag it to a different valid position.
- **Real notation.** Actual treble and bass clefs, correct key signature for whichever key you picked, and notes automatically render on whichever staff keeps ledger lines to a minimum (a voice that dips below or climbs above middle C crosses to the other staff rather than piling up ledgers).
- **Full checklist, every chord:**
  - All three chord tones present, and what's doubled
  - Spacing between adjacent voices (nothing wider than an octave)
  - Leading-tone resolution — including the doubled-leading-tone exception (one copy resolves up, the other drops to the fifth)
  - True parallel fifths and octaves against the previous chord, checked across all six voice pairs
- **Parallel motion, visualized.** If a chord introduces a parallel fifth or octave, red animated lines draw themselves across the staff tracing exactly which two voices moved in lockstep.

## How to use it

1. Pick a tonic and major/minor.
2. Tap the chord chips to build your progression, then **Begin voicing**.
3. For each chord, select a voice tab and place its note (hover + click, or drag an existing note to change it).
4. **Confirm chord** to run the checklist. Fix and re-check, or move on to the next chord.
5. At the end, start a new progression to try another key or shape.

## Scope

Root-position triads only. All seven diatonic degrees are available; in minor, V and vii° raise the leading tone and the rest stay diatonic to the natural minor scale. No inversions or seventh chords yet.

## Tech

Single self-contained HTML file. No build step, no external services — just open it in a browser. All rendering is hand-drawn SVG (staff, clefs, noteheads, key signatures); all the theory (scales, chord spelling, the rule checks) is plain JavaScript with no external libraries.
