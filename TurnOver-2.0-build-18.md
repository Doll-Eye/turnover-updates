# TurnOver 2.0, build 18

A week of fixes from your reports, and safer settings.

### New to try

- **Who reads, everywhere at once.** Command Control Comma, then A, goes round three modes: TurnOver in its apps (as
  now), TurnOver everywhere (VoiceOver keeps only the apps you give it), and VoiceOver everywhere (TurnOver steps
  back but keeps running). Each mode remembers its own apps; Command Control Comma, then T, still switches the app in
  front. Also in the TurnOver menu, Applications, Who reads (Mohammad, Ashley).
- **Your keyboard language said.** Switching input source with Fn, the Globe key or Control Space says the new one,
  as VoiceOver does (Mohammad).
- **Mail says its autocorrections** while you write: "corrected to the" (Chelsea).
- **Moving by formatting in documents.** VO-Command-B, I, U, K, O and P (with Shift for previous) find the next
  bold, italic or underlined text, colour or font change, or plain text in Word and TextEdit, not only on web pages
  (Mohammad).
- **The layer key's list.** After Command Control Comma, Down Arrow lists TurnOver's commands to arrow through;
  Return runs one.
- **The browse mode sound both ways.** TurnOver now plays a sound when it goes back to browse mode by itself, as well
  as into focus mode (Ashley).
- **For plugin makers:** the plugin listing (summary, contact, abilities, privacy, licence, changes) and
  `turnover-plugin check --listing`, which checks it and your keys without the app running (PLUGIN-GUIDE.md).

### What to test

- Safari: from Google's search box, Command L, an address and Return; then a favourite. The new page should be
  announced once, in browse mode.
- Mail: in a reply, move through the quoted part (quote levels said), and Command ' and Command Option '. Then
  Command Shift D: "sent", straight away.
- Word: VO-Command-T to a table, then the arrows. A table with Arabic in it. VO-Command-B through bold text.
- Moving by character through a misspelled word: "spelling error" once going in, "out of spelling error" coming out.
- Command Control Comma, then T, in an app VoiceOver is reading: TurnOver should take it.
- ChatGPT or Brave: Shift H and Shift B back through a page.
- Arabic text in TextEdit: Right Arrow at the start of a paragraph. Typing Arabic in Safari or TextEdit: each letter
  and word said.
- Command Control Comma, then A, three times: round all three modes and back.
- Switching your keyboard language, if you have more than one.
- Word: VO-T twice: alignment and line spacing at the end.

### Fixed

- Privacy, from the full review of 14 Oct: TurnOver's log on disk now keeps only the length of what was said, not
  the words (the words go into a feedback report only when you choose "with what TurnOver said"); typing on a braille
  display in a password field is never logged or echoed; what was spoken privately (a code from a notification) is
  never written by the braille display either; the AI plugin brief carries no spoken text; screen recognition drops
  its text when closed; the places remembered on web pages are stored without the page's address or search terms.
- Say all no longer stops for good on empty lines in web editors, which then left the arrows silent.
- Escape in a web page ends the by-hand focus mode choice too, so the next field switches by itself again.
- Escape, the browse-mode key and Command Control Comma and Period can't be taken away in the keys menu.
- Uninstall asks on a second list before removing anything.
- A word half typed on a braille display is dropped, with a tone, if the focus moves before it is finished, and typed
  before any command runs.
- Quitting from outside (TurnOver Key, an installer) tidies up without waiting on a stuck main thread.
- The hand-over to VoiceOver no longer toggles while VoiceOver is still starting or stopping.
- Faster: Word checks for a table once a second instead of before every arrow key; quick-navigation letters no longer
  rebuild a changing page on every press; a very long page says "page read in part"; each focus change costs half
  the round trips; chat views ask the app for the window once in half a second.
- Find (TurnOver F) lets you switch the keyboard language while the prompt is open, so you can search in Arabic or
  any other language (Mohammad).
- Desktop items whose kind Finder doesn't give are named by their file extension instead of only "2 of 2" (Tyler).
- The battery report says whether the Mac is charging or on battery, and how long to full or how long is left
  (Mohammad).
- Safari: a page opened afresh, or in a new tab, starts at the top; only Back and Forward return to where you were
  (Mohammad).
- Safari: VO-Shift-M (Shift F10 in the Windows style) on a link opens the link's own menu, with Open in New Tab and
  Copy Link (Mohammad).
- Arabic and other scripts read one letter at a time in their own voice, not named by the English voice ("Arabic
  letter alef"), in screen recognition and everywhere else (Mohammad).
- Apps that rest the focus on an unnamed group between items (Spring's timeline) no longer have the list around them
  said again and again ("Home, grouping" on every arrow; Oliver).
- Up and Down at the top or bottom of a box holding one line (a reply, a message, a prompt) read the line, as in a
  one-line field; documents still only bump. Apps whose line positions are wrong (Spring's reply box) are read by
  paragraph instead of saying nothing (Oliver).
- Mail: coming back to Mail with the focus on the message's scroll area now reads the message; the arrows only
  scrolled it, silently (Oliver).
- Marking a moment (Command Control Comma, then J) says just "marked"; the count climbing with each press sounded
  like something going wrong (Oliver, JC). The count is in the TurnOver menu, Send feedback.
- Safari: a new page starts in browse mode. Focus mode left over from the page before (Google's search box) kept the
  new page from being announced, and the arrows went to the page (Ashley). The page title is said once, not twice,
  and Return in the address bar no longer says "new line".
- Mail: quote levels are said while you write a reply, and Command ' and Command Option ' say the new level (Ashley).
  "Sent" is said as soon as the message goes, not after the window behind it (Oliver).
- Word: VO-Command-T puts the cursor in the table's first cell, so the arrows carry on from there (Mohammad).
- Arabic in a table cell (and anywhere TurnOver speaks text in another script: a name, a list item, a message) is
  read by the Arabic voice; the English voice said nothing (Mohammad).
- Audio ducking now uses macOS's own ducking, the way the system lowers sound for its voices: no "record system
  audio" permission, no sound passing through TurnOver, less battery. TurnOver's voice stays at full volume (Choom,
  on AppleVis).
- WhatsApp and Messages: Tab and Shift Tab follow the screen: the sections (WhatsApp), the conversations, the
  messages, the message box. Shift Tab from the box goes up to the messages (Oliver).
- WhatsApp and Messages: moving through the chats is quicker: TurnOver remembers where the list is while you arrow,
  instead of searching the window at every move (Oliver).
- WhatsApp: the chat you open no longer disappears from the list. WhatsApp shows the open chat's row differently
  (as text, not a button), and TurnOver left it out (Oliver).
- Marked moments can be forgotten without sending them: TurnOver menu, Send feedback, Forget the marked moments
  (Oliver, JC).
- WhatsApp: after Return opens a chat, what you type in the message box is echoed again. WhatsApp moved its focus to
  an unnamed group a moment later, and TurnOver followed it there, where typing isn't echoed (Oliver).
- Typed Arabic letters and short words are said in the Arabic voice in Safari, Brave and TextEdit (Mohammad).
- Word: VO-T pressed twice adds the paragraph's alignment and line spacing (Mohammad).
- Moving by character, "spelling error" is said on entering a misspelled word and "out of spelling error" on leaving
  it, in your main voice, not on every letter (Mohammad).
- Right to left: Right Arrow at the start of an Arabic paragraph no longer gives the edge sound when it has moved
  (Mohammad).
- ChatGPT, Brave and other Chromium apps: Shift H, Shift B and the other backward quick keys work (Mohammad).
- Command Control Comma, then T, follows who is reading: where VoiceOver reads an app, TurnOver takes it, even with
  automatic switching off (JC).
- Making a plugin with ChatGPT, Gemini or Claude no longer freezes TurnOver while it looks at the app: the freeze
  handed the Mac to VoiceOver and, as Alex couldn't speak meanwhile, TurnOver switched the voice to Reed. A voice that
  has spoken is never swapped now (Ashley).
- Say all: an arrow that carries say all on no longer reads the line twice.
- Settings: only TurnOver itself writes them; what was there before each change is kept (settings-previous.json),
  and a copy a day for a week (settings-history), so a bad change can be undone.
- A full disk no longer stops TurnOver (its log writer gave up on it); log lines are lost instead.
- This build is smaller inside: the internal names programs carry are taken out before it is signed.
