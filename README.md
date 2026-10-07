# RocketSky

A browser remake of Atari's 1980 arcade classic **Missile Command**. Defend six cities from waves of incoming missiles using three anti-missile bases.

The whole game is a single HTML file. It has no dependencies and needs no build step.

## Play

Download or clone the repo, then open `index.html` in any modern browser. Click or tap the screen to start.

```bash
git clone https://github.com/jamalxcode/rocketsky.git
```

Sound starts after your first click, because browsers block audio until the page gets some input.

## How to play

Enemy missiles fall toward your cities and bases. Aim the crosshair and fire: your missile flies to that spot and bursts into an expanding fireball. Anything that touches the fireball is destroyed, and destroyed missiles explode too, so one well-placed shot can set off a chain reaction.

- **Lead your shots.** Aim where the missile will be when your blast goes off, not where it is now.
- **Use the center base for fast threats.** Its missiles fly almost twice as fast as the side bases'.
- **Watch your ammo.** Each base has 10 missiles per wave and shows **LOW** at 3 or fewer and **OUT** when empty. A base that gets hit loses its remaining missiles for that wave.
- **Don't run dry.** When all three bases are out of missiles, the remaining enemy missiles speed up.

The game ends when every city has been destroyed and you have no bonus cities left to rebuild them.

## Controls

| Input | Action |
| --- | --- |
| Mouse / tap | Aim and fire from the nearest base |
| A / S / D (or 1 / 2 / 3, Z / X / C) | Fire from the left / center / right base |
| Space / Enter | Fire from the nearest base, or start the game |
| P or Esc | Pause and resume |
| M | Sound on / off |

The game also pauses on its own when you switch to another tab.

## Scoring

| Target | Points |
| --- | --- |
| Missile | 25 |
| Bomber or satellite | 100 |
| Smart bomb | 125 |
| Missile left over at the end of a wave | 5 |
| City left standing at the end of a wave | 100 |

All points are multiplied by the wave multiplier: **1×** for waves 1–2, **2×** for waves 3–4, and so on up to **6×** from wave 11. You earn a **bonus city every 10,000 points**, and it rebuilds a destroyed city at the end of the wave. Your high score is saved in your browser.

## Waves

| Wave | What's new |
| --- | --- |
| 1 | Slow single missiles |
| 2+ | MIRVs that split into several missiles mid-flight, plus bombers and satellites that drop missiles as they cross the sky |
| 6+ | Smart bombs that steer around your explosions |
| Every wave | More missiles, falling faster and arriving in bigger volleys |

The color scheme changes every two waves, as it did in the arcade original.

## Effects and sound

- Low-resolution pixel graphics with CRT scanlines
- Missile trails with blinking warheads, and blinking X markers where your shots will burst
- Explosions that flicker through colors as they grow and shrink
- A screen flash when a city or base is hit
- "DEFEND CITIES" intro, end-of-wave bonus tally and the octagonal **THE END** finale

All sound effects are synthesized live with the Web Audio API, so there are no audio files. They include the launch whoosh, explosion booms, heavier blasts on city hits, the alert at the start of each wave, the buzz of bombers and satellites, the bonus tally ticks and chimes, and the long final rumble.

## Accessibility

If your system has **reduced motion** turned on, the screen flash is disabled and the explosion colors cycle more slowly.

## Project structure

```
index.html   The entire game: markup, styles and JavaScript (canvas + Web Audio)
README.md    This file
```

## Credits

Inspired by *Missile Command* (Atari, 1980), designed by Dave Theurer. RocketSky is a fan remake and is not affiliated with or endorsed by Atari. All code, graphics and sounds in this repo are original.
