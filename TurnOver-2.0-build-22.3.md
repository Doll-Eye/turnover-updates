# TurnOver 2.0, build 22.3

### Fixed

- Typing echo: after a Backspace, the word said at the next space was the word before the one just typed when the
  field was slow to take the space (TextEdit, WhatsApp). The field's word now counts only once the space is in; until
  then TurnOver looks again, and after a tenth of a second says the letters typed.
- JAWS keys: Caps Lock H reads the sentence, as in JAWS; it opened the Speech settings (a contributor's change).
