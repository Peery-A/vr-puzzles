# VR Lichess Puzzles — setup

A WebXR app for Quest 3 / 3S. Runs in the Quest Browser. No install, no developer mode.

Live at: https://peery-a.github.io/vr-puzzles/

## Use it on the Quest

1. For hands: Settings → Movement Tracking → Hand Tracking → On. Controllers work without this.
2. Open the Quest Browser and go to https://peery-a.github.io/vr-puzzles/. Bookmark it.
3. Tap **Log in with Lichess** and approve. The app asks for puzzle read/write and study read access.
4. Optional: load a study (see Studies below). Text entry is not available inside VR, so do this first.
5. Tap **Enter VR**. Use controllers, or put them down and use your hands. The app switches automatically.
6. The table appears in front of you at chest height.

## Hand controls

Right of the board:

| Action | How |
|---|---|
| Move a piece | Pinch it (thumb + index), carry it, release over the target square. Legal squares show green dots. |
| Next puzzle / chapter | Poke **Next** |
| Hint | **Hint** highlights the piece to move (does not count as a fail) |
| Show solution | **Solution** plays the answer and records a loss (puzzles only) |
| Table height | **Higher** / **Lower**, 3 cm per poke |

Left of the board:

| Action | How |
|---|---|
| Mode | **Mode** switches between puzzles and the loaded study |
| Step through moves | **◀** / **▶**. Works during and after the puzzle. While reviewing, pieces are locked; step forward to the current position to keep playing. |
| Difficulty | **Level** cycles Easiest (−600) → Easier (−300) → Normal → Harder (+300) → Hardest (+600). Applies from the next puzzle. Saved. |
| Board size | **Board +** / **Board −**, 10% per poke, 70%–160%. Saved. |

## Controller controls

A laser points from each controller. The square under it highlights when it holds one of your pieces; table keys brighten when aimed at.

| Input | Action |
|---|---|
| Trigger on a piece | Hold to pick it up, drag along the board, release over the target square |
| Trigger on a key | Presses the key |
| Grip | Grabs a piece within 6 cm of the controller tip; release over the target square |
| A / X | Hint |
| B / Y | Next puzzle / chapter |
| Thumbstick left / right | Step back / forward through the moves |
| Thumbstick up / down | Table height |
| Thumbstick click | Re-place the table in front of you |

Releasing a piece off the board or on an illegal square returns it. Controllers vibrate on pick-up and key presses.

Re-center: thumbstick click, hold the Meta button, press **R**, or exit and re-enter VR.

## Studies

Play any Lichess study chapter by chapter along its mainline.

1. On the page, paste a study URL (`https://lichess.org/study/AbCdEfGh`) or its 8-character ID and tap **Load study**. A chapter URL starts at that chapter. Logged in, **My studies** lists your own.
2. Mode switches to Study. You play the chapter's orientation colour; the other side's moves play automatically.
3. A wrong move is rejected; try again. **Hint** and **Solution** work as in puzzles.
4. Chapter comments show on the panel and in the page. Arrows, circles and side variations are ignored.
5. **Next** goes to the next chapter. After the last chapter it starts over.

Studies are never rated. The last study and chapter are saved and reload on the next visit. Variant chapters (Crazyhouse and so on) are skipped with a message.

Private studies need the study read permission. If you logged in before this update, log out and log in again.

## Desk play: keyboard and mouse

Sit at a desk with the headset on and play without reaching. An orange cursor marks a square on the board. Cursor directions are relative to your seat: up always moves away from you, as White or Black.

| Key | Action |
|---|---|
| W A S D / arrow keys | Move the cursor one square |
| Space / Enter | Pick up the piece under the cursor; press again to place it |
| Esc | Cancel the pick-up |
| Q / E (or , / .) | Step back / forward through the moves |
| N | Next puzzle / chapter |
| H | Hint; also jumps the cursor to the piece to move |
| X, X | Show solution. Needs a second press within 2.5 s, since it records a loss. |
| L | Cycle difficulty |
| M | Switch between puzzles and study |
| + / − | Board size |
| Page Up / Page Down | Table height |
| R | Re-place the table in front of your head (VR only) |

Mouse, in VR:

| Input | Action |
|---|---|
| Move | Slides the cursor across the board |
| Left click | Pick up / place |
| Right click | Cancel the pick-up |
| Wheel | Step back / forward through the moves |

The first click in VR locks the pointer to the page so the mouse keeps working at screen edges.

### Which setups work

- **PC VR (Quest Link or Air Link, page open in Chrome or Edge on the PC):** keyboard and mouse both work. Keep the browser window focused.
- **Quest Browser with a Bluetooth keyboard and mouse paired to the headset:** keyboard works. Mouse depends on whether Quest Browser forwards mouse movement during an immersive session; this is untested. If the mouse does nothing, use the keyboard.

## Pieces

Tournament Staunton proportions: king 1.7× the square height, base about 70% of the square. Rook has crenellations, bishop a mitre slit, queen a beaded coronet, knight a carved head.

## Rating rules

- Puzzles come from `/api/puzzle/batch/mix`; logged in, you only get puzzles you have not seen.
- Difficulty is set in the app, not on lichess.org. The website's puzzle difficulty setting does not apply to API requests. Offsets are relative to your puzzle rating. Default is Easiest.
- The first wrong move records a loss immediately, as on lichess.org. You can keep playing to finish.
- A clean solve records a win. Your new puzzle rating and the change show on the panel.
- Any mating move is accepted on the final move, as on lichess.org.
- Not logged in: puzzles still load, results are not recorded.

## Desktop testing (no headset)

The same page works on a PC: drag pieces with the mouse, orbit with drag on empty space, click the keys. All keyboard shortcuts above also work. The **Board size** slider, **Difficulty** and **Mode** menus, and study loader sit in the top-left panel.
