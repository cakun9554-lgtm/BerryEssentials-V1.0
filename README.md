# BerryEssentials 0.2.0

All-in-one survival plugin project targeting Paper 26.3 and Java 25. Land Claim is intentionally not included.

## Build

Requirements: JDK 25 and Maven 3.9+ with internet access.

```bash
mvn clean package
```

Output: `target/BerryEssentials.jar`

Paper API dependency follows PaperMC's documented Maven range `[26.3.build,)`. See https://docs.papermc.io/paper/dev/project-setup/ and https://jd.papermc.io/paper/26.3/.

## Current implementation in 0.2.0

- Economy wallet, bank deposits/withdrawals, and player-to-player transfers
- Configurable item shop GUI
- Multiple homes, warps, random teleport with cooldown and basic safe-location checks
- TPA request and accept
- Persistent personal backpack
- Clan create/invite/join/leave/info (basic membership implementation)
- Daily mob-hunt quest with configurable reward
- Battlepass point and level counter
- Admin rank assignment; rank color is reflected in the player's scoreboard team/nametag prefix
- Villager NPC creation; right-click opens Berry main menu
- Sign chest shop basic BUY/SELL flow
- Sidebar with PROFILES and SERVERS sections and live player/server values

## Important limitations — do not treat this as production-ready yet

This source project has **not been compiled or tested against a running Paper 26.3 server** in the current environment. A JDK 25 + Maven build environment and a test server are required before deployment.

The requested reference scoreboard includes a pixel-art logo, ornamental frame, and textured background. Bukkit/Paper's normal sidebar scoreboard only renders text; this project recreates the section order, colors, and values, but cannot render that bitmap artwork in the vanilla sidebar. A client resource pack/custom HUD would be needed for the full visual match.

Minimap display is client-side or depends on a specific server-side web-map plugin. This build does not yet ship a Dynmap/BlueMap marker adapter. NPC dialogs currently open the Berry menu rather than a configurable branching dialogue editor. Battlepass currently tracks points/levels but does not yet have a tier reward catalogue. Clan permissions/roles and invitation expiry are also not complete. These are explicitly pending, not silently claimed as finished.

## Install after building

1. Build with JDK 25 and Maven.
2. Copy `target/BerryEssentials.jar` into the Paper server's `plugins/` folder.
3. Start the server once to generate `plugins/BerryEssentials/config.yml` and `data.yml`.
4. Back up `plugins/BerryEssentials/` before updating.

No Land Claim module or command is provided.
