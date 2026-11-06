# Super Mario Engine

A custom 16-bit real-mode platformer written in NASM x86 assembly, running as a single `.COM` binary in DOSBox.
**Course:** EL2003 Computer Organization & Assembly Language, FAST-NUCES (Chiniot-Faisalabad Campus)
**Deadline:** Submission 29 Nov 2026

## Features
- VGA Mode 13h (320×200, 256 colors) with off-screen double buffering (`REP MOVSW`)
- 16×16 tile map (60×12) with forward-only scrolling camera
- Sprite engine with color-0 transparency and horizontal flipping
- 8.8 fixed-point physics (acceleration, friction, gravity, variable jump)
- AABB collision, Goomba/Koopa AI, shell kicks
- ? blocks, coins, Super Mushroom, HUD (score, coins, lives, 300s timer)
- Game states: Title, Playing, Paused, Dying, Win, Game Over
- Custom INT 9h (keyboard) and INT 8h (timer) handlers, restored on exit

## Build & Run
```bash
nasm -f bin src/MAIN.ASM -o MARIO.COM
dosbox MARIO.COM
```
Tested on DOSBox 0.74-3.

## Controls
| Key | Action |
|-----|--------|
| Left / Right | Move |
| Jump key | Jump |
| Action key | Run / Action |
| P | Pause |
| Esc | Exit |

*(Update to match the final key mapping.)*

## Team
| Member | Modules |
|--------|---------|
| Uzwa Shahid (Lead) | 1, 2, 3, 6, 14, 15 |
| Usman | 4, 5, 10, 11 |
| Hajra | 7, 8, 9, 12, 13 |

## Git Workflow
- No direct pushes to `main`
- Branches: `feature/uzwa-graphics-camera`, `feature/usman-sprites-enemies`, `feature/hajra-interrupts-physics`
- All PRs reviewed by Uzwa and must assemble cleanly before merging

## Structure
```
src/MAIN.ASM    # main source
docs/           # screenshots and notes
MARIO.COM       # final build
```
