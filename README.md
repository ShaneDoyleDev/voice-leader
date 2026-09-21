# Voice Leader

An interactive SATB (soprano/alto/tenor/bass) voice-leading trainer. Pick a key and a chord progression, place each voice's notes on the staff, and get checked against the standard rules of four-part writing — the same way a theory instructor would mark it.

## What it does

- **Pick the key from a circle of fifths.** Majors on the outer ring with their accidental counts, relative minors inside; click a wedge to choose the key and the mode in one move, and the hub draws the signature as notation — a treble clef with its accidentals, not a list of letters. The six o'clock wedge carries the enharmonic pair — click it again to flip F♯/G♭ or D♯m/E♭m. Minor automatically raises the leading tone in V and vii°, no manual accidentals needed.
- **Build a progression.** Chain together any of the seven diatonic triads — I ii iii IV V vi vii° in major, i ii° III iv V VI vii° in minor — in whatever order you want, up to eight chords. Each numeral shows its own spelling in the current key before you add it.
- **Every note can sound.** With **Sound** switched on from the staff toolbar, placing a note plays it on a sampled grand piano, so you hear the voicing as you build it. It starts off; pressing Play switches it on.
- **Wrong notes show in red.** A note that is not one of the chord's three tones draws in red on the staff, so a misplaced voice is obvious before you check anything.
- **The chord spelling keeps score.** Under each Roman numeral sits the chord's spelling; each tone lights up once you have placed it, in any octave, so you can see at a glance which tone the chord is still missing. The numeral itself lights up when all three tones are there, and a dot under a tone means you have doubled it.
- **The opening chord fixes the voices.** As soon as the first chord is complete — four notes, every one of them a tone of the chord, all three tones present — its notes are labelled S, A, T and B down the left, top note first, and those four voices hold for the rest of the progression. Only this chord carries the letters; every later chord takes its voices when it first fills up, by the assignment that moves each line least, and then keeps them. So a note dragged past another inside a later chord stays the voice it was — a real crossing, named as one — while the opening chord always re-reads top down, since it is the chord the others are fixed to. Lose a note and that chord unfixes until it is whole again. Every check below follows these voices rather than the pitch order, and the readout under the staff names each note's voice, so a crossing is plain there too.
- **Hear it back.** Alongside Check, once every chord is voiced, a **Play progression** button walks the progression a chord at a time — four voices together, the column lit while it sounds. Press it again to stop. If the sound was switched off it switches back on rather than playing to silence.
- **Checking draws the parallels.** When the checklist catches a parallel fifth or octave, a red line strokes itself along each of the two voices that moved in lockstep, from the one chord to the next — so the fault is on the staff, not just described. Nothing else is drawn: a clean progression shows no lines at all. They belong to the report, so editing any note takes them away with it.
- **Four voices to a chord.** Each chord takes at most four notes, SATB. Once it has them the ghost preview stops offering a fifth and a note dragged in from elsewhere is turned away. A cross appears over the column instead: click it and that chord empties, so a voicing can be restarted without clearing the whole staff. Cleared notes drift up and fade rather than blinking out, whether they go one chord at a time or all at once.
- **Place notes directly on the staff.** Hover near the correct system and a faded preview snaps to the nearest line or space; click to drop it in. Drag a placed note to move it — to another pitch or another chord — and double-click it to take it off. The cursor turns to a hand over a note so you can see what is draggable.
- **Real notation.** Engraved treble and bass clefs and the correct key signature for whichever key you picked. The half of the system you are hovering decides the staff: the treble covers C4 up to C6, the bass E2 up to C4, so between them every SATB pitch has a home and none of them piles up ledger lines. Middle C belongs to both — written below the treble staff or above the bass, at its own height in each, the way a widely spaced grand staff actually reads.
- **The checklist.** Once every chord has its four voices, a **Check voice leading** button appears. Voices come from the opening chord as described above — the report marks what to fix in red, what to watch in amber, and what is merely worth noting in green:
  - **Completeness** — root, third and fifth must all be present somewhere in the four voices; anything missing is an error.
  - **Doubling** — reports which tone is doubled. Doubling the third is flagged as the weaker choice rather than an error; the root or fifth is preferred.
  - **Voice crossing** — a voice sounding above the one named over it (tenor above alto, say) is an error, reported with both notes.
  - **Spacing** — Soprano–Alto and Alto–Tenor each stay within an octave. Tenor–Bass has no limit. A gap that is too wide is named as an interval as well as measured: “a major tenth apart — C4 to E5, 16 semitones”.
  - **Leading-tone doubling** — a doubled leading tone in a V is a caution to watch on the next move.
  - **Leading-tone resolution**, whenever a V moves to the tonic: undoubled, it must rise by step; doubled, at least one copy must rise and the other must either rise too or drop by leap to the fifth of the tonic — the recognised exception.
  - **Parallel fifths and octaves** against the previous chord, across all six voice pairs. Flagged only when the same perfect interval appears in both chords *and* both voices moved the same way. Contrary and oblique motion into a repeated perfect interval are left alone, and so are hidden (direct) fifths and octaves.

## How to use it

1. Pick the key from the circle of fifths — majors outside, relative minors inside.
2. Tap the Roman numerals to build your progression, then **Begin voicing**.
3. For each chord, place its notes: hover and click to add, drag to move, double-click to remove.
4. With all four voices in every chord, **Play progression** hears it back and **Check voice leading** marks it. Fix what it flags and check again — editing any note clears the last report.
5. At the end, start a new progression to try another key or shape.

## Scope

The checklist reports in prose, with the parallels it finds also drawn on the staff.

Root-position triads only. All seven diatonic degrees are available; in minor, V and vii° raise the leading tone and the rest stay diatonic to the natural minor scale. No inversions or seventh chords yet.

## Tech

Single self-contained HTML file. No build step, no external services — just open it in a browser. Everything is drawn as SVG: staff lines, stems, ledger lines and the brace are generated in code, while the clefs, accidentals and noteheads are real engraved outlines. All the theory (scales, chord spelling, the rule checks) is plain JavaScript with no external libraries.

The clef, accidental (sharp, flat, natural, double sharp) and notehead outlines were extracted from [Bravura](https://github.com/steinbergmedia/bravura), Steinberg's reference SMuFL font, and inlined as SVG path data — about 5KB for the seven glyphs — so the page loads no font and makes no network request, but the notation is the genuine engraved shapes. Bravura is © Steinberg Media Technologies GmbH, licensed under the SIL Open Font License 1.1.

The note sounds are five samples from the [Salamander Grand Piano](https://archive.org/details/SalamanderGrandPianoV3) by Alexander Holm (CC-BY 3.0) — C2, C3, C4, C5 and C6, trimmed to their first 2.4 seconds at MP3 frame boundaries and embedded as base64, about 84KB in total. A pitch plays whichever sample is nearest, resampled by no more than six semitones, so it still sounds like a piano rather than a tape effect. Like the notation, this means no network request at runtime.
