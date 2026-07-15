# Grand Reopening: Last Light + Live Wire

Grand Reopening is a complete compact 2D platformer built in Godot 4.7 with GDScript. It contains two deliberately separate campaigns:

- **Last Light:** nine solo levels across Neon Boardwalk, Gearworks Underground, and Skyline Observatory. The fired maintenance crew answers CIRCUIT's midnight page and restores the abandoned park before demolition at sunrise.
- **Live Wire:** twelve online-only levels for two to four players, set weeks later during the public reopening. The crew must keep six restored zones powered at once and finish with a synchronized light show at Hub Tower.

Solo save progress, dialogue, objectives, and level routing remain isolated from Live Wire. Online sessions never substitute the solo premise.

Open `project.godot` in Godot 4.7 stable and run the project.

## Technical architecture

- The inviting player runs an authoritative ENet listen server on their own PC; there is no dedicated server or paid service.
- Clients send bounded input frames to peer `1`. The host simulates movement and authoritative outcomes, then sends correction snapshots and discrete state RPCs.
- `NetworkManager`, `LevelManager`, `GameState`, `SaveManager`, `AudioManager`, and `VoiceManager` are stable autoload singletons.
- `Main` persists while deterministic `GameWorld` scenes are instanced below it. Player scenes are created through `MultiplayerSpawner` after every peer passes the content-hash and load-ready barrier.
- JSON selects only trusted object types registered in `GameWorld`; it cannot load arbitrary scripts or scene paths.
- Solo and Live Wire have separate manifests, level folders, unlock lists, last-level fields, completion sets, and endings.

## Project structure

```text
GrandReopening/
|-- project.godot
|-- autoload/                     Network, level, state, save, and audio systems
|-- content/
|   |-- campaign.json             Last Light manifest
|   |-- levels/                   9 solo levels
|   |-- live_wire_campaign.json   Live Wire manifest
|   `-- live_wire_levels/         12 online-only levels
|-- scenes/
|   |-- main/ and world/          Persistent root and runtime world
|   |-- player/ and actors/       Crew controller and enemies
|   |-- objects/                  Checkpoints, hazards, relays, doors, objectives
|   |-- multiplayer/              Live Wire grid stations, arc, and Overcharge pad
|   `-- ui/                       Menu, lobby, HUD, dialogue, pause
|-- scripts/                      Focused GDScript modules
|-- tests/                        Solo, content, mechanics, flow, and ENet suites
`-- docs/                         Canon, level authoring, networking, release notes
```

## Gameplay systems

The player controller includes tuned run acceleration, ground friction, air control, coyote time, jump buffering, variable jump height, asymmetric fall gravity, floor snap, and role traversal. Wren double-jumps and grapples, BOLT-9 power-dashes and ground-pounds, Nova uses a long light-hook, and the fourth Live Wire slot is a palette-swapped Wren relief crewmember.

Live Wire adds multiplayer-only systems:

- a visible current links the active crew, with a forgiving disconnect grace timer;
- dual relay groups latch only when separate players activate both sides together;
- a shared load meter must remain inside each stage's safe band;
- grid stations add or remove load through latched interactions and held positions;
- Overcharge Jumps require one player on a launch pad and another at its lever;
- electric hazards can short a player, who must be touched by a teammate before the reconnect timer expires;
- failures consume a shared retry pool, while checkpoints refill it;
- exits regroup slightly delayed players instead of permanently stranding them.

Every Live Wire level introduces story through timed dialogue and the restoration work itself. Its three acts move from opening-rush failures, through a cascading midpoint overload, to Frozen Lagoon and the Hub Tower finale. The ending requires all six zone feeds, a simultaneous countdown, a paired Overcharge, both crown holds, a safe load, and an uninterrupted ten-second synchronization.

Dialogue is voiced locally with Godot's operating-system text-to-speech support. Wren, BOLT-9, Nova, and CIRCUIT use distinct voice, pitch, and rate profiles where the installed speech engine permits them. A subtitle remains on screen until its utterance-complete callback arrives; systems without a usable voice fall back to the existing readable timer. **Speak dialogue aloud** can be turned on or off from title Settings or the in-game pause menu, while volume is adjustable in Settings.

## Controls

- Move: **A/D** or arrows
- Jump: **Space**, **W**, or Up
- Role ability: **Shift** or **K**
- Interact / revive / carry / lock station: **E** or **F**
- Run: **Ctrl** or **Z**
- Pause: **Esc**
- Gamepad: left stick, A, B, X, right shoulder, Start

## Hosting and joining Live Wire

1. The inviting player selects **Host Live Wire**, chooses an unlocked starting stage, and opens a lobby. The default UDP port is `24872`.
2. The lobby displays the detected LAN `IP:port` and a **Copy Address** control.
3. Friends select **Join Live Wire** and paste the complete address. Pasted IPv4 and bracketed IPv6 addresses may include the port.
4. The host starts when two to four players are present.

LAN play normally needs no infrastructure. Internet hosting may require UDP port forwarding. CGNAT requires a future relay or platform P2P adapter. The peer-creation boundary is isolated so Steam, EOS, console, WebRTC, or relay transport can be added without rewriting gameplay RPCs.

Windows can show a firewall prompt the first time an executable hosts. Review it and allow only network types you trust.

## Adding JSON levels

Last Light levels live in `res://content/levels/` and are registered in `content/campaign.json`. Live Wire levels live in `res://content/live_wire_levels/` and are registered in `content/live_wire_campaign.json`.

To add a level, copy the appropriate template or existing file, assign a unique stable ID to the level and every object, register the level ID in its manifest, update the preceding `next_level`, and run the matching campaign smoke test. The schema supports tiles, platforms, moving platforms, spawns, checkpoints, enemies, hazards, triggers, doors, carried cells, switches, objectives, exits, zone cores, ride machines, Live Wire grid stations, Overcharge pads, and world metadata. See `docs/LEVEL_FORMAT.md`.

## Export and validation

Install Godot 4.7 export templates, open **Project -> Export**, select **Windows Desktop** or **Linux/X11**, and export. The PCK is embedded in the executable. Distribute the player README, credits, third-party notices, Godot copyright, and license files with the game.

Automated scenes cover both campaign manifests, all 21 levels, story canon, role abilities, restoration objects, timed dialogue, enemy patrol behavior, Live Wire mechanics, menu flow, two-process ENet, and the supported four-process roster. See `VALIDATION.md` and `docs/RELEASE_CHECKLIST.md`.

## Credits and assets

Visible art is drawn from original runtime geometric primitives. Original procedural music and sound are synthesized in code. No downloaded character, environment, music, or sound pack is bundled, so no third-party game-asset attribution is required.

Godot Engine is MIT licensed. See `CREDITS.md`, `THIRD_PARTY_NOTICES.md`, `GODOT_COPYRIGHT.txt`, and `LICENSE`.
