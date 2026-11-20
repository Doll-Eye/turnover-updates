# TurnOver 2.0, build 24

### New to try

- Help improve this app, in the TurnOver menu under This app: tell us what's wrong in the app in front, with a short
  form already filled in with the app and how it is built (never what's in it); fix the item you're on; build a fix
  with your own AI assistant (Claude Code, Codex or Gemini CLI) or by hand; or ask for something new from TurnOver
  itself. It takes over from Ask for this app to be tuned. The guide, Helping TurnOver read your apps, has the steps.
- Share the fixes you make: after labelling an item, giving it a key, or keeping it quiet (VO-Slash with VoiceOver
  keys, or This app, Change the item I'm on), choose Share my changes on GitHub. TurnOver copies them and opens a
  short form. Fixes the project accepts come with TurnOver for everyone who uses that app.
- The welcome pages read like little web pages: Up and Down read a page a line at a time, Return goes on, Escape
  skips the rest. The two keys everything hangs on come straight after the welcome: Command Control Period turns
  TurnOver on and off, and Command Control Comma is the way in to everything.
- VO-J and the window spots work as VoiceOver's do. VO-J goes from a sidebar to its content and back, and from Mail's
  message list into the message; in Music, Podcasts and TV it goes between the sidebar and the page. VO-Right Bracket
  and VO-Left Bracket go through the window's main parts. Wherever you land, the arrows carry on from there. In
  Safari, VO-J goes between a page's main parts, such as a site's sidebar and its content, and from the address bar
  into the page.
- Spotify: in its focus mode, Command with the arrows says what it did: louder, quieter, previous track or next track.
- TurnOver has its own icon, and the menu bar shows a matching symbol instead of the name.
- Help make TurnOver, in the TurnOver menu under Help: the ways to help, from a sentence of feedback to writing code,
  with a button that opens TurnOver on GitHub, and TurnOver's Discord. It opens once by itself after this update.

### Changed

- If you build TurnOver yourself, it installs as TurnOver Developer beside TurnOver, so the TurnOver you have keeps
  its permissions and its updates. The TurnOver menu switches between them, and Command Control Period follows
  whichever you used last.
- The guides describe TurnOver as a second choice beside VoiceOver: one reader at a time, with some apps kept for
  VoiceOver, which Command Control Shift T does on its own.
- Turkish: every string new in builds 23 and 24 is translated.
- Russian: every string is translated, including the settings and the permission prompts.

### Fixed

- Uninstall completely also removes TurnOver Developer, when it is installed.
- Command F4 quits the app in the NVDA and JAWS styles, also when the top row is media keys. It uses the app's own
  Quit, and says so when Quit is dimmed.
- Terminal: the text area is read on a Mac in any language, not only English.
- With secure input on, as in a password field, Command, Option and Shift let go after a shortcut no longer count as
  pressed on their own, so a Command shortcut no longer opens the menu bar in the Windows styles.
- Preview: the first Down Arrow in a PDF no longer waits while the PDF's notes are read.
- TurnOver Settings: a slider's value is said once as it changes, not several times.
- System Settings on macOS 27.2: Control Command 1, 2 and 3 find the sidebar, the settings pane and the search field
  again.
- System Settings: a permission row says its switch and whether it is on, not only the app's name.
- TV: Return on a sidebar item waits for TV to open it, instead of saying it could not; on a heading, such as
  Library, it says it can't be opened.
- Long pages, such as a long chat in the ChatGPT app, are read to the end. TurnOver used to stop at the six
  thousandth item and say bottom part way down; now Down Arrow, the quick navigation letters, Command Down Arrow and
  Say All read on from where it stopped.
