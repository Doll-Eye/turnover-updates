# TurnOver 2.0, build 25

### New to try

- Your own sound sets: Settings, Sounds has two new buttons, "Open the sound sets folder" and "Make a starter set", and "Whose sounds" also lists every folder of audio files you put there, one file per event; where a set has no file TurnOver's own sound plays, and an empty file is silence.
- With VoiceOver's sounds chosen, activating an item, turning the rotor, a search wrapping round the page, a window coming to the front (not the Finder desktop) and a dialog or system prompt appearing now play VoiceOver's own sounds.
- Mouse tracking: Settings, Item details, "Read what is under the mouse pointer as it moves" (or NVDA+M in the Windows
  keyboard style) reads each item the pointer crosses, as VoiceOver's cursor following the mouse pointer does. It is off
  until turned on. The keyboard focus never moves with the pointer; the review cursor goes to the item, as NVDA's review
  cursor follows the mouse. The cursor follows the pointer only into the app in front, or the app the keys are in:
  an item in another app's window, on the Dock or in the menu bar is still said, and the cursor stays where it was. A blank place (a window's background, a group with no name) is silent, and coming back to an
  item reads it again. Each new item cuts off whatever is being said, as VoiceOver does when the pointer moves: a tester
  found that notifications, live announcements and the speech from opening a chat kept talking over the pointer, which
  made it no faster than the keyboard.
  The whole lookup, the item's name, role, value, state and a group's item count, is read off the main thread under one
  deadline, and only the finished text is handed back, so an app that stops answering cannot freeze TurnOver. This
  reads less than the keyboard does: app-specific names (Mail, Excel, Finder, Calendar, Dock, Terminal and others),
  plugin and profile labels, the Item details order and toggles, position information and the "goes in" hint are left
  out.
  What it says is private: it is not kept in the speech history, and the log holds only the kind of item and the app,
  never its words. It watches the pointer only while TurnOver is the reader, and it waits while Say All or the
  trackpad's explore is reading. If an app holds the lookup for over a second, the lookup is given up and the
  pointer is read again.
- Deleted text by pitch: Settings, Speech, "Lower the pitch for deleted text, instead of saying deleted" says a
  deleted character or word lower, as VoiceOver does, without the word "deleted". Off by default. A deleted capital
  is lowered too when capitals are raised.

### Changed

- The test program no longer plays any audio: one switch (AudioOutput.muted), set first thing in the tests, makes every
  place that starts a sound file, tone, bell, system alert or spoken warning skip the playing and still log and report
  as before. Builds that ran tests used to be heard at random. TurnOver itself is unaffected.
- The log now has one line for every sound TurnOver plays, "sound: <name> (why: <what asked for it>)", so a sound that
  cannot be accounted for can be traced to its cause. Nothing is heard differently.
- Claude: Return in the prompt, when it sends the message, now says "sent" at once. Claude's own progress lines wait
  until it has been said.
- A text field that holds only a space, such as PayPal's empty code boxes, is now read as "blank", the word for an
  empty field, not "space". A space typed or deleted inside text is still named.
- Finder: choosing an order in View, Sort By says "sorted by" and its name, for example "sorted by Date Created",
  once the menu has closed.
- VoiceOver Shift End on a long page that is read only in part says "reading on" at once while the rest is read, then
  the bottom line when it gets there. It is not said when the bottom is already read, nor again for a repeat press.
- Automatic focus mode for caret movement is on by default. Arrows, quick navigation and VoiceOver's keys put
  the keyboard in the field you reach; VO-Left and VO-Right can move on. Turn it off in Settings, Web pages.

- Finder: opening Quick Look on a sound or video file now says nothing, so the clip is heard. With Quick Look open,
  an arrow to a clip of five seconds or less plays it and then says its name; a longer clip, or one whose length is
  not known at once, says its name at once. The name is not said if you press another key first. Nothing else from
  the Quick Look window is said while a clip is selected. Other files are read as before.
- Finder: opening Quick Look on any other file says that file's name in place of "Quick Look, window".
- Menus: Up Arrow on the first item and Down Arrow on the last now wrap round to the other end.
- Dock: the menu of a Dock icon is now found and read even when the Dock sends no notice that it opened.

### Fixed

- After an update, and when TurnOver quits with "turn VoiceOver back on" switched on, VoiceOver now comes on in a
  fraction of a second. TurnOver had been opening VoiceOver as an app, which on macOS 27.2 sits for about ten seconds
  before it reads, so the "what's new" pages came up with nobody reading them. TurnOver now presses VoiceOver's own
  on and off shortcut first, as the hand-over between apps already does, and opens the app only if the shortcut does
  not bring VoiceOver.
- Launching an app from Finder no longer makes TurnOver say the bare word "application": an activation notice that names no running application is ignored.
- Claude: Space on a checkable item in a menu that stays open, such as "Goal" in the "Show" menu, now says the item's new state, for example "Goal, checked".
- Safari: H (and the other quick keys, and a choice from the Elements list) on a heading too long for one line now reads
  the whole heading, as VoiceOver does, not its first line with the rest left for Down Arrow.
- Claude: Command 1 to 5 (and the other numbers) names the conversation it lands on at once, and says it once. The
  sidebar's Recents list had changed shape, so the row could not be read and the answer waited, came late or was missed.
- Sounds, with "VoiceOver's" chosen: more of VoiceOver's own sounds now play on the event VoiceOver uses them for. A
  search that finds nothing plays NotFound, a menu opening plays MenuDown (a context menu no longer plays the popover
  sound as well), and a page that has loaded plays WebPageLoaded, the file VoiceOver names for it, where TurnOver
  played WebAreaLoaded. "TurnOver's" sounds are as they were. Every sound file of both sets is now prepared in the
  background from the start of TurnOver, never on the main thread, so a first play can no longer hold up speech or
  keys; one asked for in the first moments before it is ready is skipped, never played late. These sounds play after
  the spoken message is queued.
- Sounds, with "VoiceOver's" chosen in Settings, Sounds: TurnOver now plays a sound only where VoiceOver has one, and
  plays VoiceOver's own file for it. Before, the sounds TurnOver made up (the focus tick, pressing, headings, lists,
  landmarks, tables, pictures, quotes, comments, the browse and focus mode tones, the jump beeps) played as well, so
  the sounds were not VoiceOver's. The gate is now at the lowest level, so the waiting beep, the "marked" sound and
  the beep when an app finishes installing are silent too; only startup, take-over, hand-back, the progress beep and
  the stand-ins for a missing VoiceOver file still play. With "TurnOver's" chosen nothing changes. TurnOver Space, switching between
  browse mode and focus mode, now plays VoiceOver's single-key Quick Nav on and off sounds. The page-loaded sound plays
  once for each page load, not again when the same page is read again.
  When TurnOver changes between browse mode and focus mode by itself (landing on a text field, or leaving one), there
  is no sound with VoiceOver's sounds chosen, because VoiceOver plays none there. The focus mode and browse mode sounds
  named in the fixes below are heard with "TurnOver's" chosen.
- An app or a web page that stops answering: after a few seconds TurnOver now says the app's name and "is not
  responding", or "the page is not responding" when the app still answers and only its page does not. It says so once,
  and says "is responding again" when the app or the page answers. Before, "please wait" was all that was said, however
  long the wait. Only the app in front is spoken about.
- Safari: Up and Down Arrow in a box that holds one character (the digit boxes on PayPal's code page) now answer at
  once, as they do at the top of any line. Before, Down waited about a third of a second.
- Safari: the list a pop-up button opens (Amazon's Quantity) is no longer taken for a page of its own, so the heading
  and other browse keys no longer say "nothing on this page yet" over it. Why the Down Arrows after the second were
  silent in that list is not yet known.
- Mail: Up Arrow on the first message and Down Arrow on the last now say "top" and "bottom", as Finder's lists do.
  Before, you heard the edge sound and nothing was said.
- Safari: Tab on a page answers as soon as the new focus can be read, not after a fixed third of a second. After Safari
  was relaunched, every Tab took about 0.36 s because Safari sent no news of the focus; TurnOver now asks Safari
  every 25 ms and speaks the control as soon as it has moved.
- Safari: "please wait" is no longer said falsely while you Tab quickly down a healthy page. A focus that TurnOver
  read from the page itself now counts as a sign the page is answering.
- Find (Turnover F): Tab, an arrow, a Command key such as Command Tab, or a Turnover key now closes the Find prompt
  and does what it always does. Before, the prompt stayed open until Return or Escape, and took every such key
  without a word, even after Command Tab to another app, so Tab, the arrows and Turnover's keys seemed dead until
  TurnOver was turned off. Switching to another app in any way, opening TurnOver's menu, locking the Mac and a
  password field's secure input also close it now. Typing, Backspace, Return and Escape work in the prompt as before.
- Find (Turnover F): switching to another app while TurnOver is waking an app's accessibility now closes the Find
  prompt too. Before, the prompt stayed open, and what you typed in the other app went into Find.
- Find (Turnover F): a Quick Nav arrow pressed straight after Turnover F now stops the prompt from opening, and moves
  as always. Before, the prompt could open just after the arrow and take the next letters you typed.
- Find (Turnover F): switching to another app, opening TurnOver's menu or locking the Mac straight after Turnover F
  now stops the prompt from opening. Before, it could open a moment later over the app you had switched to.
- Closing the Find prompt with a Quick Nav arrow no longer writes to TurnOver's log while the arrow is being handled,
  so a slow disk can no longer hold up the keys.
- Safari: VoiceOver Space on a link that opens its page in the same tab now reads the new page as soon as it has
  loaded. Before, nothing was said until you pressed a key.
- Safari: after VoiceOver Space on a link, a Quick Nav arrow or a keypad key now counts as moving on, as other keys
  do, so where the focus goes next is read at once. Before, it could be held back for up to five seconds.
- When an app leaves the Mac's secure input on after you leave a password field, as Safari did on Steam's sign-in
  page, VoiceOver now takes the keys a second later, and TurnOver takes them back a second after secure input goes
  off. Before, TurnOver heard none of your keys until you left the page. Nothing is said, and inside a password field
  TurnOver reads as before.
- When an app leaves the Mac's secure input on after you leave a password field, as Safari does on some sign-in and
  password pages, VoiceOver no longer comes on in TurnOver's place. TurnOver goes on reading where the focus goes,
  and a password field's length as before. Nothing is said about secure input. TurnOver's own commands still wait
  for the page to let go of it.
- TurnOver's own menu: Turnover with Right Arrow and Left Arrow now move to the next and previous item, as Down
  Arrow and Up Arrow do. Before, they gave the edge sound and nothing was said.
- Claude: Command and a number now says a conversation's title only once the conversation it chose has arrived, so
  the title you hear is the one you are in. Before, it could say the wrong one: the conversation you were leaving
  when you pressed the key just after sending a message, the one in between when you pressed two numbers quickly,
  or "Claude" while the page was still loading; sometimes it said nothing. Now TurnOver reads the sidebar's Recents
  afresh after the key, waits for the page to take that row's title, and says only the last key's arrival. A slow
  page still has the row's name said after three seconds, and "no conversation" and the conversation already open
  are said as before.
- The log now says how long each step of an app coming to the front takes, and what the main thread was busy with
  when a key was answered late, so that a slow first switch to an app such as WhatsApp can be traced to its cause.
  Nothing is said differently; this is the first step towards fixing that stall.
- Mail: Command and a number that chooses the mailbox already showing now reads its list at once. Before, it waited
  a second and a half for a new window title that could not come. A mailbox key is known this way after it has been
  used once in the session; the first use still waits for the title, as before.
- Claude: pressing "Copy code" from browse mode now says only "Copied". Before, it first read out the groups round the
  button ("Side chat, grouping; Chat messages, grouping; ..."), and "Copied" could come seconds late or not at all.
- A slider's value is no longer said twice when the page announces the same change twice in a few milliseconds, as a
  video's seek slider did at every second. A different value, or the same one a moment later, is still said.
- Finder: arrowing into a list that is still reloading no longer says "empty" just before the file it comes to. Before,
  a list with no rows for a moment was called empty at once. Now TurnOver waits a tenth of a second for the list to
  answer, and a folder that really is empty still says so.
- Finder: with Quick Look open, Up Arrow and Down Arrow (and Left and Right in an icon view) now say the file the
  selection moved to. Before, the keys moved the selection under Quick Look and TurnOver said nothing.
- Finder: with Quick Look open, Up Arrow on the first file and Down Arrow on the last now say "top" or "bottom" at
  once. Before, TurnOver waited almost half a second for a selection that could not move and then said nothing.
- Claude: coming back to the Claude app now says "Claude, window" and then where you are. Before, "Claude,
  grouping" was said after the window every time, from the group round the whole app, which has the window's name.
- Claude: when Command and a number puts you in the new conversation's Prompt, you now hear only its title and the
  focus mode sound. Before, the start of the Prompt's own announcement was heard just before the title.
- TurnOver no longer stops answering for several seconds when an app in the background, such as Mail, is slow to
  answer while its list changes. Before, keys and speech could stop for six seconds and VoiceOver came on.
- Mail: switching to Mail now says its window, such as "Mail, Inbox – Personal – 495 messages, window", every time.
  Before, now and then Mail's main window was read as a dialog, its whole message list was read out, and when Mail was
  slow TurnOver could stop answering until VoiceOver came on.
- Mail: in Save Attachments and any other sheet or dialog, Tab and Shift Tab now move through the panel, from its
  search field to its list of files and its buttons. Before, the panel's list of files was taken for Mail's mailbox
  list, and Tab tried to go to the message list, found nothing and was lost. Mail's other keys (Return in the search
  field, Command Shift N, Escape and the rest) are left to the panel too, so Command Shift N there makes a new folder.
- Open and Save panels, in any app: as the panel opens you hear its title and the folder it is in, for example "open,
  dialog, Downloads", said once. Before, TurnOver looked through the whole panel for words to read, which held keys up
  for as much as a second, found none, and then said the panel's inner window as a second dialog.
- Open and Save panels: when the panel goes to another folder, with Option Command L, Command Shift D, Go to Folder
  or a folder you choose, the new folder's name is said once. Before, nothing was said, so you could not tell where
  the file would be saved. If the panel stops answering, TurnOver stops listening for its folder rather than let your
  keys wait.
- Web pages: when a reading key or a quick navigation key (such as F) lands on a text field and TurnOver moves the
  keyboard into it for you, you now hear the field's name and the focus mode sound only. Before, the name of the group
  the field sits in was said after it, as if you had moved into that group yourself. Tab and clicks still say the group.
- Safari: Tab and Shift-Tab pressed while a new page is still being read in now say "loading page", as the heading key
  does. Before, they went to the page, which was not answering yet, and said nothing.
- Typing: Backspace at the very start of a field, or in an empty one, now plays the edge sound at once. Before, it waited
  a fraction of a second for a caret that could not move and then made no sound at all. The key still goes to the
  application. Not used where the line has right-to-left text, or when Backspace deletes a word or a line.
- Browse mode: a key that would type something but has no command, such as a slash, a comma, a dash or an Option
  symbol, is kept from the page, and now says "browse mode" once the keys stop, as a letter does. Before, only
  letters and digits did, so a punctuation key kept from a field that still had the keyboard was silent.
- Browse mode: Backspace and Delete, with Shift, Option or Command, are kept from the page and say "browse mode", as a
  letter does. Before, a text field that still had the keyboard while you read, such as the Claude app's Prompt after
  VO arrows crossed it, had a character, a word or a line deleted from it. In focus mode they edit as before, and on a
  page whose focus is not a text field they still go to the page.
- Browse mode: VO-Space on a line of text with one link in it, such as Mail's "Unsubscribe." line, now presses the
  link, as VoiceOver does. With several links it presses none and says their names, and on a label the page pairs
  with its field it goes to the field. On plain text it says "nothing to activate" at once. Before, it waited and
  then said "nothing to activate". Return and Space are unchanged.
- Browse mode: "browse mode" for a kept key is said at once, not about half a second later once the keys had stopped.
  A kept key soon after it neither cuts it off nor says it again; any other key still stops it.
- Browse mode: on a long page that keeps changing, such as a long Claude chat, VoiceOver's find keys (VO Command H and
  the like) answer from the copy of the page TurnOver already holds, and wait for a fresh copy only when what they look
  for is not in it yet. Before, they waited two to four seconds for a fresh copy whenever the page had changed. A key
  waiting for a fresh copy, F included, is no longer dropped without a word because another key came first: it is
  answered, unless a later key has moved the reading or is waiting itself, and then that key is answered.
- Browse mode: on a page read only in part, such as a long Claude chat, pressing VO Shift End or Command Down Arrow
  again while TurnOver is still reading on to the bottom no longer cancels the first press. Before, each press cancelled
  the one before, and three presses said nothing. Now the read goes on and the bottom line is said once.
- Safari: after Return in the address field, a key pressed before the new page has arrived no longer acts on the page
  you have just left. Before, Space, Return, a quick navigation letter or Tab pressed in that moment could press a link
  on the old page, or move through it, a fraction of a second before the new page appeared. Now TurnOver says "loading
  page" and does nothing with the key; once the new page has arrived, or the old one is seen to stay, keys work again.
  If a key was refused and the old page turns out to have stayed, its current line is read, so you know the keys work
  on it again. A page still loading waits up to twenty seconds; if nothing new has come by then, the old page's line is
  read and its keys work again. Command keys, such as Command-C and Command-A, and Escape are never refused.

- Browse mode: after F, or another quick navigation key, says the name of a text field, what you type straight away
  goes into the field. Before, a key pressed in the instant between the field's name and the field taking the keyboard
  (a Backspace, a letter, Space) left TurnOver in browse mode, so that the next letters ran as commands. Those keys are
  now held for a moment and typed into the field once it has the keyboard, in the order you typed them and ahead of
  anything typed after them, a Backspace saying what it deleted as usual; if it does not take it, they run as they
  would have. If the focus goes to another field, or the page or the app goes away first, they are not typed anywhere:
  the edge sound plays instead. Return, Tab, the arrows, Escape, VoiceOver's keys and F or Shift F pressed again still
  move on, as before.

- Browse mode: after you turned Quick Nav off and then left focus mode with a heading key, F onto a text field no longer failed to switch to focus mode (the letters you typed were kept from the page). Leaving focus mode now ends the by-hand choice.

- Quick Nav no longer switches itself on: Left and Right arrows count as the turn-on chord only when pressed within 150 milliseconds of each other, and a half-seen first arrow is forgotten when the keyboard connection restarts or you change application.

- Heading and link keys say "application switcher is open" in your language too, not only in English.

- A waiting system dialog reminds you once, with at most one further reminder after five minutes, instead of repeating on every application switch.

- Claude's conversation shortcuts return to focus mode when the destination Prompt has keyboard focus, so typing goes into the Prompt after the page changes.

- Claude conversations with identical titles announce their destination once it has loaded, without waiting for the eight-second ceiling.

- Missing Claude conversation numbers preserve the Prompt’s mode; an unavailable sidebar waits for an unchanged URL at the ceiling instead of reading the current title.

- Repeating a Claude conversation shortcut while the page rebuilds says only the final destination.

- Claude’s slash-command suggestions speak when opened and as Up and Down change the choice. Choosing an Effort menu item confirms the choice after focus returns to the Prompt.

- Finder says “opening” immediately when Command Down opens a selected application, while the application starts.

- Claude's conversation shortcuts say only the destination title once, without the " - Claude Code" suffix or
  an extra first-line announcement. Title-only changes are recognised, and the wait's ceiling reads the current
  title afresh. A verified already-open conversation answers immediately; a number beyond the sidebar's
  conversations says "no conversation" and its number without changing mode.

- Notes: Return and Space in the held Folders list now announce the selected folder, or explain why it could not be chosen.

- Notes: view shortcuts announce their destination and focus; Tab leaves attachments for folders and notes.

- Notes: Tab and Shift-Tab reach folders, notes and the open note in list and gallery views.

- Unnamed controls say their known role or stay silent, instead of being called unknown.

- Claude's Command 1 to 9 say the conversation title even when that conversation is already open.

- Dialogs open with their text and focused control, without listing unnamed fields; explicit descriptions keep named choices.

- Reading the saved copy of an unresponsive page no longer asks the page about automatic caret focus.
- A delayed automatic field-focus event no longer pulls the reading position back after another command.
- Recovered button presses wait for keyboard activation to finish, or report failure at the shared focus deadline.
- VO-Space activates Claude's focused session-menu Delete command when VoiceOver keys are active.
- A button replaced since the page was copied can be found near its old position or at the end of a long page,
  including labels inside nested groups, with one bounded fresh-copy retry.
- Claude's Command 5 to 9 use conversation-switch handling, dialog notices are immediate, VO-Right leaves an
  empty Prompt, and session menu activation uses the keyboard when its accessibility press does nothing.
- Typing: Left and Right bump at once at the edge of a text field with left-to-right text, where they used to wait
  for the caret first (over 300 ms in a web field). Not used where the line has right-to-left text, with a
  selection, with a modifier key or in a table cell.
- Typing, VoiceOver's keys: with words spoken as you type, the word said as the space is typed is no longer followed by
  "space", as in VoiceOver. A space typed on its own is still said, and NVDA's and JAWS's keys say both.
- Automatic changes between browse mode and focus mode play the mode sound after the destination field’s words,
  even with navigation sounds off. Ordinary keys carry an interrupted cue to the current field or reading
  position; Control stops it. Brief changes within one key or refresh stay silent.
- Quick navigation onto an editable field plays the browse-mode sound after the field when typing would still navigate.
- The manual mode toggle and Escape keep the mode words, or the sound with navigation sounds on.
- Command F in Maps says "search" followed by the focus-mode sound.
- Returning to a page with the keyboard in a text field reads that field and resumes focus mode when automatic
  focus mode is on. Space after pasting stays in the field instead of pressing another control. A manual browse
  mode override, automatic focus mode off, and returns to other controls keep the saved reading position.
- Claude's sidebar session status waits until keys and speech are quiet, keeping each session's newest notice
  through title changes. The open conversation's own assertive notices keep their ordinary delivery.
- The command layer is audible while VoiceOver leads. Reading-mode changes wait for the reader of the current
  app to be ready, including confirmed VoiceOver muting when TurnOver speaks while VoiceOver is running.
- Safari no longer says "please wait" when it answers a focus check without moving the focus.
- At the bottom of a changing page, repeated forward keys answer from the copy once its end has been checked.
- Claude's progress lines wait for speech to finish as well as quiet keys, keeping each conversation's newest
  waiting notice until it can be said, even after a minute, without repeating its last delivered line.
- Claude's conversation shortcuts say the new name promptly without holding up the keys; waiting page commands
  run once after a short settle if the conversation stays the same, or when the wait reaches its limit,
  while Claude stays focused. Leaving Claude discards those waiting commands.
- Wrapping round a page with the heading, link and other single-letter keys is immediate again: at the end of a page
  TurnOver no longer reads the whole page again before "wrapped to the top", unless the page has changed. Previous
  heading at the top of a page wraps to the bottom even while the page is being read again, instead of saying "top".
- After the Mac sleeps, VoiceOver is no longer turned on and straight off again for the lock screen, and after the
  unlock TurnOver takes the keys if neither reader is on.
- Speech that gets stuck just after an unlock, such as when the sound moves to other headphones, recovers within
  seconds instead of staying silent.
- Typing in a field on a page whose form is in a frame of its own, with Safari's AutoFill, no longer drops back to
  browse mode, so the letters go into the field.
- Buttons that open a menu, such as the Claude app's model and permissions buttons, stay in browse mode when Tab
  reaches them, as in NVDA.
- In browse mode, a letter that is not a command says "browse mode", so letters that were not typed are not lost
  without a sound.
- Pressing a button that opens or closes something says expanded or collapsed straight away.
- Tab on a page reads where the focus went, even when the page sends no news of it.
- A page that fills in after it first appears is read again, so Tab and the quick keys find all of it.
- After Return in Safari's address bar, a line of the page being left is no longer read before the new page.
- Find in browse mode goes round the page, and says so.
- Secure input left on after a password is told sooner when you are pressing keys TurnOver can't hear.
- Claude app: a reply is no longer read just after you send a message while Claude is working; Claude Code's plan is
  left out of the reply that is read; a reply you are already reading is not started again from its top; progress
  lines wait until you stop pressing keys; switching conversations says which one.
- Mail: switching mailboxes with Command and a number reads the new mailbox, not a row of the old one.
- Up and Down in an empty list say "empty" at once, and Backspace in an empty field answers at once.
- The link sound plays once for a line, not once for each link on it.
- The app you are leaving is no longer read over the Command Tab app switcher.
- When VoiceOver stops without turning itself off (it crashes, or is stopped from outside), TurnOver now speaks once
  it takes over, starting with "VoiceOver stopped. TurnOver is speaking." Before, it took the keys but said nothing,
  because macOS still said VoiceOver was on, so the Mac was silent.
- VoiceOver started by TurnOver itself, when it stops responding, restarts or quits, no longer counts as you
  choosing VoiceOver for the app in front. Before, after a restart Mail could be kept with VoiceOver as if you had
  turned it on there by hand. Turning VoiceOver on yourself still keeps that app with VoiceOver until TurnOver quits.
- Command Tab back and forth between an app TurnOver reads and one VoiceOver reads now changes reader once, for the
  app you end up in, after you let go of Command and VoiceOver has finished starting or stopping. Before, each switch
  started its own change, so the readers could swap several times in a row, and one could give up and leave the app
  with the wrong reader until you switched again.
- Quitting TurnOver, or stopping it with Command Control Period, just after it changed reader for an app no longer
  risks leaving the Mac with no speech. Before, a check of the reader that was still waiting could turn VoiceOver off
  again while TurnOver was bringing it back as it quit.
- After TurnOver restarted itself because it had stopped responding, VoiceOver that its watchdog had started could
  still keep Mail, or the app in front, with VoiceOver as if you had chosen it by hand. TurnOver now remembers its own
  start across the restart even when VoiceOver is still off as the new TurnOver begins.
- Turning VoiceOver on or off yourself with its own key is always taken as your choice for the app in front. Before,
  doing it within three seconds of TurnOver changing reader for an app was taken as TurnOver's own change, so the app
  was not kept with the reader you chose, and TurnOver could change it back; and turning VoiceOver on just after
  TurnOver had restarted VoiceOver itself was taken as TurnOver's start. When TurnOver cannot tell whose it was, it
  now takes it as yours. Your choice now also holds in the half minute after TurnOver recovered from not
  responding, and a change of reader TurnOver had already started no longer opens VoiceOver over it. This holds in a password
  field too, where TurnOver cannot hear your keys.
- When VoiceOver comes back after it had stopped without turning itself off, TurnOver now stops speaking at once.
  Before, TurnOver could go on talking over VoiceOver for up to about four seconds.
