# Grand Reopening: Last Light + Live Wire

Run `GrandReopening.exe` and choose one of two complete, separate campaigns:

- **Last Light:** a nine-level solo platforming story about saving the abandoned park before sunrise.
- **Live Wire:** a twelve-level host-run online co-op story for two to four players, set weeks later during the public grand reopening.

## The night shift

CIRCUIT, the dying mascot-AI of your old amusement park, has paged its fired maintenance crew back at midnight. Demolition starts at sunrise. Recover Sparks, restore Neon Boardwalk, Gearworks Underground, and Skyline Observatory, then bring every zone online at Hub Tower.

Wren "Wrench" Okafor, BOLT-9, and their crew each hold part of CIRCUIT's master restart override. Coordinate switches, shared lifts, carried power, checkpoints, and timed repairs. Each zone ends with a broken ride mechanism to restore through platforming and teamwork--not an enemy boss.

## Controls

- Move: **A/D** or arrow keys
- Jump / wall jump: **Space**, **W**, or Up
- Role ability: **Shift** or **K**
- Wren: double jump, then role ability near metal for a magnetic grapple
- BOLT-9: power dash; while airborne, hold **S/Down Arrow** or left-stick down and press the role ability to ground pound
- Nova: long light-hook grapple and illumination aura
- Pip: wall slide, wall jump, and air dash
- Interact / revive / carry: **E** or **F**
- Run: **Ctrl** or **Z**
- Pause: **Esc**
- Gamepad: left stick, A, B, X, right shoulder, Start

## Dialogue voices

Story dialogue uses a voice installed by your operating system. The subtitle changes only after that line finishes speaking. Open **Settings** to adjust **Dialogue Voice** volume or turn **Speak dialogue aloud** on or off. The same speaking switch is available from the in-game pause menu. If the computer has no compatible text-to-speech voice, subtitles use their normal reading timer automatically.

## Live Wire online co-op

The inviting player chooses **Host Live Wire** and runs the listen server on their own PC. The crew lobby displays a detected LAN address with the active UDP port and provides a **Copy Address** button. Friends choose **Join Live Wire** and paste that complete `IP:port` value. The default port is `24872`. The host can begin when the lobby contains two to four players.

Live Wire progress is separate from Last Light. Stay within tether range so the visible current between crew badges remains connected. Coordinate dual relays, balance the shared grid meter inside its safe band, pair a pad rider with a lever operator for Overcharge Jumps, and touch shorted crewmates before CIRCUIT's reconnect timer expires. The crew shares one retry pool.

The online campaign crosses six restored public zones—Neon Boardwalk, Gearworks, Skyline, Mirror Maze, Big Top, and Frozen Lagoon—before every feed is synchronized at Hub Tower.

LAN play normally works with the host's LAN address. Internet play may require UDP port forwarding. A host behind CGNAT needs a future relay or platform transport; this release has no dedicated server or cloud dependency.

Windows may show a firewall-access prompt the first time this executable hosts. Review it and choose only the network types you trust; cancelling leaves inbound sessions blocked.

## Files in this package

- `GrandReopening.exe`: Windows x86-64 game
- `VALIDATION.md`: tested build details and known distribution caveats
- `CREDITS.md`: game and asset credits
- `THIRD_PARTY_NOTICES.md`, `GODOT_COPYRIGHT.txt`, `LICENSE`: engine and license notices

The executable is unsigned, so Windows may show its standard warning for independently distributed applications.
