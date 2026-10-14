# TurnOver 2.0, build 18.1

A small build on the heels of 18, for one bug worth having at once.

### Fixed

- After a menu closes with Escape (TextEdit's spelling menu, a context menu in any app), the text area is the focus
  again and the arrows read. In build 18 TurnOver could lose the focus there, and the arrows went quiet until you
  switched apps (Oliver).

### What to test

- In TextEdit, VO-Shift-M on a misspelled word, Escape, then the arrows: they should read the text.
