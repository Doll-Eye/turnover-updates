# TurnOver 2.0, build 22.5

### Fixed

- Command-B and Command-I report bold and italic on/off in TextEdit rich text and Ulysses with Markdown XL,
  where those shortcuts were silent. Requires the apps’ English menus. Reported by the maintainer. Issue 212.
- After unlocking, VoiceOver stays available until an ordinary app and keyboard input are ready. A failed return
  to TurnOver retains a bounded retry; another lock or a deliberate reader choice cancels stale restoration.
  VoiceOver already on before sleep remains on. Issue 204.
- In JAWS keyboard style, Caps Lock U, O, J, L, M and Period move the text cursor as their arrow equivalents do,
  rather than only moving the review cursor. Rapid reading commands keep their order, the keys work where
  VoiceOver reads, and assigning one of these commands to its own arrow no longer causes a crash. Issue 144.
- Text fields such as System Settings’ search field are read and respond to review keys when the app first
  reports a temporary stand-in before the actual focused field. The focus check does not copy the field’s full
  text. Issue 195.
- Returning to an app in browse mode keeps the reading position and mode when the same control regains focus
  on the same page. Enter and Space act at that reading position instead of jumping back to the focused control.
  Issue 200.
