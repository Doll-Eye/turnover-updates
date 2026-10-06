# TurnOver 1.0, build 9

### New to try
- TextEdit joins the previews: TurnOver menu, Preferences, Applications, TextEdit, "TurnOver leads".

### Fixed
- First run: TurnOver never asked for Input Monitoring, so on a new install it could not take over until you found the setting yourself. It now asks straight after Accessibility, and if macOS doesn't show the question, TurnOver explains and opens the right page of System Settings.
- Braille: plugging the display in by USB while it was connected over Bluetooth left it with nothing on it. TurnOver now moves to USB by itself, notices when a Bluetooth display stops answering, and keeps looking for a display after losing one.
- Braille: with the TurnOver menu open, the display's joystick and keys moved through the application behind it (Mail's message list) instead of the menu. They now drive the menu: up and down move, the routing keys or joystick press choose, letters typed on the braille keyboard jump to items, and space with dots 1 2 closes it.
