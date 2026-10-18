# Windows 3.0 with Plantronics ColorPlus

320 × 200 pixels · 16 colors · IBM PC/XT with ColorPlus

An experimental display driver for Windows 3.0 real mode on the Plantronics ColorPlus card. Recorded Windows results are from 86Box; physical cards remain unqualified.

## [Download PCP3216.ZIP →](https://github.com/astrobleem/oemdisplay-tandy/releases/download/experimental-displays-2026-10-12/PCP3216.ZIP)

Ready-built **PCP3216.DRV**, installation/rollback instructions, checksums and component notices. Bring your own Windows 3.0 installation; this is a driver packet, not a Windows Setup disk.

[Release notes](https://github.com/astrobleem/oemdisplay-tandy/releases/tag/experimental-displays-2026-10-12) · [Prerequisites](#prerequisites) · [Install](#install-in-a-clone) · [Rollback](#rollback-from-plain-dos) · [Source & support](#source--support)

[![86Box ColorPlus emulator capture: Windows 3.0 Paintbrush reopening a saved 16-color test image](https://raw.githubusercontent.com/astrobleem/oemdisplay-tandy/ba980d4ccf9092c38ea22b006373f420d0f059e2/docs/pcp/P86_09.PNG)](https://github.com/astrobleem/oemdisplay-tandy/blob/ba980d4ccf9092c38ea22b006373f420d0f059e2/docs/pcp/P86_09.PNG)

86Box 6.0 on an emulated IBM XT with Plantronics ColorPlus: Windows 3.0 Paintbrush in 320×200×16. This original 1368×868 emulator capture is linked to the [88/88 test record](https://github.com/astrobleem/oemdisplay-tandy/blob/ba980d4ccf9092c38ea22b006373f420d0f059e2/docs/pcp/P86CHK.JSN), [capture details](https://github.com/astrobleem/oemdisplay-tandy/blob/ba980d4ccf9092c38ea22b006373f420d0f059e2/docs/PCP.MD), and [tested evidence commit ba980d4](https://github.com/astrobleem/oemdisplay-tandy/commit/ba980d4ccf9092c38ea22b006373f420d0f059e2). Emulator evidence only; physical cards and clones remain unqualified.

### Prerequisites

- IBM PC/XT with a Plantronics ColorPlus card and normal 640 KB RAM. The card has 32 KB dedicated video RAM. Ordinary CGA, Tandy/PCjr shared video RAM and PC1512 planar video are different hardware.
- ATI Small Wonder and other ColorPlus-class clones remain unqualified.
- A bootable backup or disposable clone of an existing Windows 3.0 installation, with a plain-DOS recovery route.
- Retain the EGA fonts/grabber configuration used by the recorded AT/EGA cloned-install tests for the first reproduction. Fresh CGA-class Setup/fonts/grabber integration is untested.
- Use a nonanimated WIN.COM and plain Windows startup. ColorPlus needs no RESERVE/JRGUARD step; video RAM is on the card.

Read README.TXT in the ZIP and the [updated installation/recovery guide](https://github.com/astrobleem/oemdisplay-tandy/blob/a9d341d13bc24072c0f870f8ec3fe4caee12c45a/experiments/DISPLAY3/PCP3216.TXT) before changing files. The updated guide also clarifies startup-logo behavior.

### Install in a clone

1. Exit Windows completely. Extract the complete ZIP into a new `C:\PCPEXP`, verify `SHA256.SUM` on a modern host, and back up the complete installation/image. Do not reuse an old backup directory.
2. From plain DOS, save SYSTEM.INI:

   ```dos
   COPY C:\WINDOWS\SYSTEM.INI C:\PCPEXP\SYSBACK.INI
   ```

   Stop if SYSBACK.INI already exists. Record the old `display.drv` setting and preserve any existing `C:\WINDOWS\SYSTEM\PCP3216.DRV` separately.
3. Copy the driver:

   ```dos
   COPY C:\PCPEXP\PCP3216.DRV C:\WINDOWS\SYSTEM\PCP3216.DRV
   ```

4. With a DOS editor, change only `[boot]` → `display.drv` in SYSTEM.INI to `display.drv=PCP3216.DRV`.
5. Start Windows in real mode:

   ```dos
   CD \WINDOWS
   WIN /R
   ```

Substitute your actual Windows directory consistently if it differs. The package does not change keyboard/mouse configuration. Do not use the Tandy WINXT reservation/animation startup route.

### Rollback from plain DOS

Exit Windows completely, or reboot to DOS if Windows will not start. Restore the saved configuration:

```dos
COPY C:\PCPEXP\SYSBACK.INI C:\WINDOWS\SYSTEM.INI
```

Restore any pre-existing PCP3216.DRV you replaced. A newly added driver can remain inactive after restoring the old setting. Restore the complete backup if other configuration changed.

### Recorded results and limits

The exact driver passed **88/88 recorded Windows 3.0 checks** in 86Box 6.0's IBM XT + Plantronics ColorPlus model: desktop redraws, overlapping windows, menus/dialogs, mouse movement, cursors over all 16 colors, Paintbrush drawing/save/close/reopen, exit to DOS and a second launch. [Pinned test results](https://github.com/astrobleem/oemdisplay-tandy/blob/ba980d4ccf9092c38ea22b006373f420d0f059e2/docs/pcp/P86CHK.JSN).

**Physical ColorPlus/cards and clones, RGB output/timing, real serial/bus mice, XT BIOS and keyboard variants, fresh Setup and DOS-box/grabber switching remain unqualified.** Fixed emulator cycles do not establish real-machine performance. The recorded tests used an AT/EGA clone with EGA fonts/grabber and emulated serial input.

[![86Box ColorPlus emulator capture: Calculator dragged over Program Manager and Notepad](https://raw.githubusercontent.com/astrobleem/oemdisplay-tandy/ba980d4ccf9092c38ea22b006373f420d0f059e2/docs/pcp/P86_03.PNG)](https://github.com/astrobleem/oemdisplay-tandy/blob/ba980d4ccf9092c38ea22b006373f420d0f059e2/docs/pcp/P86_03.PNG)

86Box emulator capture: Calculator dragged over overlapping Windows windows. Both images are original captures, not physical-hardware photos or reconstructed frames.

### Startup logo

The packet supplies no splash/logo, runs no Setup and does not rebuild WIN.COM. `WIN /R` retains the existing WIN.COM's startup behavior. A compatible stock loader can show Microsoft's original static logo; a customized loader can show other art or no image. The Tandy wave is not invoked, and there is no automatic logo fallback. Logo appearance/compatibility on ColorPlus has not been separately qualified.

### Source & support

This repository is the documentation and download front door. All implementation, builds, fixes, canonical releases and issue tracking live in [astrobleem/oemdisplay-tandy](https://github.com/astrobleem/oemdisplay-tandy).

- [Report a problem or request a change](https://github.com/astrobleem/oemdisplay-tandy/issues)
- [Matching adaptation/build/test source — DISP3SRC.ZIP](https://github.com/astrobleem/oemdisplay-tandy/releases/download/experimental-displays-2026-10-12/DISP3SRC.ZIP)
- [Release qualification — QUALIFY.JSON](https://github.com/astrobleem/oemdisplay-tandy/releases/download/experimental-displays-2026-10-12/QUALIFY.JSON)
- [Published SHA-256 checksums](https://github.com/astrobleem/oemdisplay-tandy/releases/download/experimental-displays-2026-10-12/SHA256SUMS)

Release/package source: [`37b504be3619032f435381eded7d92a504d8d9da`](https://github.com/astrobleem/oemdisplay-tandy/commit/37b504be3619032f435381eded7d92a504d8d9da). Runtime adaptation and screenshot evidence: [`ba980d4ccf9092c38ea22b006373f420d0f059e2`](https://github.com/astrobleem/oemdisplay-tandy/commit/ba980d4ccf9092c38ea22b006373f420d0f059e2).

`PCP3216.ZIP` SHA-256: `dbeda38a8a9c114ec189fcb82aa269ff36a47e2f128b957abe8ee03f9ce3c545`.

Component notices/license scope are in NOTICE.TXT and LICENSE.TXT; the derived driver is not blanket MIT-licensed. Windows, DOS, fonts/grabbers, ROMs, compilers and original DDK inputs are not included. Do not share installation images or backups containing Windows/DOS files.
