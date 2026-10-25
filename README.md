# Windows 3.0 on Plantronics ColorPlus

**[Download CPPAN.ZIP](https://github.com/astrobleem/oemdisplay-tandy/releases/download/windows-xt/CPPAN.ZIP)**

For an IBM PC/XT with Plantronics ColorPlus, 640 KB, DOS 3.20+ and an installed
Windows 3.0 in real mode. Choose a fixed 320x200 sixteen-color desktop or a
320x400 desktop viewed through a 320x200 screen. The packet includes both
drivers, fonts, grabber, startup artwork and viewport controls.

## Install

1. Extract all files from CPPAN.ZIP to `C:\CPPAN`. Exit Windows to DOS.
2. Run `C:\CPPAN\INSTALL`.
3. In Windows Setup choose Display, Other, `C:\CPPAN`, then the fixed
   **ColorPlus 320x200** or **ColorPlus 320x400 panning** display. Complete Setup.
4. Start Windows from DOS with `C:\CPPAN\CPWIN`.

These entries use Windows at `C:\WINDOWS`. In the panning display, run
`C:\CPPAN\PANCFG` inside Windows once to enable viewport controls.
Dedicated video RAM needs no reservation helper.

Ordinary CGA, PC1512 and Tandy/PCjr shared-memory video use different drivers.
Native Setup and startup passed in emulation; physical cards and clones are
unqualified. Wide dialogs can clip at 320 pixels. Windows 3.1 is not supported.

![Windows 3.0 on emulated ColorPlus](https://raw.githubusercontent.com/astrobleem/oemdisplay-tandy/main/docs/pcp/P86_09.PNG)

[Packaged instructions](https://github.com/astrobleem/oemdisplay-tandy/blob/main/tools/CURRENT/GUIDES/CPPAN.TXT) |
[Technical details](https://github.com/astrobleem/oemdisplay-tandy/blob/main/docs/PCP.MD) |
[Report a problem](https://github.com/astrobleem/oemdisplay-tandy/issues).
Implementation lives in [oemdisplay-tandy](https://github.com/astrobleem/oemdisplay-tandy).
