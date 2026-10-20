# TurnOver 2.0, build 20.2

### Fixed

- TurnOver restarting itself ("TurnOver's voice stopped"), most often after say all and an arrow key: the speech could
  wait for ever on the Mac's audio player. It no longer can, and if speech ever does stick, a fresh voice takes over
  within a few seconds instead of a restart. Reported by a tester.
- Context menus: Right Arrow on an item with no submenu no longer closes the menu or freezes TurnOver, and Right on
  Open With opens it. Reported by a tester.
- Word: every table in a document moves by row and column, not only the first. Reported by a tester.
- Your own keys: VoiceOver's and NVDA's commands (next paragraph, next table and the rest) are listed whatever the
  keyboard style, and keys given to them work; right Option keys you set work with VoiceOver's Option Commander off.
  Reported by a tester.
- Command Control Period switches TurnOver off and on again after an update; it had quit TurnOver instead.
