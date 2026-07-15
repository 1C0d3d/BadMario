# Grand Reopening release validation

Validated July 14, 2026 with Godot `4.7.stable.official.5b4e0cb0f` on Windows x86-64.

## Campaign isolation

- Last Light remains a nine-level solo campaign with its original manifest, route IDs, story, three restoration zones, save keys, CIRCUIT arc, sunrise deadline, and Hub Tower ending.
- Live Wire is a separate twelve-level multiplayer-only campaign with its own manifest, level folder, unlock list, completion records, last-level value, and ending flag.
- Live Wire contains exactly two levels in each of six zones: Neon Boardwalk, Gearworks, Skyline, Mirror Maze, Big Top, and Frozen Lagoon.
- Canon checks found every supplied dialogue anchor, the public-reopening premise, the Orbit Overcharge cascading midpoint, and the all-six-feeds Thaw Point finale.

## Automated results

- Headless editor import, resource loading, JSON parsing, and GDScript registration completed without reported errors.
- All nine Last Light JSON levels instantiated geometry, objects, enemies, and a solo player; every original objective graph reached completion.
- Last Light canon, four solo role kits, restoration systems, timed-only dialogue, checkpoints, hazards, authored enemy patrol paths, and same-level engagement all passed their existing suites unchanged.
- A live Windows text-to-speech run found an installed voice, spoke a CIRCUIT test line, and received the matching utterance-complete callback. HUD regression confirms subtitles do not advance while speech is active and change when that callback arrives.
- All twelve Live Wire JSON levels passed the expanded schema, built their Live Wire controller, grid stations, Overcharge pads, geometry, and gameplay objects.
- The Live Wire mechanics suite passed connected-chain tethering, grace-period power loss and recovery, distinct-player Overcharge, Shorted/Reconnect teammate touch, signed load aggregation, shared retry consumption, latched-feed retry persistence, and stable-grid completion.
- Main-flow validation passed title navigation, the persistent **Speak dialogue aloud** Settings switch, solo continue/restart/return, the minimum-two-player lobby lock, unlocked Live Wire route selection, detected host `IP:port` display, and pasted IPv4/IPv6 address parsing.
- HUD regression passed the pause-menu speaking switch and confirmed that disabling speech mid-line cancels the voice without removing or immediately advancing its subtitle.
- A two-process ENet run passed Live Wire player replication, host-authoritative client movement, checkpoint and discrete-event synchronization, simultaneous relay latching, client state receipt, and disconnect cleanup.
- A four-process ENet run passed the maximum roster: Wren, BOLT-9, Nova, and Wren Relief all replicated, activated the dual relays, and disconnected cleanly.
- The release Windows executable completed 180-frame headless and normal-window boots with successful exit status.

## Gameplay content checks

- Every Live Wire stage requires at least two active players, a connected wire, safe shared load, and its configured cooperative events before grid stabilization can complete.
- Simultaneous relay groups require separate placed switches to be active in the same physics window; they cannot be cleared sequentially by one player.
- Electric short hazards, shared retry pools, reconnect timers, timed surges, checkpoint refills, and Live Wire-dependent hazard shutdown are data-driven per level.
- Thaw Point requires all six zone feed events, the paired countdown, Tower Overcharge, both crown holds, safe load, and an uninterrupted ten-second light-show synchronization.
- Public-facing failure copy stays warm and gameplay-first; guest danger or dark failure stakes were not introduced.

## Distribution notes

- Online play is direct-IP ENet over UDP, default port `24872`. The host lobby displays a LAN address and active port with a copy control.
- Internet hosts may need to allow the game on trusted networks and forward the UDP port. CGNAT needs a future relay, join-code rendezvous, or platform P2P transport.
- This is a player-hosted listen server. There is no dedicated server or paid-cloud dependency.
- The Windows executable is not code-signed, so Windows may show the normal warning for independently distributed software.
- A Linux export preset is included in source; this release package contains the tested Windows x86-64 build.
- Art is original runtime geometry and audio is synthesized in code. No third-party game-asset attribution is required; Godot's MIT and third-party notices ship with the build.
- Dialogue voices come from the player's operating-system speech service. Voice availability and exact timbre vary by installed system voices; subtitles and timed fallback remain available everywhere.
