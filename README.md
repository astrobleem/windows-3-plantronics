# Windows 3.0 on Plantronics ColorPlus

**[Download CPPSET.EXE](https://raw.githubusercontent.com/astrobleem/oemdisplay-tandy/main/downloads/experimental/CPPAN/CPPSET.EXE)**

For an IBM PC/XT with Plantronics ColorPlus, 640 KB, DOS 3.20+ and an installed
Windows 3.0 in real mode. Choose a fixed 320x200 sixteen-color desktop or a
320x400 desktop viewed through a 320x200 screen. The packet includes both
drivers, fonts, grabber, startup artwork and viewport controls.

## Install

1. Put CPPSET.EXE on the DOS computer, exit Windows and run `CPPSET`.
2. Run `C:\CPPAN\INSTALL`.
3. In Windows Setup choose Display, Other, `C:\CPPAN`, then the fixed
   **ColorPlus 320x200** or **ColorPlus 320x400 panning** display. Complete Setup.
4. Start Windows from DOS with `C:\CPPAN\CPWIN`.

These entries use Windows at `C:\WINDOWS`. In the panning display, run
`C:\CPPAN\XTPAN.EXE` inside Windows for viewport controls.
Dedicated video RAM needs no reservation helper.

Prefer a ZIP? [Download CPPAN.ZIP](https://raw.githubusercontent.com/astrobleem/oemdisplay-tandy/main/downloads/experimental/CPPAN/CPPAN.ZIP), extract all its files
to `C:\CPPAN`, then follow step 2. Windows Setup installs the display;
no manual SYSTEM.INI editing or separate support files are needed.

Ordinary CGA, PC1512 and Tandy/PCjr shared-memory video use different drivers.
Native Setup and startup passed in emulation; physical cards and clones are
unqualified. Wide dialogs can clip at 320 pixels. Windows 3.1 is not supported.

![Windows 3.0 on emulated ColorPlus](https://raw.githubusercontent.com/astrobleem/oemdisplay-tandy/main/docs/pcp/P86_09.PNG)

[Packaged instructions](https://raw.githubusercontent.com/astrobleem/oemdisplay-tandy/main/downloads/experimental/CPPAN/INSTALL.TXT) |
[Technical details](https://github.com/astrobleem/oemdisplay-tandy/blob/main/docs/PCP.MD) |
[Report a problem](https://github.com/astrobleem/oemdisplay-tandy/issues).
Implementation lives in [oemdisplay-tandy](https://github.com/astrobleem/oemdisplay-tandy).
