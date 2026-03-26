# Spectator Indicator CXFR

A KSL mod for CarX Drift Racing Online that shows when another player is watching you in spectator mode.

<img width="200" height="200" alt="icon" src="https://github.com/user-attachments/assets/f453ae69-6430-4bb1-8829-9d1ab3d25bea" />

---


## How it works

Every player running the mod broadcasts their spectator state via Kino.Sync. When someone watches your car, their mod sends the position of the car they are looking at. Your mod compares that position to your own car and if it matches, the overlay appears with the spectator's name.

Both players must have the mod installed for the detection to work.

### Detection methods

The mod detects spectator mode using two approaches:

1. UIWatchPlayerContext — the game creates this component when a player enters spectator mode. The mod reads it via reflection to identify the watched car.
2. Camera direction scoring — the mod checks which car the main camera is pointing at. If it is not your own car, you are spectating someone else. This uses a combination of dot product (camera direction) and distance to reliably detect spectating even when cars are parked close together.

---

## Features

- Real-time spectator detection with player names
- Names are displayed with their in-game rich text formatting (Kino color tags)
- Configurable overlay position (four corners of the screen)
- Adjustable overlay size
- Toggle name display and spectator count independently
- Multiplayer sync via Kino.Sync
- Per-broadcast name resolution with fallback system
- Optimized with cached lookups to minimize performance impact

---

## Installation

### Requirements

- CarX Drift Racing Online (moddable branch on Steam)
- KSL mod loader — https://github.com/trbflxr/ksl
- KSL.CarX extension — https://github.com/trbflxr/ksl_carx

### Install

1. Download the latest `.ksm` file from [Releases](https://github.com/Silv3r25/SpectatorIndicator-CXFR/releases)
2. Place it in `CarX Drift Racing Online/kino/mods/`
3. Launch the game on the moddable branch
4. Open the KSL menu and select SpectatorIndicator

---

## Configuration

All settings are accessible from the KSL in-game menu:

| Setting | Description |
|---------|-------------|
| Indicator enabled | Toggle the mod on or off |
| Show names | Display the names of players watching you |
| Size | Scale the overlay from 0.5x to 2.0x |
| Position | Place the overlay in any corner of the screen |

---

## Overlay

When a player watches you, a minimal overlay appears showing:

- An eye icon
- The number of spectators
- The list of spectator names (with their in-game colors)

The overlay has no background and is designed to be unobtrusive during gameplay.

---

## License

This project is provided as-is for the CarX modding community.

---

## Credits

- KSL and Kino by [trbflxr](https://github.com/trbflxr)
- Mod by S!LVER

