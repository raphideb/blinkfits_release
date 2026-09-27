# BlinkFits

This is the binary release repository for **BlinkFits**, a small Windows tool for blinking FITS
images: flipping back and forth between frames of the same field to spot what changed.

Website, documentation and help: https://crashdump.info/astronomy/blinkfits/

## Download

Each release provides two files:

- `blinkfits.zip` - the download. It contains `blinkfits.exe` (the program: one file, no
  installer, no runtime, no DLLs - just run it) and this readme.
- `blinkfits.zip.sha256` - the SHA-256 checksum of the zip.

To check that the download is complete and unchanged, run this in PowerShell in the download
folder and compare the result with the value in `blinkfits.zip.sha256`:

```powershell
Get-FileHash .\blinkfits.zip -Algorithm SHA256
```

After unpacking, check the exe the same way. The SHA-256 of `blinkfits.exe` in version 1.2.0 is
`1bdd30edc5f8292f92c4a349fd6a2cf5cd96482cf625ea13f469b1e9261308e0`:

```powershell
Get-FileHash .\blinkfits.exe -Algorithm SHA256
```

## Changes in version 1.2.0

- New: Find trails tags images with satellite or plane trails as _trail.
- New: Find blur tags images whose stars are larger than in the sharpest frame as _blur.
- New: Allowed blur deviation (%) slider, 0 to 200 percent in steps of 10, default 20.
- New: Remove trail/blur tags renames every tagged file back and forgets tags taken off with M.
- New: M on a tagged image takes the tag off; M again marks it with your own suffix.
- New: Show trails, Show blur and Show marked limit the list and blinking to those images.
- New: Mouse wheel zooms around the pointer, through every step from 5 percent to 10x.
- New: Magnify slider, 2x to 10x, below Zoom.
- New: X opens Move marked to folder.
- New: The move dialog opens in the folder you used last.
- New: Move marked to folder also moves images tagged _trail or _blur.
- Help: restructured, with a table of contents and a Top link on every section.
- Help: new sections for Find bad images and Move marked to folder.
- All 15 languages updated for the new functions.

## Changes in version 1.1.0

- Multi-image selection: Shift + arrow keys, Shift/Ctrl + Home/End, Ctrl + A and click
  modifiers build a selection; Esc clears it.
- Marking and moving act on the whole selection, with per-file results, so one locked file no
  longer stops the rest.
- The automatic blink runs over the selection when two or more images are selected, wrapping
  within it. Starting the blink no longer clears the selection.
- Rotate: R turns the selected frames 180°, for subs taken after a meridian flip. Only the
  display is turned - the file is never written, and a debayered frame keeps its colours.
- Help: the keyboard reference moved to the top and became a table of keys and actions, shared
  with the hints in the control panel.
- Translations updated in all 15 languages for the new strings.
- New download page at https://crashdump.info/astronomy/blinkfits/, with a screenshot and
  instructions for checking the download.
- Tests added for selection and rotation.

## Windows warnings

BlinkFits is not code signed, and it is not downloaded often enough yet for Microsoft to know it. Windows might therefore warn about it even though nothing 
is wrong with the file.

**Windows says "Windows protected your PC" (SmartScreen)**

Click **More info**, then **Run anyway**. This is needed only the first time.

If you are unsure, compare the checksum as shown above before running the program.

## License

© 2026 Raphael Debinski, all rights reserved. BlinkFits is free to download and use for any
purpose. Redistributing, selling, modifying it or passing it off as one's own work is not
permitted without written permission.
