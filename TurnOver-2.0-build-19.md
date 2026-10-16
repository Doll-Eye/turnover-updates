# TurnOver 2.0, build 19

### New to try
- The plugin library is open: TurnOver menu, Plugins, Plugin library. Each plugin says what it can do before it
  installs; every list and download is checked against TurnOver's signature. To start: Xcode (build and test results said as they happen, keys to build, run and test; asked for by
  Ashley), and two examples: Calculator and Bambu Studio.
  No plugin for the app you're in? "No plugin for this app yet", last in the library's list, finds what the app
  is built with. If TurnOver has the parts for that kind of app, make its plugin or post it as wanted for plugin
  makers; if not (Java, Qt, Flutter…), ask for the parts. Only how the app is built is sent, never what is in it. Every plugin can be read in full at github.com/TurnOver-For-Mac/turnover-plugins, and anyone can add one
  there: a plugin that passes TurnOver's checks goes into the library within the hour (CONTRIBUTING.md).
- Making a plugin with an AI: Claude Code, OpenAI's Codex or Google's Gemini CLI open in the plugin's folder and can
  try keys in the app and hear what TurnOver says, as a developer would (TurnOver presses them, says so, and only in
  that app for three hours). Without Codex or Gemini CLI, ChatGPT and Gemini work through their websites as before.
  Each installed plugin in the Plugins menu now has About and Remove; Remove puts it in the Trash.
- The plugin layer (Command Control Comma, then P) lists each command with its key.
- Help wanted: if you use OpenAI's Codex or Google's Gemini CLI, try TurnOver menu, Plugins, Make a plugin for an
  app with ChatGPT or Gemini, and tell me how it goes (Send feedback). I can only test Claude Code here.
- Browse mode: P and Shift P move to the next and previous paragraph of text, past menus and link bars to the
  article; N and Shift N to the text after a block of links, as in NVDA (Andrew).
- Browse mode letters follow each style's reader: the Mac style now has VoiceOver's own single-key Quick Nav (L link,
  X list, C check box, F text field, J control, M heading at the same level, N landmark, D different item, R radio
  group), where it had NVDA's; the Windows style keeps NVDA's, with A now annotation as in NVDA. Caps Lock F7 on a
  page lists its headings, links and fields (Windows style). The rule, from Oliver: Mac keys do what VoiceOver's do,
  Windows keys what NVDA's do.
- The rest of NVDA's browse mode keys (Windows style): I (list item), S (separator), O (embedded object), headings 7 to 9, Comma
  and Shift Comma (past the end of a list, table or other container, or to its start), and in the Windows style
  NVDA+Shift+Space to turn single-letter navigation off for a page (Oliver).
- Mac style, more of VoiceOver's keys: arrow-key Quick Nav with VoiceOver's two-arrow chords, its rotor kinds and
  web pages; VO-Home and VO-End in text; VO-Return selects text; VO-A reads the cursor's contents; VO-F3 the
  VoiceOver cursor; VO-F4 twice; VO-F7 three times (network); VO-Shift-S scrolls.
- Windows style, more of NVDA's: NVDA+S's four speech modes; the desktop layout's keys; NVDA's braille tether,
  braille mode and auto scroll; NVDA+Control+Shift+F1 copies part of the log; Excel's note, elements list and cell
  review; Screen Curtain on NVDA+Control+Escape only (VoiceOver's VO-Shift-Underscore in the Mac style).
- Settings profiles: VO-X (Activities) and NVDA+Control+P (configuration profiles), by hand or for an app.
- TurnOver works with Steam for Mac: Big Picture and Steam's games speak.

### Fixed
- Changing reading mode (Command Control Comma, A) says the mode's name in place of "TurnOver on", not on top of it
  (Oliver).
- Steam's Big Picture: the menu Escape opens (Home, Library, Settings…) can be used with the arrows, Return and Escape
  even when Steam gives it no keyboard focus; the keys go into the menu through the Steam reader (Oliver).
- Speech is no longer 3 dB louder than VoiceOver's: at the same Mac volume, Alex (and every voice) now plays at the level VoiceOver plays it (Oliver's report).
- On a web page, pressing Space or Enter on a video player's button (YouTube's Play) no longer switches to focus mode when "Focus mode when a field takes the focus" is off (Mohammad).
- The keyboard language is said right when it changes: on a Mac with two sources it was said the wrong way round, "ABC" as Arabic came on and the reverse (Mohammad).
- Steam's Add a Non-Steam Game: each program is one line, its name and path with the tick box, and Return ticks it. It read as nameless boxes, names and paths apart (Oliver).
- Steam with a controller: the Home, Settings and Power menu reads as you move through it; it had gone silent after its first item.
- Steam's desktop windows: a tick box says on or off as you switch it with Space or Return, not only when you come back to it.
- Steam's desktop windows: after Tab moves to a button, Return presses that button; it pressed the line the arrows had last been on.
- Steam's game pages: the note beside the main button is read after it, so Resume says why ("Update failed, not enough free disk space") and Play says when you last played.
- Word: tabbing through a dialog's fields (Font) no longer cuts each field to its first letter (Mohammad).
- Word: VO-Command-T and VO-Command-Shift-T move to the next or previous table from inside a table too; they said "no next table" (Mohammad).
- Terminal: a command's output no longer talks over an open menu or over the "terminate running processes?" sheet;
  it's read when you're back in the terminal. VO Right and Left stay inside a sheet (Oliver).
- VoiceOver turned on by hand while TurnOver led, and TurnOver kept the keys because macOS never said so: TurnOver
  now checks for itself every two seconds and steps aside (reported by a tester).
- Windows style, browse mode: Control Up and Down move by paragraph, as in NVDA (reported by a tester).
- If VoiceOver stops but macOS still says it's on, TurnOver speaks after a few seconds.

- App Store: Update works on the Updates page (each update's row went unrecognised, so the press was refused as
  unsafe) (Oliver).
- App Store: while an app downloads, Space and Return say how far it has got (a second Space no longer cancels;
  Delete does), the app's line reads its progress as it is now and then Open, and Open pressed again while a big
  app is starting says "opening" instead of starting it again (Oliver).
- Tables in TextEdit (and other Mac text views) are announced: entering says the table's size and the cell, moving
  says the new row or column, leaving says "out of table" (Mohammad).
- Steam's Big Picture: only the part of Big Picture you're in speaks, so the page behind the menu no longer talks
  over it (Oliver).
- TurnOver reads in Big Picture itself (it runs as a separate Steam app, Steam
  Helper, which VoiceOver kept until now when TurnOver reads only its own apps).

- After a menu closes with Escape (TextEdit's spelling menu), the text area is the focus again and the arrows read
  (Oliver).
- A system dialog left open (the keychain asking for your password, a security prompt) is no longer lost behind
  other apps: TurnOver says it is waiting whenever you switch app, and it is first in the application chooser
  (VO-F1 twice, or Option Tab in the Windows style) (Oliver).
- TurnOver E and Shift E (VO-Command-E in the Mac style) find every misspelled word, in TextEdit and in Safari's
  text boxes when Safari marks none, including the word just typed and one at the very start (Oliver).
