# QUALEA-500

A 4-track loop MIDI sequencer with five sequencer types for the Roland MC-500 MkII.
4stopý loop MIDI sekvencer s pěti typy sekvencerů pro Roland MC-500 MkII.

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
On macOS the **DiskWrite** app works. In the terminal, always write **whole tracks** (`bs=9216`):

```
# macOS – find your floppy first (e.g. disk2), double-check the number!
diskutil list
diskutil unmountDisk /dev/disk2
sudo dd if=QUALEA-500.dsk of=/dev/disk2 bs=9216
diskutil eject /dev/disk2

# Linux
sudo dd if=QUALEA-500.dsk of=/dev/sdX bs=9216
```

Do **not** write sector by sector (`bs=512`, often with `conv=noerror,sync`): with USB floppy drives this produces disks the MC-500 reads with CRC errors – even Roland's own system disk then fails to boot. `conv=noerror,sync` also hides write errors.

## Terms of use
QUALEA-500 is free for personal use. You may share the unmodified disk image. Selling it or distributing modified versions is not allowed. All rights reserved.

QUALEA-500 je zdarma pro osobní použití. Obraz diskety smíš šířit v nezměněné podobě. Prodej a šíření upravených verzí není dovoleno. Všechna práva vyhrazena.

## Disclaimer
QUALEA-500 is an independent project, not made by or affiliated with Roland Corporation. Roland and MC-500 are trademarks of Roland Corporation. The software neither uses nor distributes any Roland code. Use at your own risk.

## Support
If you like QUALEA-500, you can [buy me a coffee](https://buymeacoffee.com/bretikov). ☕
