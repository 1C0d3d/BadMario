# Grand Reopening: Live Wire — multiplayer canon

This canon applies only to multiplayer. The Last Light solo story, levels, progression, and ending are unchanged.

## Premise

Live Wire begins weeks after Last Light, on the park's first public reopening night. Real guests fill the restored park for the first time in years. CIRCUIT is healthy again, but the systems restored during the quiet repair night are fragile under real public load.

Every active zone now shares one live grid. Wren, BOLT-9, Nova, and the relief crew must keep the park operating while more zones come online. A single person cannot hold controls in multiple places, balance competing loads, reconnect a shorted partner, and run the finale at once. Cooperation is the story's physical problem, not optional flavor.

The stakes remain warm and public-facing: a failure means flickering rides, a tripped checkpoint, or an awkward light show—not danger to guests.

## Three acts

1. **Doors Open:** guests enter, the crew is thrilled and terrified, and Neon Boardwalk teaches the Live Wire, dual relays, load balancing, Overcharge Jumps, shorts, and shared retries.
2. **Everything, All At Once:** Gearworks, Skyline, Mirror Maze, and Big Top come online. Surges force the crew to split positions while remaining ready to abandon one post and rescue another. Orbit Overcharge is the midpoint cascading overload.
3. **The Finale:** Frozen Lagoon releases the last feed. At Hub Tower, all six zones must be stable at the same moment for the reopening light show.

## Mandatory mechanics

- **Live Wire:** a visible current connects the active crew. After a grace period without a connected chain, mechanisms power down and linked hazards reactivate.
- **Dual relays:** separate players must hold distinct controls simultaneously before the group latches.
- **Load balancing:** station draws, shunts, and timed surges feed one shared meter. The breaker trips if the team cannot return it to the safe band.
- **Overcharge Jump:** one player stands on the pad while a different player holds its lever.
- **Shorted and Reconnect:** a teammate must touch the shorted player before CIRCUIT's timer expires.
- **Shared retries:** failures consume the crew's common checkpoint pool; checkpoints replenish it.

Past the opening tutorial, Live Wire is not completable with one connected player.

## Route

| Zone | Level 1 | Level 2 |
|---|---|---|
| Neon Boardwalk | Arcade Overload | Midway Meltdown |
| Gearworks Underground | Grinding Gears | Full Throttle |
| Skyline Observatory | Zero-G Static | Orbit Overcharge |
| Mirror Maze Funhouse | Double Vision | Reflected Circuit |
| Big Top Carnival | Center Ring Surge | Grand Finale Rehearsal |
| Frozen Lagoon | Ice Break | Thaw Point |

Thaw Point leaves Frozen Lagoon, climbs Hub Tower, locks all six zone feeds, starts two countdown relays together, performs a paired Overcharge, and holds both crown lines in the safe band for ten seconds.

## Required dialogue anchors

- Wren: “Real guests. Real power grid. No pressure.”
- BOLT-9: “Zone Two is drawing 40% over baseline. This is either a malfunction or Wren is having fun again.”
- Wren: “Can't it be both?”
- Nova: “I can't hold both zones—someone needs to come help Bay 3, now.”
- BOLT-9: “Leaving my post.”
- Wren: “Go. I've got this side.”
- CIRCUIT: “All zones... stable. All at once. I don't think I've ever actually been fully awake before tonight.”

These anchors appear in the corresponding level JSON. With system voices enabled, each subtitle advances when its utterance-complete callback arrives. Without a usable voice it uses the reading timer. Gameplay input never skips a line.
