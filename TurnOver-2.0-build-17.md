# TurnOver 2.0, build 17 (in progress)

TurnOver is now built in Swift 6 language mode with the main-actor default: the compiler checks every thread
boundary (speech, the key tap, the background page walks), which is why the version number moves to 2.0.
Nothing changes in how it is used.

### Keys that moved: please read this first

TurnOver now has three sets of keys. In the Mac style, VoiceOver's keys do exactly what they do in VoiceOver. In the
Windows style, NVDA's keys do exactly what they do in NVDA. And TurnOver's own commands sit behind one key, the same
in both styles, that works even in an app VoiceOver reads: **Command Control Comma, then a letter** (Oliver).

Why one key: Apple's own apps use nearly every Command Control letter (we read the menus of Finder, Safari, Mail,
Terminal, Preview, Xcode and more: Command Control N, T and R alone are taken by five or six of them), and TurnOver
shouldn't take shortcuts away from the apps you use. JAWS users will know this as a layered key. **Tell us what you
think of it**: Send feedback, or reply on AppleVis.

- **Command Control Comma, then N: the TurnOver menu.** In the Mac style, VO-N is now VoiceOver's: the notifications
  you've heard lately. In the Windows style, Caps Lock N still opens the menu, as NVDA's does.
- **Command Control Comma, then T: hand the app in front back to VoiceOver** (or back to TurnOver), and remember it.
  The TurnOver menu, Hand over or quit, does it too. VO-V is now VoiceOver's verbosity list, and Caps Lock V NVDA's
  screen layout. Nothing is lost: the way back to VoiceOver is always there.
- **Command Control Period: start or quit TurnOver**, a single press, from anywhere (it was Command Control T).
- The other letters: **S** settings, **K** keyboard style, **J** "that was wrong", **Slash** the shortcuts here,
  **P** the plugin maker, **C** copy the last thing said, **H** the guide, **I** describe a picture, **R** screen
  recognition. Any other key says the letters; Escape or three seconds cancels.
- In the Mac style, VoiceOver's own keys for these work too: VO-H twice the commands, VO-Slash a custom label (the
  plugin maker), VO-Shift-Slash the guide, VO-F8 settings, VO-Shift-C copy the last phrase, VO-Shift-L describe.
- **The latest messages in Messages and WhatsApp, and the parts of a window in apps with panes, are Command Control
  1 to 9** (those apps' own keys, where TurnOver reads them). In the Mac style, VO-1 to VO-0 are now VoiceOver's hot
  spots; in the Windows style, Caps Lock 1 to 5 are NVDA's again (input help, typed characters and words, command
  keys, dynamic content).
- Windows style, as NVDA: Control stops speech and Shift pauses it; Caps Lock Up and Down Arrow move the review
  cursor by line (Caps Lock L reads the line, Caps Lock A says all); Caps Lock Shift Z is sleep mode for the app in
  front. Mac style, as VoiceOver: Control pauses and carries on.

### New to try

- **Keys have moved.** TurnOver's own commands are Command Control Comma, then a letter, in both styles and any app:
  N the menu, T hand the app to VoiceOver or back, S settings, K keyboard style, J that was wrong, Slash the
  shortcuts here, H the guide, I describe a picture, C copy what was said, R screen recognition, P the plugin maker.
  Command Control Period starts or quits TurnOver. In the Mac style VoiceOver's keys, and in the Windows style NVDA's,
  do exactly what they do there.
- **The Mac style is VoiceOver's.** 178 of the 189 commands in Apple's VoiceOver guide behave as in VoiceOver, among
  them the notifications list (VO-N), verbosity (VO-V), hot spots (VO-Shift with a digit to set, VO with a digit to
  go), the speech settings (VO-Command with the arrows), the help menu (VO-H), the Find commands (VO-Shift-F),
  style changes and same-level headings (VO-Command-C, VO-Command-M), tables (VO-R, VO-C, VO-Shift-T), paragraphs
  and sentences, and moving and resizing windows.
- **The Windows style is NVDA's.** 114 of the 130 commands in NVDA's reference: the review cursor, table navigation
  (Control with Command and the arrows on a Mac keyboard), the clipboard (Caps Lock C), repeat (Caps Lock X), sleep
  mode (Caps Lock Shift Z), screen layout (Caps Lock V), the synth settings ring, and Control to stop speech and
  Shift to pause it.
- **The keypad.** Mac style: VoiceOver's NumPad Commander, with VoiceOver's own keys; VO-Clear turns it on. Windows
  style: NVDA's desktop layout (7 8 9 lines, 4 5 6 words, 1 2 3 characters, keypad 0 held as the NVDA key); Clear
  switches between commands and typing numbers.
- **Audio ducking.** Other apps' sound is lowered while TurnOver speaks: Settings, Speech, or Caps Lock Shift D in the
  Windows style. Off to start with. The first time, macOS asks to let TurnOver record system audio; nothing is kept.
- **Plugins.** Label an unnamed button, give an item a key, have it read when it changes, or keep it quiet: VO-Slash,
  or Command Control Comma then P. A careful first step: plugins can do more in coming builds, each asking for what
  it needs.
- **Google Docs, Sheets and Slides.** TurnOver reads Google's own announcements as you move and type, as NVDA does.
  Google's screen reader support must be on: Command Option Z in a document; TurnOver tells you if it's off.
- **System prompts.** Prompts that appear behind your app ("would like to use your location") are read, and Tab and
  Space work in them.
- **The TurnOver menu is tidier.** This app first, then Settings, Apps, Keys, What to test, Send feedback, Tools,
  About and updates, Hand over or quit.
- **Microsoft Excel.** Cells are read as you move, content then address ("Monday, A2"); selecting says the range.
- **Right Option T.** It says the time, and twice quickly the date.
- **Your own keys.** TurnOver menu, Keys: give any key to a command, or take one away.
- **Speech.** Capitals can be said at a higher pitch, and speech can play on a chosen device: Settings, Speech.
- **Messages, Finder and Safari.** In Messages, Command T opens the Tapback reactions as a list. Finder reads desktop
  and icon view items with their kind. Safari says the new tab's title as you switch tabs.

### What to test

- The layer key: Command Control Comma, then N, S, K, J; and in an app VoiceOver reads (Calculator, say).
- Your usual work in your usual style: anything a key did before that it no longer does, tell us.
- Google Docs or Sheets, with Google's screen reader support on: moving, typing, the menus.
- The keypad, if you use one, in your style.
- A plugin: label an unnamed button in an app you use, then undo it.
- Ducking, with music playing.

### Fixed

- Word: TurnOver no longer quits when you come back into a table you had just left (Mohammad).

- Typing straight after Backspace in Claude's prompt (and other web text boxes) came late: each Backspace waited for
  the box to report its caret. TurnOver now lets the next key through at once, as NVDA does (Oliver).
- System prompts that appear behind the app you're in ("would like access to record your system audio", "would like
  to use your current location") are now said, as VoiceOver says them, and get the keyboard. In these protected
  prompts Tab and Space go straight to macOS, and if macOS refuses a VO-Space press TurnOver puts the focus back on your
  choice and asks for Space (Oliver).
- In a dialog, Tab and VO-Space now agree: VO-Space presses the choice Tab reached (Oliver).
- VO-Command-C (next style change) gives up after a third of a second rather than holding TurnOver up in a long note.
- The keypad stops speech as other keys do, and leaves sleeping apps and "pass next key" alone.
- Sleep mode no longer traps TurnOver's own menu over a sleeping app.
- "That was wrong" only marks the moment; pressing it twice no longer sends a report by itself.
- The clipboard (NVDA+C), link addresses and notifications are spoken but no longer written into the log or
  reports, which could carry a copied password or a two-factor code.
- The shortcuts list shows only keys that really do what it says in the current style.

- TurnOver Shift T no longer says the time: it was a tester's preference, not NVDA's or VoiceOver's (VO-Shift-T is a
  table's row and column now, in the Mac style).
- Keyboard help names the modifier keys as you press them: command, shift, option, control (left or right),
  function, and caps lock, the TurnOver key. Control no longer pauses speech while keyboard help is on (Oliver).
- Windows style: Control Right goes to the start of the next word and reads it, as NVDA does; it read the text
  passed over (JC).
- Opening TurnOver from Finder or Spotlight no longer leaves you on TurnOver itself ("TurnOver has no windows"): it
  steps back to the app you were in (Chelsea).
- Feedback reports are kept in TurnOver's own folder, the newest ten, not on the Desktop (a synced Desktop sent them
  all to the cloud); a copy goes on the Desktop only when no mail app opens (Chelsea).
- The Voice menu lists voices for the languages set on your Mac, so a Spanish speaker can choose a Spanish voice for
  TurnOver itself (Agustín).
- The function keys are never touched (build 16 could switch off "Use F1, F2 as standard function keys"; turn it back
  on once in System Settings, Keyboard) (Urh).
- Reminders: Tab in a new reminder announced the window between the title and the notes. Tab out of the sidebar had
  been judged "ignored" too quickly, and TurnOver then took Tab over in text fields too. Text fields now always get
  the app's own Tab, and TurnOver waits a little longer before deciding an app ignores it (Oliver).
- Right and Left on a sidebar item answer at once ("expanded", "collapsed"), with the edge sound where there is
  nothing to open; they used to wait and say nothing.
- Text is never announced as "text": iPhone apps on the Mac (Books, Audible) said "Home, text, selected".
- Icon buttons with only a tooltip are named by it, as VoiceOver does (Cyberduck's Back, Forward, Browser,
  Bookmarks and History were just "button").
- Web pages inside apps (Bambu Studio's release notes): list numbers say "1", not "unknown, 1"; a heading is one
  stop, not read twice; icon-font symbols are no longer read as names.
- After waking or unlocking the Mac, TurnOver could hear none of your keys for several seconds (the lock screen's
  password field keeps the Mac's secure input on for a moment). VoiceOver now keeps the Mac until that is over, then
  TurnOver takes back the app in front (Oliver).
- Chrome and Edge: tables are read once, by rows (they were read by rows, then by columns, then the header again);
  each item of a list is its own line (Google Drive's files ran together); toggle buttons say "toggle button,
  pressed", not "check box"; dialogs, menu bars and tool bars are named as you enter them.
- Excel opened fresh: its cells are read from the first arrow (it said nothing until Excel had been open a while).
- Switching to an app whose first focus has no name (Excel) no longer leaves the last app's text box in charge: its
  arrows were answered silently.
- Preview: pages are read as "page", not "unknown, unavailable"; tool groups are "grouping"; lists and other
  containers are no longer said to be "unavailable".
- A dot between words (Byword's "Markdown • 61 words") is read as a pause, not "bullet". A value that repeats the
  name is said once (Excel's headings). Review no longer stops on a table's untitled columns (Ulysses).
- Reminders: Tab between a reminder's title and its notes said the window and the list before each field. The
  window's passing focus is now held a quarter of a second and said only if nothing else takes the focus (Oliver).
- Tabs say which one is showing ("Input, tab, selected, 2 of 2"). On the Mac the arrows move between tabs without
  switching, and Space switches; TurnOver did not say which was selected (Oliver, System Settings' Sound).
- Switches say "switch, on" or "switch, off", as VoiceOver does, not "toggle button, pressed".
- A control reported twice (SwiftUI apps such as System Settings hand over two references for one) is read once.
- Review reads a row once: no more the row, then its cell, then each text in it (Reminders, Contacts, System
  Settings; the duplicates heard in the Windows style). Faster in long lists (Contacts).
- Focus on a scroll area itself says what it holds ("…, scroll area"), where it was silent (Shortcuts' editor).
- Safari: Enter or Space on a button you have tabbed to (a cookie banner's "Accept all cookies") pressed the link
  before it, or went to the group around it. They now go to the button the keyboard is on (Oliver).
- Web pages: misspelled words in fields now say "spelling error", and inside a line, not only at its start (Lorien).
- Live regions inside other live regions are said once, not twice (Mert, The Playroom).
- Finder: Command Down with nothing selected (after Command Up to the top) says so, rather than nothing (Stuart).
- WhatsApp with no chat open: the arrows go straight into the conversations (it said nothing until Tab), the
  arrows and Return work the sections when WhatsApp's own focus is on one, and Escape no longer drops the cursor
  (Oliver, 10 Oct 2026).
- Function keys: TurnOver no longer changes them at all. They behave as set in System Settings, Keyboard ("Use
  F1, F2, etc. keys as standard function keys"). Earlier builds switched them with the reader and put them back
  as media keys every time (Mert).
- TurnOver T reads the window's title as it is now; after a Safari tab switch it said the old one (Mert).
- Space in Podcasts, Music and other lists now plays and pauses, and in Finder opens Quick Look: TurnOver only
  takes Space when the selected row has a check box to tick (Oliver, 10 Oct 2026).

- Speech follows the Mac's output device: headphones or speakers chosen after TurnOver started now get its voice
  (AirPods Max left TurnOver on the speakers, 9 Oct 2026). Confirmed by Oliver switching back and forth.
