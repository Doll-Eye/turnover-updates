# TurnOver 1.0, build 16

### New to try

- A slider or other control read as its value changes now reads the new value, not the one it had when it took the
  focus; a slider from 0 to 1 is said as a percentage.
- Mac style: VO M twice, the status menus, now includes TurnOver's own item at the end.
- Mac style: on a web page, typing while the reading position is on a text field goes into that field, as it does
  once VoiceOver's cursor lands on one; the field takes the focus and focus mode starts. In the Windows style letters
  stay quick-nav keys until Enter or Tab goes into the field, as in NVDA.
- Tab on a web page no longer announces the group a control sits in ("Description of App, grouping" on AppleVis).
- TurnOver Shift T reads the time, twice for the date, for Macs without an Insert key or the function keys (JC).
- A short start-up tone when TurnOver starts while VoiceOver has the Mac, so with Open at login you know it is there
  (Daniel).
- Force quit, spoken. Command Option Escape (and Control Shift Escape in the Windows style) lists the running
  applications; choose one, then confirm to force quit it or ask it to quit normally. The Mac's own Force Quit
  window is silent with VoiceOver off. Also in the TurnOver menu as "Force quit an application".
- Automatic language switching now works in any app, not only where the text is marked with its language: a line in another script (Arabic under an English voice, or the other way round) is read with that language's voice in TextEdit, Pages or anywhere else, and so is a single character when you move by character (reported by a tester).
- The formatting key (VO T; TurnOver F in the Windows style) reports the first selected character when text is selected, and says "selected" first. Pressed twice, it gives the detail: colour, background colour, superscript or subscript, and alignment where the application reports it (requested by a tester).
- Word tables: TurnOver Up and Down move by row and Left and Right by column from wherever the caret is, and the table's size is said once. A new switch in Preferences, Document formatting, "Table row and column headers" (requested by a tester).
- Under the bonnet: Messages and WhatsApp are now described by small recipe files rather than code (the first step towards adding apps without a build, and towards plugins). You can put your own recipe for another chat app in ~/Library/Application Support/TurnOver/recipes; a file that won't load is named in the log.
- Windows style: a review step (TurnOver and the arrows) onto a control took the keyboard focus with it, as VoiceOver's cursor does, so after reviewing TextEdit's toolbar the arrows had left the text. NVDA's review cursor never moves the focus, so it no longer does in the Windows style; a setting in Preferences, Keyboard ("Keyboard focus follows the cursor") chooses: by style, on, or off.
- Safari: H on a heading long enough to wrap over two lines read only its first line, and the next H landed on its second line as if it were another heading (reported by Oliver). Quick navigation now reads the whole heading and skips to the next one.
- Finder: Command Up and Command Down made TurnOver hand over to VoiceOver for a few seconds (macOS reported TurnOver's own process in front for a moment), which felt like a crash. TurnOver no longer hands over on account of its own process unless one of its own windows is showing (reported by a tester).
- Mac style: VO M no longer has the focused item spoken over "Apple menu"; and after closing a menu with Escape, the focused item is read once, not three times (reported by a tester).
- Under the bonnet, from this week's code review: TurnOver's keys are decided on its main thread now, so an application that stops answering can no longer make macOS switch TurnOver's keyboard off (a TurnOver chord's letter then landed in the document). Nothing changes in how the keys work; it should feel the same or quicker.
- The App Store's End key (reading to the end of a long page) and Word's headings list (VO U) no longer hold TurnOver up while they wait for the application: "please wait" is said if they take long, and speech carries on meanwhile.

### Fixed
- Mac style: after reading from a field with the VO keys (VO Command Shift H from Claude's prompt), the first letter typed was taken as a quick-navigation key and only the later ones went into the field. A typed key now goes straight back to the field (reported by Oliver).
- If a chosen voice went silent, the guide now says how to get speech back: Command Control T for VoiceOver, then one line in Terminal (under "If something goes wrong").
- VO Right and VO Left along a big window (Music's grid, System Settings) asked the application thousands of questions a key; the answer is kept for a moment while you step along the same group.
- The log's "ms after the last key" figure was nonsense before the first key.
- TurnOver now has automated tests that run on every build, and a way of recording a window so an app can be tested without it running (TESTING.md).
- Quitting TurnOver from outside (a kill, an installer) now tidies up as a quit from the menu does: the top row back to the media keys, the curtain off.
- A BAUM display unplugged while TurnOver was using it could crash it later; fixed.
- Switching TurnOver off and on again at once could leave its keyboard layer half torn down; each start now has a layer of its own.
- A hand-over to VoiceOver that needed a second try could be read as you pinning the app to VoiceOver by hand; fixed.
- The code that decides which focus reports to follow is now nineteen named rules, one per special case, with tests; it should behave exactly as before, so please report any app where the focus seems to go astray.
