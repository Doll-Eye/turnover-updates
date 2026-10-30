# TurnOver 2.0, build 22.2

### Fixed

- After the Mac wakes and is unlocked, TurnOver comes back. The lock turns VoiceOver on for the login window; the notice
  of that arrived only after the wake, minutes later, and TurnOver took it for VoiceOver turned on by hand, so it stayed
  off until quit and started again. The lock's own VoiceOver no longer counts, and once secure input is off TurnOver
  looks again for up to ten seconds until an ordinary app is in front.
- TurnOver Settings: Tab and Shift Tab are TurnOver's own in its window: the sidebar, then the section's controls in
  screen order, round and round, whatever the Mac's Keyboard navigation setting says. With that setting off (the Mac's
  default) the window's own Tab reached the sidebar and the ducking pop-up and nothing else, and TurnOver's generic
  Tab fallback, sorting the sidebar by its middle, skipped the top half of the pane. Reported by four people on
  AppleVis; reproduced here with the setting off and on.
- Copying VoiceOver's settings with a Siri voice chosen in VoiceOver no longer sounds like a failure: the copy is
  reported, then that the voice is a Siri voice, which Apple gives to Siri and VoiceOver alone, so TurnOver keeps its
  own, with where to choose another. Reported on AppleVis.
- NVDA and JAWS keys: Left Option on its own, when the Dock doesn't take the focus (macOS's own Move focus to the Dock
  shortcut turned off), says so and where to turn it on, instead of nothing. Reported on AppleVis.
- The shortcut menu (VO-Shift-M; Shift F10 or Right Option in the NVDA and JAWS styles) opens the menu of the item
  TurnOver is on: its own menu action where it has one, else a right click in the middle of it. Control Return, the
  fallback before, opened nothing in Finder or Safari, and on one Mac the desktop's menu instead of the item's. With no
  item, TurnOver says so. Reported on AppleVis.
- VoiceOver keys: after VO-Shift-Down into Safari's toolbar, VO-Right moves along it and bumps at its end. Safari
  sends the focus TurnOver had put on the button back to the page, and the cursor followed it there: VO-Right then
  bumped at once, or landed on the window's close button. Issue 106.
- A password field says, once a run, that Tab or Shift Tab leaves it: macOS keeps every key from TurnOver in a
  password field, so VO-Left and VO-Right can't. Issue 107.
- WhatsApp: Return on a conversation checks that it is the one now open before going to its message box. WhatsApp
  answered the press with success and kept the conversation already open, so a link pasted and sent went to the
  wrong person. On a mismatch the row is selected instead; if that fails too, TurnOver says which conversation is
  open and stays in the list.
- Spotlight on macOS 27 is read: Command Space says the search field, the letters typed go to it, Tab reaches the
  microphone, Escape says it closed (Urh's change; Spotlight's panel is drawn by "Siri AI" there, which TurnOver didn't
  follow). Reported on AppleVis.
