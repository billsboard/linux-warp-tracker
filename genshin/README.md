# Genshin wish-link extractor for Linux

This is a native Bash port of Paimon.moe's Windows PowerShell extractor for
Genshin Impact running under Proton or Wine. It reads the game's Chromium web
cache, finds the newest wish-history URL, validates its temporary auth key
against HoYoverse, and copies the link to the Linux clipboard.

It does not invoke PowerShell, Wine, or any downloaded code.

## Requirements

- Bash 4+
- GNU `find`, `grep`, `sort`, and `strings` (normally already installed)
- `curl`
- Optional clipboard support: `wl-copy`, `xclip`, or `xsel`

## Use

First open Genshin's Wish History screen and wait for it to load. Then run:

```bash
./warp-tracker --genshin
```

The script searches the usual Steam/Proton, Wine, and Lutris prefix locations.
If the game uses a prefix elsewhere, specify it:

```bash
./warp-tracker --genshin --prefix /path/to/prefix
```

For a nonstandard layout, point directly at the Chromium cache file:

```bash
./warp-tracker --genshin \
  --cache-file /path/to/webCaches/VERSION/Cache/Cache_Data/data_2
```

China-server installations can use `--region china`. `--no-validate` skips the
HoYoverse API check and returns the newest cached URL; it is mainly useful for
diagnostics.

The resulting URL contains a temporary HoYoverse `authkey`. Treat it as a
secret and paste it only into a service you trust.
