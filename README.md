# BlinkFits

This is the binary release repository for **BlinkFits**, a small Windows tool for blinking FITS
images: flipping back and forth between frames of the same field to spot what changed.

Website, documentation and help: https://crashdump.info/astronomy/blinkfits/

## Download

Each release provides two files:

- `blinkfits.zip` - the download. It contains `blinkfits.exe` (the program: one file, no
  installer, no runtime, no DLLs - just run it), `blinkfits.exe.sha256` and this readme.
- `blinkfits.zip.sha256` - the SHA-256 checksum of the zip.

To check that the download is complete and unchanged, run this in PowerShell in the download
folder and compare the result with the value in `blinkfits.zip.sha256`:

```powershell
Get-FileHash .\blinkfits.zip -Algorithm SHA256
```

After unpacking, check the exe the same way against the `blinkfits.exe.sha256` from the zip:

```powershell
Get-FileHash .\blinkfits.exe -Algorithm SHA256
```

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
