# DosBox

Until Community QBasic is released, or as a tool to verify side-by-side feature comparisons, you can execute Microsoft QBasic 1.1 on modern devices using the DosBox tool.

## Download

Download [DosBox](https://www.dosbox.com/).

A couple of options for where to find QBasic...

- [WinWorld - MS-DOS 5.0](https://winworldpc.com/product/ms-dos/50)
- [WinWorld - Windows 95 RTM](https://winworldpc.com/product/windows-95/rtm)

To my knowledge the "last version" is the one available on the Windows 95 installation disc under the `OTHER\OLDMSDOS` folder.

## Setup/Install QBasic in DosBox

I typically install DosBox into `C:\DosBox`. In this folder, I create a `C-Drive` subfolder that will represent the `C:` drive within the DosBox environment. In this folder, like the original MS-DOS installation, I create a `DOS` folder where I will then place the `QBASIC.EXE` and `QBASIC.HLP` files.

I then modify the default DosBox `.conf` (found by launching the *DosBox Options* shortcut) by adding the following to the end.

```bat
@ECHO OFF
CLS
ECHO SET BLASTER=A220 I7 D1 H5 T6
ECHO MOUNT C C:\DOSBOX\C-DRIVE
MOUNT C C:\DosBox\C-Drive
C:
C:\AUTOEXEC.BAT
```

Create/modify an AUTOEXEC.BAT file (located in `C:\DosBox\C-Drive`):

```bat
@ECHO OFF
SET PATH=Z:\;C:\DOS;
CLS
ECHO Microsoft MS-DOS [Version 5.00 (DosBox 0.74)]
ECHO (c) 2019 DosBox. All rights reserved.
```

At this point you can start DosBox and should now have a `C:\>` prompt instead of the default of `Z:`.

To start QBasic, type `qbasic` and press enter.

If you wold like to start QBasic automatically when launching DosBox you can modify the `AUTOEXEC.BAT` file to add `qbasic.exe` as the last line.
