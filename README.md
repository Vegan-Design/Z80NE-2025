# Z80NE-2025
Enhanced version of Nuova Elettronica Z80 microcomputer from 1979

The Z80 computer was published on the pages of the magazine Nuova Elettronica starting with issue 68 of October 1979.

It was a project carried out by Micro Design of Genoa presented progressively in many issues of the magazine, until August 1985.

The initial configuration, based on a proprietary bus, was very simple:
 - 1.92 MHz CPU
 - 1K RAM
 - 1K ROM
 - separated hexadecimal keypad with eight-digit 7-segments LED display

A Kansas City Standard cassette interface card was available with transfer rates of 300 baud, 600 baud, or 1200 baud.

An eprom programmer board could be added to this basic system.

Next it was also possible to expand the memory through both static and dynamic RAM expansion cards, in various sizes, up to a maximum of 56K,
removing orginal 1K RAM from CPU board.

A further step forward was made with the presentation of a low-resolution video card based on the MC6847 chip which, however,
was wired to operate only in text or semigraphic mode 6, excluding all graphics modes because only 512 bytes of VRAM was available.

With this board, equipped with a parallel type keyboard connector, it was possible to use a cassette-loaded 5.5K Basic via hex Monitor commands
and to use a printer via a specific parallel input/output board.

A very important expansion was the Floppy Disk interface that allowed the loading of a real operating system called "NE-DOS" (TRS-80 derivation)
or a version of CP/M 2.2 adapted to the 32-character by 16-lines screen provided by low-resolution video card.

The interface, however, was limited to handle a single face disk for only 40 columns, which with the FM encoding allowed a storage capacity of about 77K

Together this Floppy Disk interface, a new 1K Eprom was released containing a video hexadecimal monitor with commands for booting from disk.


The entire system thus composed could be housed in a specifically designed metal cabinet with integrated power supply, keyboard, 5"1/4 SSSD floppy drive
and 12" green phosphor monitor.

One of the last expansions released was a high resolution video card based on the SY6545 chip capable of displaying in monochrome
an 80 column screen for 24 lines of text and limited graphics capabilities with a resolution of 320x144 pixels.

With this video card a new 1K Eprom was released which by changing the formatting of the disks brought the capacity to about 90K.

You could now run a new "NE-DOS Grafic" operating system still derived from the TRS-80 or a CP/M 2.2 version renamed "SONE"

Finally, a Hard Disk card with SASI interface and BASF 6188/F 12 MB disk was released. With this card was released the last firmware in 2K eprom to handle Hard Disk CP/M boot.


These last configurations required the assembly in a rack case with floppy and separate monitor and keyboard

 
My compact replica is structured in only three boards so organized:

* Main board including:
- Z80B CPU clocked at 1.92 MHz or 4.8 MHz selectable by software
- 64K static RAM
- 64K of ROM divided into 4x 16K banks, can be switched off by software to free all RAM
- decoding RAM-VRAM-ROM-I/O
- Hexadecimal interface for separated keypad and LED display
- PS/2 keyboard interface
- 300, 600 or 1200 baud cassette interface
- Parallel printer interface and generic 8-bit I/O
- 2x RS-232 9 pin connectors (can be activated with expansion board)
- BUS connector for expansion board
- Video interface with MC6847:
  - 8K dedicated Video RAM (visible 1K at a time: max 6K used by the 6847, 8K available to the CPU in 1K pages)
  - NTSC color encoder
  - external CG ROM with 2x characters set selectables by software
    - text 32x16 int CG ROM 2x palettes of 2 colors
    - text 32x16 ext CG ROM 2x palettes of 2 colors
  - all graphic and semigraphic modes selectable via softare:
    - SG4 64x32 9 colors
    - SG6 64x48 2x palettes of 5 colors
    - CG1 64x64 2x palettes of 4 colors
    - CG2 128x64 2x palettes of 4 colors
    - CG3 128x96 2x palettes of 4 colors
    - CG6 128x192 2x palettes of 4 colors
    - RG1 128x64 2x palettes of 2 colors
    - RG2 128x96 2x palettes of 2 colors
    - RG3 128x192 2x palettes of 2 colors
    - RG6 256x192 2x palettes of 2 colors

This main board can work by itself to run the following firmwares from Nuova Elettronica:
- LX382 hex monitor on keypad and LED display
- LX390 video hex monitor with disk functions
- LX548 Basic 16K resident on Eprom
- Basic 5.5K loaded from cassette

and the following from third parties:
- LX382 redirected to video
- LX390 modified for NE-DOS format
- Basic 8K Microsoft
- RAM test

--

* Expansion board, to be mounted above the main board:
- RS232 interface with Z80SIO:
  - a fixed port at 115200 baud
  - a variable speed port from 300 to 115200 baud
- Floppy Disk interface with support of the second disk face, for a total of 4 floppy drive units
- Eprom Programmer interface LX394-LX395
- Hard Disk interface with SASI bus
- 4 programmable timers with Z80CTC
- programmable sound generator (uses two CTC timers)
- Z80 Interrupt Mode 2 management
- connector for original Nuova Elettronica BUS riser
- hardware debug circuit with 8K dedicated CPU-accessible RAM for breakpoint generation (NMI) on:
  - address access for M1 cycle (after 1-255 times)
  - address access for read and/or write (after 1-255 times)
  - address access for specific opcode
  - address access for reading and/or writing specific data
  - I/O access (after 1-255 times) 
  - I/O access for reading and/or writing specific data

By adding this card you can run the following firmware and OS from Nuova Elettronica:
- LX1390 bootloader for NE-DOS boot
- Basic 5.5K loaded from disk
- CP/M 2.2 on low resolution 32x16 chars screen

or a new feature:
- RS232 control through PC Dashboard that allow complete machine control such as debug, read/write memory or peripherals, read/write floppy disk images

--

* High resolution video card LX529 with R6545, to be mounted on Nuova Elettronica BUS riser:
- text 80x24 (+ added 16 colors for single char and 16 colors for char background)
- text 40x24 (+ added 16 colors for single char and 16 colors for char background)
- 320x144 pixel graphics (+ added 2 of 16 colors per block of 4x6 pixels)
- new 80x48 interlaced text with 16 colors for single char and 16 colors for char background
- new 40x48 interlaced text with 16 colors for single char and 16 colors for char background
- new 320x200 graphics with 16 colors for pixel
- new 640x200 graphics with 2 of 16 colors per block of 8x2 pixels

The board provide a 16-grays composite video output and a CGA compatible RGBI video out also suitable for SCART connector (with external circuitry).

There is a software selctable video switching to select MC6847 gray video or R6545 gray video to be outputted to RCA connector


With this card you can use the OS "NE-DOS grafic" and my 62K CP/M 2.2 version that support double face floppy disks for a total storage of around 188K

A boot from a SASI emulator (external project) is also available
