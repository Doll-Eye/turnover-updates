# TurnOver 1.0, build 11

### New to try
- Keyboard style: Mac, which works like VoiceOver key for key (as now), or Windows, which makes the Mac feel like a PC with NVDA: NVDA's commands on the TurnOver key, Command alone for the menus, Option alone for the Dock, F1 to F12 as function keys, and in Finder, Return opens and F2 renames. Switch with TurnOver Shift K, or Keyboard style in the TurnOver menu. More Windows keys are on the way.
- Windows keys for editing, in the Windows style: Control C, X, V, A, Z, S, O, N, P, F and W do what Command does with them; Control Y redoes; Home and End go to the start and end of the line, Control Home and Control End to the start and end of the document; Control with the arrows moves by word or paragraph; Control Backspace deletes a word; Command F4 quits an app (Alt F4). Terminal keeps its own Control keys. These apply where TurnOver leads; where VoiceOver leads, the keys are the Mac's as always.
- Input help: press Escape twice to leave it.
- Unverified apps: in the TurnOver menu, Applications, Unverified apps lists every app you have open that TurnOver hasn't been checked with yet. Switch any of them to TurnOver to try it; they may not read well, and feedback on them is welcome.

### Fixed
- The Dock: after Escape, TurnOver kept reading the Dock with nothing selected and the arrows went back into it. Escape now returns to the app you were in, and the arrows in the Dock are the Dock's own (Left and Right move, Up opens the item's menu).
- Safari: when a page stopped answering for a few seconds, TurnOver could be left with nothing to read until you switched apps. It now looks again once Safari answers, and treats a page with no address yet as still loading.
