# Star Rail warp-link extractor for Linux

This is a native Bash port of Star Rail Station's Windows PowerShell extractor
for Honkai: Star Rail running under Proton or Wine. It finds `Player.log`, maps
the recorded Windows game path through the prefix's `dosdevices`, searches the
Chromium web cache, validates candidate API links, and copies the valid link to
the Linux clipboard.

It does not invoke PowerShell, Wine, or downloaded code.

## Requirements

- Bash 4+
- Standard GNU utilities, including `find`, `grep`, `sort`, and `strings`
- `curl`
- Optional clipboard support: `wl-copy`, `xclip`, or `xsel`

## Use

Open Star Rail's Warp History screen and wait for it to load, then run:

```bash
./warp-tracker --star-rail
```

For a nonstandard prefix or cache location:

```bash
./warp-tracker --star-rail --prefix /path/to/proton/pfx
./warp-tracker --star-rail --cache-file /path/to/Cache/Cache_Data/data_2
```

`--no-validate` skips the API check and is intended for diagnostics. The output
contains a temporary HoYoverse `authkey`; treat the URL as a secret.

