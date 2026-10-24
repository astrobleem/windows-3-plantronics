# Windows 3.0 on Plantronics ColorPlus

**320x200, 16 colors. [Download PCP3216.ZIP](https://github.com/astrobleem/oemdisplay-tandy/releases/download/experimental-displays-2026-10-12/PCP3216.ZIP)**

For IBM PC/XT with Plantronics ColorPlus and 640 KB. Ordinary CGA, PC1512 and
Tandy/PCjr shared-memory video need different drivers.
Use an existing Windows 3.0 real-mode installation. The driver is ready built;
there is no automatic installer or fresh Windows Setup integration.

## Install

1. Extract the ZIP to `C:\PCPEXP` and exit Windows completely to DOS.
2. Copy the driver:

   ```bat
   COPY C:\PCPEXP\PCP3216.DRV C:\WINDOWS\SYSTEM\PCP3216.DRV
   ```

3. In `C:\WINDOWS\SYSTEM.INI`, set the `display.drv` line under `[boot]` to
   `display.drv=PCP3216.DRV`. Keep the other settings, fonts and grabber.
4. Start Windows:

   ```bat
   C:
   CD \WINDOWS
   WIN /R
   ```

Use your actual Windows directory if different. Dedicated video RAM needs no
RESERVE/JRGUARD step. Use ordinary Windows startup; the Tandy WINXT launcher
and palette animation are for other hardware. This packet keeps your existing
WIN.COM and its startup logo behavior.

## Known limits

The driver passed 88/88 final Windows checks in 86Box. The recorded runs used
an existing AT/EGA installation with EGA fonts/grabber and emulated serial input.
Physical cards and ColorPlus clones, including ATI Small Wonder, are unqualified.
Fresh Windows Setup and DOS-box switching are untested. At 320 pixels, wide dialogs can clip.
Windows 3.1 is not supported.

![Windows 3.0 in the Plantronics ColorPlus emulator](https://raw.githubusercontent.com/astrobleem/oemdisplay-tandy/main/docs/pcp/P86_09.PNG)

## Change back or get help

From plain DOS, use Windows Setup to restore your previous display, or restore
the previous `display.drv` value. The copied driver is inactive afterward.

[Detailed guide](https://github.com/astrobleem/oemdisplay-tandy/blob/main/experiments/DISPLAY3/PCP3216.TXT) ·
[Source and test records](https://github.com/astrobleem/oemdisplay-tandy/blob/main/docs/PCP.MD) ·
[Report a problem](https://github.com/astrobleem/oemdisplay-tandy/issues).
Optional checksums and component notices are in the download/release.
This repository is the front door; implementation lives in [oemdisplay-tandy](https://github.com/astrobleem/oemdisplay-tandy).
