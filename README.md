# QUALEA-500

A 4-track loop MIDI sequencer with five sequencer types for the Roland MC-500 MkII.

**Web / manual:** https://bretikov.github.io/QUALEA-500/

**Download:** [QUALEA-500.dsk](https://github.com/bretikov/QUALEA-500/releases/latest/download/QUALEA-500.dsk) · [all releases](https://github.com/bretikov/QUALEA-500/releases)

## Sequencer types
- **EUC** – Euclidean rhythms with a random melody
- **TUR** – Turing machine, shift register with mutation
- **USR** – your own recording from MIDI IN, overdub
- **GOL** – Game of Life, 4 voices on a 4×16 grid
- **CRD** – chords, rhythm templates, arpeggio, strum

## Requirements
- Roland MC-500 MkII (also tested on the MC-500B = MkI with the OM-500 board)
- 3.5" 2DD (720 KB) floppy disk – 2HD does not work
- a floppy drive to write the image

## Writing the floppy
On Windows use the **DiskWrite** app (tested by the author). On macOS and Linux, use `dd` in the terminal and always write **whole tracks** (`bs=9216`):

**macOS**

1. Insert the floppy, then run `diskutil list`. Find the disk that is external, physical and about 737.3 KB – that is your floppy (e.g. `/dev/disk4`). The number changes from time to time, so check it every time.
2. ⚠️ Double-check the number. Writing to the wrong disk erases your SD card or hard drive.
3. Write the image (replace `disk4` with your number):

```
diskutil unmountDisk /dev/disk4
sudo dd if=QUALEA-500.dsk of=/dev/disk4 bs=9216
diskutil eject /dev/disk4
```

**Linux**

```
sudo dd if=QUALEA-500.dsk of=/dev/sdX bs=9216
```

Do **not** write sector by sector (`bs=512`, often with `conv=noerror,sync`): with USB floppy drives this produces disks the MC-500 reads with CRC errors – even Roland's own system disk then fails to boot. `conv=noerror,sync` also hides write errors.

## Terms of use
QUALEA-500 is free for personal use. Redistributing the disk image (modified or not) and selling it are not allowed – please link to this page instead. All rights reserved.

## Disclaimer
QUALEA-500 is an independent project, not made by or affiliated with Roland Corporation. Roland and MC-500 are trademarks of Roland Corporation. The software neither uses nor distributes any Roland code. Use at your own risk.

## Support
If you like QUALEA-500, you can [buy me a coffee](https://buymeacoffee.com/bretikov). ☕
