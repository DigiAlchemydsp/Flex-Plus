# Flex+ 1.0

Flex+ routes the Digitone and Digitakt audio inputs—or their internal
tracks—into a track, with a low-CPU pitch shifter and an oscilloscope on the
machine page.

![Flex+ SYN1: T1 routed, TUNE +7](https://github.com/DigiAlchemydsp/Flex-Plus/raw/main/flexbus-syn1.png)

## Files

| device | file | needs |
|---|---|---|
| Digitone mk1 / Keys, OS 1.44 | `flexbus-1.0-digitone-flexbus.elemod` | core-dn1 4.0 + machines 0.2 |
| Digitakt mk1, OS 1.54 | `flexbus-dt-1.0-digitakt-flexbus.elemod` | core 4.0 + machine-pages 1.1 |

SHA-256:

```
59B4655FDD53750FEE338C579A8391CA0CEB10827A16572CAD976150B918BBD2  flexbus-1.0-digitone-flexbus.elemod
0A169EF4EE0751BB68CDDEDDEE51A19EEECCBDCEC767DF4424CD3AFD00FA9AA5  flexbus-dt-1.0-digitakt-flexbus.elemod
```

## What it does

- **Inputs:** external L, R, L+R; or the internal tracks (T1..T4 on the
  Digitone, T1..T8 on the Digitakt).
- **TUNE:** -24..+24 semitones, two-tap delay-sweep shifter.
- **GAIN** and **MIX** (shifter dry/wet).
- **Scope:** a low-CPU oscilloscope on the page (full-width on the Digitone,
  the A-D top row of the Digitakt SRC page, display only).
- The selected input replaces the track's sample/voice and then goes through
  the track's filter, AMP envelope, level and FX as usual. One bus per track;
  trigger it to open it; selecting itself is silence.

## Install

Build an OS with [elekloader](https://github.com/irpina/elekloader) from your
own stock OS: install the core and companion for the device, then the matching
Flex+ `.elemod`, and send the `.syx` with Elektron Transfer. Recovery is the
normal stock-OS path: hold **FUNC** while powering on, choose OS upgrade
(**TRIG 4** on the Digitone), send the stock `.syx`. The bootloader is never
touched.

## Status

Digitone 1.0 is hardware-tested by the user. Digitakt 1.0 is built, linted and
bench-tested; not yet hardware-tested.

GPL-2.0-or-later. Unofficial; not affiliated with or endorsed by Elektron.
