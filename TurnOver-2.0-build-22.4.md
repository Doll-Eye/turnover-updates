# TurnOver 2.0, build 22.4

### Fixed

- Open and Save dialogs are read: a file dialog in TextEdit, or "browse for file" on a web page in Safari. macOS
  draws them in a separate service, which TurnOver ignored as a process that isn't an application; the service
  serving the app in front now counts as that app. Reported by Maldalain (issue 14).
- After the Mac wakes and is unlocked, TurnOver takes over again when the swap is off. TurnOver turns VoiceOver on
  for the lock screen, which it can't read; with the swap off it then never turned VoiceOver off again, so VoiceOver
  stayed in charge after every wake until it was turned off by hand. A VoiceOver that was already on before the Mac
  slept stays on. Reported by the maintainer.
- App Store: Return on a search result opens it. The results page's container reports no size, so every row counted
  as off screen and Return said "could not reach … try again" for an app plainly on screen; the page's list, or the
  window, now gives the area, and a page with no scroll bar asks the row to scroll into view. Search results that
  arrive in stages (11, then 24, then 36 for "water") are read again as they settle, the place kept by name, and the
  Store's own hit test, which lags a new results page, is given up to a second to agree before the icon is clicked.
  Reported by the maintainer (Keynote, from a search for Pages; then the water apps).
- VO-Left and VO-Right can move past segmented controls, such as the buttons in a SwiftUI picker, without getting
  trapped between their segments.
- Finder's desktop: each item says its own place ("3 of 35"), not "35 of 35" for every one. Reported by jcast77
  (issue 140).
- TurnOver Key: pressing Command Control Period again just after "TurnOver off" no longer leaves the key doing nothing
  until its helper restarts (a contributor's change).
- An app that refuses TurnOver's notification sign-ups as it comes forward (Telegram from the Mac App Store) no longer
  holds TurnOver up for seconds: the second try runs off the main thread, as the first one does (a contributor's
  change).
- Windows style: Option D, which opens the Desktop folder, no longer leaves TurnOver silent while macOS asks for
  permission to the Desktop folder (a contributor's change).
- Copy VoiceOver settings reads a VoiceOver export that stores its voice the newer, flattened way; it failed with
  "no voice" for such an export (a contributor's change).
- Pages: a document just opened can be read with the arrows. Pages reported its page layout as the focus, with no
  caret in it; the body text takes the focus instead (a contributor's change).
- Next and previous item reach the texts between the buttons of a System Settings pane, which said "nothing to
  review" at every press (a contributor's change).
- JAWS keys do what JAWS's do: Caps Lock Apostrophe, Option Caps Lock X, Caps Lock V and Caps Lock F3 have their
  JAWS meanings rather than the Windows style's keys underneath; Caps Lock F7, F6 and F5 list a page's links,
  headings and form fields; and Caps Lock Left and Right Arrow stay the previous and next item in a text field (a
  contributor's changes).
- Clicks are made as a hand makes them, the pointer there first and the button held a moment, so a dialog that
  ignored a quick click (Bambu Studio's) takes it.
- Turning VoiceOver on uses VoiceOver's own shortcut first, which is quicker, and opens VoiceOver only if that fails.
- The TurnOver layer's K changes the keyboard style without TurnOver stepping in where VoiceOver leads, and the new
  style's name is said once, not by both readers.
- The spoken Tab hint in password fields is gone: it got in the way of moving around.
- Settings: the Experimental group is a plain section; its disclosure triangle wouldn't open from the keyboard.
- The control channel between TurnOver, its Settings window and TurnOver Key keeps every message whole under load,
  and a late reply can no longer reach the wrong client (a contributor's change).
- Plugins from the library: an archive that expands well beyond its stated size, or holds files its listing doesn't
  show, is refused (a contributor's change).
- Speech: when TurnOver's voice never starts as it is needed (the system voice stuck), VoiceOver is given the speech
  back instead of staying muted. Issue 71.
- Starting TurnOver waits until its keyboard access is really working before it mutes VoiceOver, so a start can't
  leave keys unheard. Issue 52.
- Moving by character keeps a letter or emoji made of several parts whole, in text fields and in Terminal.
  Issues 159 and 180.
- Searching a window for the next heading, link or control no longer holds TurnOver up, and results that arrive
  after you've moved to another app are dropped. Issue 119.
- App Store: pages are read in the page's own order, the first content is read before shelves further down finish
  loading, a late page load can no longer move the selection or act on an old row, and confirming a purchase needs a
  fresh press of its own. Issues 54, 173, 174 and 176.
- Music, Podcasts and TV: pages are read one at a time and a late read is dropped, the selection stays on the same
  item when the page refreshes, and actions go to the window you're in. Issue 182.
- TV: choosing Home in the sidebar goes to Home's page instead of staying on Search, and shelves are read as soon as
  they're ready. Issue 186.
- Word: page reading checks that the window and the page range are still current, and Word's own sound at the start
  or end of the text is left to Word, so it isn't heard twice. Issue 178.
- Mail: a message is read even when it sits beside an editable reply area. Issue 179.
- Safari: a late reply from Find or a tab switch is no longer spoken after you've moved on. Issue 181.
- Speech recovery: a voice queue still stuck after sleep or wake-up grace gets another recovery attempt. A late
  replacement cannot overwrite a player that has recovered or been replaced, and restarting waits at most two
  seconds for its spoken warning, even if the system voice is stuck too. Issue 155.
- Privacy: typed keys and braille cells are kept out of diagnostic logs, braille typing echo stays out of speech
  history, and deleting a pending braille cell in a password field does not speak it. Helper diagnostics no longer
  keep page titles or element text. Feedback reports remove old input and helper diagnostics even when speech is
  included. Issues 60, 61, 62 and 68.
