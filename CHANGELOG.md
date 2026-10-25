# Changelog

What changed for the user in each release. The full text of each release, in English and
Russian, is on the [releases page](https://github.com/ALEXalesha/IntelligenceDrawer/releases).

## 1.3.1 - 2026-09-25 - The installer no longer asks for administrator rights

It installs for the current user into `%LOCALAPPDATA%\Programs\DrawGuess`, like the author's other programs. Up to 1.3.0 it installed into Program Files and raised a UAC prompt for nothing the program needed. A copy left in Program Files by an older version is not touched (removing it needs admin rights); the installer says where it is.

Everything else is as in [1.3.0](https://github.com/ALEXalesha/IntelegienceDrawer/releases/tag/v1.3.0): the window opens where it was closed.

64 tests green.

## 1.3.0 - 2026-09-25 - The window opens where it was closed

Its place is written to `%APPDATA%\DrawGuess\window.json` when the window closes and put back at the next start. The window has a fixed size, so only the place is kept and the widgets always set the size: a number in the file cannot crop them. If that monitor is gone or the title bar would land off every screen, the window opens in the middle as before. The placement rule is a port of the `window-state.js` used by the calculators and Paint Pro, and a test checks it against `window-state.js` itself on a thousand random inputs.

64 tests green.

## 1.2.0 - 2026-09-22

First public release on GitHub.

**Several symbols are read as one string.** The network is trained on single symbols; until 1.1 the whole canvas went into it as one frame and "65" came out as "W". The drawing is now cut into symbols by strokes and read left to right, with digit rules on top: `|°` reads as `10`, `b5` as `65`, while a word like `SOS` is left alone.
