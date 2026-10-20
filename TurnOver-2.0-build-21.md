# TurnOver 2.0, build 21

### New to try

- TurnOver is free and open source: the code is at github.com/TurnOver-For-Mac/turnover, no tester key is needed any
  more, Send feedback opens TurnOver's problem form on GitHub, and Support TurnOver in the menu opens Ko-fi.
- Plugins are back on for everyone: the TurnOver menu, Tools, Plugins. Shared as pull requests to the plugins
  repository, checked and reviewed before the library carries them.
- TurnOver reads every app by default; VoiceOver still handles passwords and macOS's own prompts. Command Control
  Shift T gives the app in front to VoiceOver, or back to TurnOver, straight away (the layer's T still does too).
- JAWS keys (Command Control Comma, then K, until you hear "JAWS keys"): JAWS's laptop layout with Caps Lock as the
  JAWS key. The reading grid (Caps U I O for lines, J K L for words, M comma period for characters, Y H N for
  sentences, Control U I O for paragraphs), Caps Shift J and L for the line up to and from the cursor, Caps Z for the
  virtual cursor, Caps F5 F6 F7 for the lists, Caps P and semicolon for the JAWS and PC cursors, Caps 8 and 9 to
  click, Caps Control H for speech history, Caps Control V for the app's version, Caps Control F12 for the time with
  seconds. During say all, Left and Right go back and on a sentence, and Page Up and Page Down change the speed for
  that say all. Every other key is the Windows style's.

### Fixed

- Waking the Mac at the lock screen no longer ends in several TurnOvers speaking at once: while the Mac is asleep,
  locked or just awake, a stuck voice is left to come back rather than restarted; a restart after a hang ends the
  stuck copy, so there is only ever one. Reported by a tester.
- Giving a key to a command: the list of commands stays open for the next one; Escape leaves it. Reported by a tester.
- Command Tab doing nothing until TurnOver was turned off and on: a modifier the Mac thought was still held is
  released before Command Tab passes, and the log records both states.
- When the Mac's audio system hangs (it did for a few minutes on 20 Oct), TurnOver no longer hangs with it and
  restarts over and over: the fresh voice is built off the main thread, nothing waits on the speech queue, the
  device list is read on its own queue, and the log says which audio call stuck.
- Screen recognition no longer freezes TurnOver (it could restart itself on a slow read). Reported by a tester.

- The Windows style (NVDA, Narrator and JAWS keys): no more pauses between the pieces of what TurnOver says
  ("Settings submenu 3 of 9", "OK button"), as NVDA says them. The Mac style keeps VoiceOver's way. Reported by a
  tester.
