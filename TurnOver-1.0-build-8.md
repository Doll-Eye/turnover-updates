# TurnOver 1.0, build 8

### New to try
- Braille: TurnOver now drives your braille display while it leads, using the same drivers and braille tables as VoiceOver, so any display VoiceOver supports should just work. It shows the line you're on (contracted, with the word at the cursor uncontracted), the item in focus, and what TurnOver says by itself, such as live updates. Panning, routing and the display's keys work as with VoiceOver, and you can type on its braille keyboard, contracted or letter by letter. USB displays need nothing setting up; for Bluetooth, pair the display in VoiceOver Utility, then turn on "Use a braille display paired over Bluetooth" in TurnOver menu, Preferences, Braille, where you'll also find the table, typing and display settings. TurnOver 1 and TurnOver slash cover the display's keys and chords. Please tell us which display you have and how it goes.
- Pages in other languages are read with a voice for that language, as in NVDA. TurnOver menu, Preferences, Speech: turn it off, or choose the voice for each language.
- "That was wrong": press TurnOver Shift J the moment TurnOver gets something wrong. It quietly marks the moment and you carry on. Send all your marked moments together later from the TurnOver menu, Send feedback, or press the key twice to send straight away.
- Want TurnOver to support an app? Switch to it, then TurnOver menu, Preferences, Applications, Request support (at the end of the list). An email to us opens with a description of how the app is built (no content); add a line about what you use it for. The most-asked apps come first.
- The TurnOver menu from anywhere: Command Control N opens it even in apps VoiceOver leads, as does "TurnOver menu" in the menu bar. TurnOver steps in for the menu and hands back when you close it.
- Word says the page number as you arrow onto a new page; TurnOver Shift L says the page and line.
- Finder and Claude are in the Applications list as previews, off until you turn them on (TurnOver menu, Preferences, Applications).
- Control now pauses speech, and pressing it again carries on, as in VoiceOver.
- After each update, TurnOver tells you what's new to try, and lists it in the TurnOver menu under New to try.

### Fixed
- Safari: a page that was still loading, or stopped answering, could leave TurnOver with nothing to read, and every arrow said "top" or "bottom". TurnOver now says the page has nothing on it yet, keeps looking, and reads it as soon as it arrives. (reported by a tester)
- Menus: moving along the menu bar quickly, a menu's name ("Edit menu") could be cut off as the menu opened. It is now always said.
- Uninstall now offers to remove just the app, keeping your settings and permissions for when you install it again.
