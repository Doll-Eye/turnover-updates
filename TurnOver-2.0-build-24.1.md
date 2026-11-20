# TurnOver 2.0, build 24.1

### Fixed

- In a toolbar, in any app, Left and Right move to the previous or next control, with the edge sound at either end
  instead of silence, and Escape goes back to the window's content (the place you were before the toolbar; in Finder
  the files, in System Settings the pane or the sidebar). A text field in the toolbar keeps its own keys. Up, Down,
  Tab and Shift+Tab are unchanged. Reaching a toolbar now says "tool bar", even where the kind of an item is left out
  of what is said.
- Two rows with the same words, one above the other, are both read when you move quickly between them, such as two
  copies of one message in Mail's list. The second was not spoken.
- "Nothing in this window can be read", with the keys for screen recognition, is a hint now: turning off Hints after
  a pause turns it off too. It is no longer said in Steam's Big Picture while TurnOver is reading it.
- In the Claude app, VO-Space, Return and Space press the button the reading position is on. Some buttons, such as
  the answers offered under a reply and the sessions in the sidebar, made the pressed sound and did nothing until
  Tab had put the keyboard on them.
- On a web page, Return, Space and VO-Space press text that the page takes clicks on, such as the "Yes" and "No"
  answers of a questionnaire made without real buttons. They used to say "nothing to activate".
- Selecting with Shift and the arrows is read again in the Claude app's prompt, or a page's text field, after coming
  back from another app. It said nothing until the focus moved.
- A menu bar item whose menu does open, such as a VPN app's, no longer says "could not open" first. The press can
  report an error and the menu still appear a moment later, and a menu that opened and closed quickly was counted as
  one that never opened.
- TurnOver no longer says "Secure input is on, so TurnOver cannot hear your keys" when the Mac goes on hiding the
  keys after a password field. It cut in on ordinary sign-in pages: in Safari, while moving through the controls
  beside the password field, and at a password prompt in Terminal. The log still records it. If TurnOver's own keys
  stop answering after a password, Command-Tab twice brings them back.
- Arrowing along the Dock's own list says an item's name alone, "Safari", not "Safari, dock item, selected".
- The Dock's hint names the keys that move along it: Left and Right for a Dock at the bottom of the screen, Up and
  Down for a Dock at the side. It said Up and Down wherever the Dock was.
- In browse mode a page is now gathered in the background. A slow or large page should no longer hold up the keys
  while it is read in.
