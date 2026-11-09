# TurnOver 2.0, build 23

Features wait for a whole build; point releases carry fixes only (27 Oct 2026).

### New to try

- Searching in the App Store, Music and Podcasts: Return in the search field reads the results as a plain list, from
  Apple's public catalog, and Return on one opens its page. The App Store's own results page couldn't be read reliably
  on macOS 27.2. When the catalog can't answer, the page is read instead. TV keeps its own page, as Apple TV+ isn't in
  the catalog.
- Screen recognition finds a window's controls as well as its text: the recognition key pressed twice (VO-Shift-Y,
  or TurnOver R) finds them, in under a second; pressed once, it reads the text. Each row is a control ("Save,
  button") and Return clicks it. It uses Apple's on-device recognition and, with Apple Intelligence on, the Mac's own
  model, which is given a few seconds to add what it sees; nothing leaves the Mac. macOS 26 or later.
- After Return clicks something in a screen recognition result, the screen is recognised again a moment later, so a
  dialog's OK is followed by the screen that comes after it without pressing the key again. Settings, Screen
  recognition, "After Return clicks something, recognise again" turns it off, and the result closes after a click
  as before.
- Screen recognition can recognise again whenever the screen changes: Settings, Screen recognition, "Recognise again
  when the screen changes" (it was "Read new text as it appears"). The window is looked at each second, and when it
  has changed, the result is updated and what is new is read; for controls too. Off by default.
- Screen recognition reads cards side by side as cards: a name over a button, four across, was "Download Download
  Download Download" and then the four names (Parallels' installation assistant, issue 73); now each card is a row,
  top to bottom, and Tab moves between them. The controls result reads in the same order as text: a sidebar before
  the pane beside it.
- A screen recognition result that comes back after you've moved to another app no longer opens over it.
- Natural voices for everyone: 25 English voices made on your Mac, on Apple silicon with macOS 15 or later. In
  Settings, Speech, beside Voice, choose Download natural voices (about 170 MB, once; Remove natural voices takes them
  off again). Then pick one under Voice to speak everything,
  with the rate, volume and EQ as for any voice, or under Natural voice for say all only. Other languages keep your Mac
  voice. They are Phonon's voices; Kokoro's, the first natural voices, are gone, and a Kokoro voice chosen before
  becomes Maeve.
- Progress bars beep as they move, as in NVDA: a short beep for each percent, rising in pitch from low at 0 to high
  at 100. To hear the percentage instead (as before), both, or nothing, choose in Settings, Sounds, or in the
  Verbosity list (VO-V). With NVDA keys, NVDA+U goes through them. A bar's beeps keep up with it as it moves, rather
  than once a second. App Store downloads follow the same choice: beeps, or the app's name and percentage every 10
  percent while the App Store is in front (it was every quarter, wherever you were), and "installed" at the end, as
  before. A page's progress bar is now a line in browse
  mode, so it can be read and followed.

### Changed

- Settings has a Sounds section: whose sounds, the sounds as you move and press, what you hear as TurnOver takes over,
  progress bars, and lowering other sounds while TurnOver speaks (from General and Speech). With NVDA keys,
  NVDA+Control+U opens it, as it opens NVDA's Audio settings.
- Settings, Speech: "In the rotor", under Voice, puts the voice chosen there among the voices VO-Command-Shift steps
  through, or takes it out, without going through every voice's switch below.
- In a menu, a letter that leaves the same item highlighted (r, then u, for Russell) says that item again, where it
  said nothing.
- The speech settings ring ends at punctuation: its last stop, sync with VoiceOver, has gone. VoiceOver's settings
  are copied from the TurnOver menu, Copy VoiceOver settings.
- The Games item has gone from the TurnOver menu's Tools: game reading is always on, and Steam's Big Picture switch and
  Restart Steam are in Settings, Other apps' speech.
- Braille: panning to another line moves the caret there, so the arrows carry on from the line read. The Braille section of Settings offers Line by line (the default), To the text shown, or Off. Tethered to review, panning moves only the review cursor.
- Braille: Apple USB and HID drivers are polled and written on the braille thread, as Bluetooth drivers are, so a
  display does not hold up speech. Reads and writes cannot enter each other while a driver waits, the latest
  pending frame is kept, and handing back to VoiceOver waits for the driver to unload.

- VoiceOver keys: VO-Shift-L only describes: the picture under the cursor, or anywhere else what the window looks
  like. VO-Shift-Y, a key of TurnOver's own (VoiceOver has none for it), recognises the window's text to read and
  click, which VO-Shift-L used to do away from a picture. The notice for a window with nothing to read names both.
  Describing a window needs the Mac's on-device model (Apple Intelligence on). Where VoiceOver reads an app,
  VO-Shift-Y is VoiceOver's; the TurnOver layer's R (Command Control Comma, then R) recognises there.
- An app whose window accessibility doesn't report at all (Parallels Desktop's virtual machine) is treated as a window
  with nothing to read: TurnOver says so and names the screen recognition key, and screen recognition reads that
  app's window, not the whole screen with the windows behind it.
- A window with nothing TurnOver can read (a custom-drawn or OpenGL window: Parallels' installation assistant, Bambu
  Studio's plate) says so a moment after it comes to the front, and names the key for screen recognition in the
  keyboard style in use: VO-Shift-Y with VoiceOver keys (and VO-Shift-L to describe it), the TurnOver key with R with
  NVDA or JAWS keys. It said
  "window" and then nothing. Issue 74.
- The verbosity manager: Settings, Item details now lists what is said about an item, in the order it is said (name,
  kind, value, state, help text, keyboard shortcut, position, level), each on or off, moved up or down with a button.
  "For" chooses the list for everywhere or for the app last in front. (It orders an item's pieces; a Mail message's
  sender, subject and time come as one name, so their order isn't changed by it.) The three old switches (help text, shortcut, position) are rows of the
  list now; a settings file from before keeps their values.

### Fixed

- An app allowed to speak through TurnOver could speak once after you'd switched away: the line that asked is now said
  only with the app still in front. Issue 56.
- A web page cut short at the reader's size limit said nothing and was taken as complete; it now says "page read in
  part", as a page cut at the time limit does. Issue 58.
- Notification banners went unread after Notification Centre restarted, until VO-O was pressed. Issue 80.
- A Settings window left open across an install knocked on the new TurnOver every two seconds; it now stops and says to
  open Settings again. Issue 77.
- With NVDA or JAWS keys where VoiceOver reads, a style change could leave the key layer without its tap. Issue 53.
- Settings, Sounds, "Whose sounds" counted only in part with VoiceOver off: choosing VoiceOver's left the boundary,
  headings, moving and pressing on TurnOver's set. VoiceOver's now plays VoiceOver's own sounds for links, misspellings,
  boundaries, pop-ups, a braille display and the rest it has, and TurnOver's set for what VoiceOver says instead
  (headings, lists, moving and pressing, the modes); TurnOver's is the set throughout. Until you choose, VoiceOver's, as
  before; with VoiceOver off that now means its boundary and braille display sounds too.
- VoiceOver's sounds were quieter than TurnOver's own, by 5 to 10 dB for most, so a link's blip all but vanished: each
  now plays at the set's loudness. A page loaded plays VoiceOver's "web area loaded" sound, the one in its own list.
- Copy VoiceOver settings copied nothing on macOS 27.2 when VoiceOver's export kept its voice in a new place; it now
  finds the voice there and copies the rate, verbosity and typing echo with it. Issue 221. Reported by a tester.
- Settings, Speech: the voices for other languages and the rotor's voices couldn't be reached from the keyboard. Each
  list is now behind a switch that Tab stops on. Issue 225. Reported by a tester.
