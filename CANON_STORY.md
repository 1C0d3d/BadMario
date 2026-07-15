# GRAND REOPENING — Game Narrative & Story Brief
*(working title — swap freely)*

**Game type:** 2D multiplayer platformer, Godot 4
**Players:** 2–4, host-client co-op
**Structure:** Multiple worlds/zones, classic platformer level design

---

## BUILD NOTES (read this first)

- **Core roster is 2 characters.** Everything else (3rd/4th player, extra zones) is additive — the game is fully playable and complete with just these two.
- **"Bosses" are not enemies.** Every zone climax is a malfunctioning ride — a timing/platforming sequence against a broken machine. No health bars, no combat, no damage-trading. Think Rayman Legends' machine set-pieces, not a fight scene.
- **Build 3 zones first.** Add the remaining zones only after the core loop (movement, co-op mechanics, one full zone start-to-finish) is solid and fun.
- **Co-op is the plot, not just the mode.** The story reason players must play together (see below) should be reflected in level design: some switches/lifts/platforms genuinely require two-plus players to operate.

---

## ONE-SENTENCE PREMISE

A fired maintenance crew sneaks back into the amusement park that raised them, to power it back on zone by zone before the wrecking crew arrives at dawn.

---

## MAIN GOAL

Collect scattered power cells ("Sparks") hidden throughout each zone, return them to that zone's core to restore power, then combine power from all restored zones at the central Hub Tower to fully relight the park before sunrise.

---

## WHY THE PLAYERS ARE TOGETHER

Each of them was personally paged — not randomly — by **CIRCUIT**, the park's dying mascot-AI. Years ago, CIRCUIT split the park's master restart override into pieces and hid one in each employee's old locker, "just in case." No single person holds enough pieces to restart the park alone. The need for multiple players isn't just a game mode — it's the reason the story exists.

---

## CHARACTERS

### Build first — 2 core roles

**Wren "Wrench" Okafor — Head Mechanic**
- Ability: double jump + short-range magnetic grapple (latches onto metal surfaces)
- Personality: sarcastic, upbeat, treats the collapsing park like a broken vending machine she just hasn't kicked hard enough yet.

**BOLT-9 — Retired Parade Robot**
- Ability: ground-pound dash that resets switches; can be stood on by teammates as a temporary platform
- Personality: deadpan, formal, painfully literal, quotes his own 15-year-old tour-guide script at the worst possible moments.

### Add later — once the two core roles are solid

**3rd player — Nova Reyes — Former Lighting & Sound Designer**
- Ability: light-hook grapple that also illuminates dark areas and powers light-based switches
- Personality: calm and quiet, turns out to be the most quietly devastated if the park doesn't make it.

**4th player — simplest option**
- A palette-swap of Wren or BOLT-9's existing kit (same moves, new name/skin) — lowest implementation cost for a 4th slot.
- Optional full character if you want a distinct 4th kit later: **Pip**, a small, fast ex-mascot performer with a wall-slide ability.

*Design rationale: keeping dialogue and ability logic to two voices at first avoids character-mixing issues during early development, with a clear low-effort path to scale up to 3–4 later.*

---

## 3-ACT STORY OUTLINE

### Act 1 — The Gate Still Opens for Us
The crew reunites at the front gates at midnight, buzzed in by a message from CIRCUIT they assumed was a prank. CIRCUIT explains the park is scheduled for demolition at sunrise unless enough zones come back online to prove it's "still operating" — a loophole in the old contract. The first zone doubles as a tutorial: easy platforming, core co-op mechanics introduced, light nostalgia humor.

### Act 2 — Zone by Zone
The crew splits attention across the park's remaining zones. Each has its own broken ride mechanism — not a villain, just a system that's glitched out from years of disuse and now runs on a loop of corrupted logic (a coaster stuck endlessly re-launching, a light show replaying the same five seconds forever). Fixing each one is a platforming gauntlet, not a fight.

**Midpoint reveal:** every zone the crew powers up is also draining CIRCUIT's own memory core. Reviving the park is quite literally costing him his mind.

### Act 3 — Last Light
With demolition trucks visible in the distance at first light, the crew makes the final climb up the Hub Tower — a level explicitly designed to require all connected players at once (pressure plates, timed relays, a lift only movable if someone stands on it while someone else pulls a switch). They restore full power and, in doing so, patch CIRCUIT's memory back together using the same Sparks that powered the park.

---

## WORLD THEMES (ZONES)

### Build first (3 zones)

1. **Neon Boardwalk** — tutorial-friendly zone; arcade games and midway lights; electric floor hazards.
2. **Gearworks Underground** — conveyor belts and rotating gears; timing-based platforming.
3. **Skyline Observatory** — low-gravity space ride; floaty jumps; drifting platforms.

### Add later (stretch goals)

4. **Mirror Maze Funhouse** — reversed/mirrored controls; illusion platforms; misdirection puzzles.
5. **Big Top Carnival** — trapeze swings; cannon launches; tightrope balance sections.
6. **Frozen Lagoon** — a shut-down water park now iced over; slide physics; sudden ice-to-water transitions.

---

## ZONE MALFUNCTIONS (Boss Equivalents — Machines, Not Enemies)

Each zone's climax is a ride stuck in a broken loop, not a creature or villain to defeat in combat:

- Neon Boardwalk: an arcade centerpiece machine short-circuiting on a repeat cycle.
- Gearworks Underground: a conveyor system jammed mid-cycle, forcing timed platforming to reset it.
- Skyline Observatory: a ride car endlessly re-launching along a broken track loop.
- (Later zones follow the same pattern: a light show stuck replaying five seconds, a coaster endlessly re-launching, etc.)

Players resolve these through platforming, timing, and switch-pulling — never through health bars, damage, or combat mechanics.

---

## BEGINNING / MIDPOINT / ENDING

**Beginning:** Reunion at the gates. CIRCUIT's voice crackles to life over an old speaker system nobody thought still worked. The crew realizes the park isn't just closing — it's being erased, all records included, by sunrise.

**Midpoint:** A zone powers up and CIRCUIT starts glitching — repeating old announcements, forgetting a crew member's name mid-sentence. The team learns every zone they light up pulls power straight from him, and decides to keep going anyway.

**Ending:** The Hub Tower lights up fully. Every zone flickers on across the park skyline at once. CIRCUIT's voice comes back steadier than it's been all night — memory intact, thanking the crew by name, correctly, for the first time since the midpoint. Demolition trucks arrive to find a fully lit, fully "operating" park and turn around. Final shot: the crew sitting on the Hub Tower roof, watching the sun come up over a park that's theirs again.

---

## DIALOGUE / CUTSCENE SNIPPETS

- **CIRCUIT (opening):** "Attention, guests — sorry. Old habit. Attention, *former employees.* I need you back at your stations. All of them. Tonight."
- **Wren (first zone):** "Last time I fixed this thing, my manager wrote me up for 'unauthorized creativity.' Let's be creative."
- **BOLT-9 (deadpan):** "Fun fact: this ride has injured fourteen guests and zero robots. I intend to keep that streak alive."
- **Nova (quiet moment, mid-Act 2):** "I designed the light show for this exact tower. Nobody's seen it finished. Not even me."
- **CIRCUIT (midpoint glitch):** "Recalibrating— sorry, what was— Wren? Is that— I remember you. I remember you. Give me a second."
- **CIRCUIT (ending):** "Wren. Bolt-9. Nova. Welcome back to the park you never should've had to leave."
- **Cutscene beat, Act 3 climb (wordless):** The crew, silhouetted against the tower, each pressing a switch in sequence; the park's lights ripple on behind them one zone at a time, visible through the tower windows as they climb.

---

## TONE

Warm, quick, a little goofy — a found family fixing a machine they love, not saving the world. Stakes stay personal and time-boxed (one night, one deadline, one friend they don't want to lose) rather than apocalyptic, keeping pacing tight and gameplay-first: every zone is a reason to platform, not a reason to sit through exposition.
