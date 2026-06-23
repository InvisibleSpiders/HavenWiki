# Worldborder Frontier

The HavenNecessities worldborder is a soft frontier. When enabled, the safe area has a configured border, but crossing it can lead into dangerous territory instead of always stopping you at a hard wall.

## What Players See

- Approaching the safe frontier can show warning feedback and a local particle wall.
- Outside the frontier, players can receive warnings and periodic damage.
- Danger can scale the farther a player travels beyond the safe area.
- Frontier hazard mobs and bonus rewards may appear depending on server configuration.
- PacketEvents can add per-player fog, darkness ambience, night/storm sky transitions, and crossing pulse feedback.

## Teleports And Anchors

Servers can block teleports while outside the frontier or block teleporting into outside destinations.

Servers can also block setting homes, server warps, and player warps outside the frontier.

## PvP

The frontier can act as a forced PvP area when both players are outside the same managed frontier. Exact behavior depends on server configuration.

## Frontier Surges

Surge profiles temporarily add stronger wave pressure for eligible players in the frontier. These waves can add mobs such as wither skeletons, piglin brutes, or vindicators without permanently changing the frontier distance.

Surges can be launched by the events module.

## Expansion

Worldborder expansion events can permanently increase the managed frontier size. Expansion can also increase the configured minimum separation between the safe world and frontier systems.
