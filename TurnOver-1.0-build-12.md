# TurnOver 1.0, build 12

### New to try
- Screen recognition (OCR), as NVDA's TurnOver R: TurnOver reads the text in the window from the screen, for apps that don't tell a screen reader what's in them (games, Steam, pictures of text). Press TurnOver R where TurnOver leads, or Command Control R anywhere, even where VoiceOver leads. Up and Down move through rows; Left and Right by character, with Option or Control by word; Tab jumps between columns and sections; Return or Space clicks the word you're on, Shift Return right-clicks, Option Return double-clicks; M moves the mouse there without clicking; TurnOver R again re-reads; Escape closes. Columns, like a sidebar beside the main text, are read one after the other, and lists and tables row by row. It works on a braille display too: routing keys move to a word, and pressed again click it. The first time, macOS asks for Screen Recording permission for TurnOver. Options are in Preferences, Screen recognition.
- Application chooser: every app with a window, including system alerts that Command Tab leaves out (such as macOS asking to allow Screen Recording), with each app's windows under it. Return switches there. Mac style: TurnOver F1 twice, as in VoiceOver. Windows style: Option Tab, as Windows+Tab is Task View.

### Fixed
- Safari: after reloading a page, the arrows could say "nothing on this page yet" while the page was there (Tab reached it). Safari had swapped the page for a new one; TurnOver now moves to it.
- Context menus say "context menu" as they open, from VO Shift M, the right Option key or Shift F10.
