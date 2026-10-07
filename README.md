# VR Lichess Puzzles — setup

A WebXR app for Quest 3 / 3S. Runs in the Quest Browser. No install, no developer mode.

Live at: https://peery-a.github.io/vr-puzzles/

## Use it on the Quest

1. Turn on hand tracking: Settings → Movement Tracking → Hand Tracking → On.
2. Open the Quest Browser and go to https://peery-a.github.io/vr-puzzles/. Bookmark it.
3. Tap **Log in with Lichess** and approve. The app asks for puzzle read and write access only.
4. Tap **Enter VR**. Put the controllers down; your hands take over.
5. The table appears in front of you at chest height.

## Controls

| Action | How |
|---|---|
| Move a piece | Pinch it (thumb + index), carry it, release over the target square. Legal squares show green dots. |
| Next puzzle | Poke the **Next** key on the table |
| Hint | **Hint** highlights the piece to move (does not count as a fail) |
| Show solution | **Solution** plays the answer and records a loss |
| Table height | **Higher** / **Lower** keys, 3 cm per poke |
| Re-center | Hold the Meta button to recenter; exit and re-enter VR to re-place the table |

## Rating rules

- Puzzles come from `/api/puzzle/batch/mix`; logged in, you only get puzzles you have not seen.
- The first wrong move records a loss immediately, as on lichess.org. You can keep playing to finish.
- A clean solve records a win. Your new puzzle rating and the change show on the panel.
- Any mating move is accepted on the final move, as on lichess.org.
- Not logged in: puzzles still load, results are not recorded.

## Desktop testing

The same page works on a PC: drag pieces with the mouse, orbit with right-drag or left-drag on empty space, click the keys.
