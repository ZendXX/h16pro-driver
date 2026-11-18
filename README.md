# H16PRO Open Driver

An unofficial, open-source settings page for the **XUNFOX / XUNSVFOX H16PRO** wireless gaming mouse.
It runs in your browser with no install, in a retro terminal style, in a window or fullscreen.

By **Hers**.

## Features

- Pick the lighting effect (applies live)
- Set the six DPI stages (200 to 12000) and choose the active stage
- Set the report rate (125, 250, 500 or 1000 Hz)
- Read the current settings from the mouse and save changes back
- Keyboard or mouse navigation, black and white themes, windowed or fullscreen

## Use it

1. Open `index.html` in **Chrome or Edge** (other browsers do not support WebHID).
2. Plug the mouse in with the Type-C cable, or use the 2.4G USB receiver. Bluetooth is not supported by the page.
3. Close the official web driver tab if it is open.
4. Choose **Connect mouse** and pick the device in the browser popup.
5. Change settings, then choose **Save to mouse**.

Keys: Up/Down move, Left/Right change a value, Enter runs or cycles an item.

## Limits

- **No single-color lighting.** The mouse firmware only has built-in animated effects plus "Turn off the light". Nothing in the protocol sets a color.
- The names of the lighting effects follow the order of the official driver's list and may not match the mouse's numbering exactly.
- Button remapping and macros are not implemented.
- This project has **not been fully tested on real hardware**. Use it at your own risk. A wrong packet could change settings you did not intend, so read the settings first and keep the official driver as a fallback.

## How it works

The page talks to the mouse over WebHID (usage page `0xFF01`, usage `0x10`) using the same packet layouts as the maker's public web driver: a config read (`55 0E A5 0B 30 ...`), a config write (`55 0F AE 0A 2F ...`) and a live light command (`55 21 ... mode`).

## Contributing

Issues and pull requests are welcome, especially: confirmed lighting effect numbers, button remapping, and test results from other firmware versions. Please include the log text from the page when you report a problem.

## License

[MIT](LICENSE). Not affiliated with, or endorsed by, the mouse's maker.
