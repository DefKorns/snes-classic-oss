# SNES Classic Edition — Open Source Software

Unofficial mirror of the open source code Nintendo publishes for the
**Super NES Classic Edition (Super Famicom Mini)**, extracted so it can be browsed, searched and fetched
per package.

- Source page: https://support.nintendo.com/jp/oss/index.html
- Original archive: https://support.nintendo.com/jp/oss/data/SuperNESClassicEdition_OSS.zip
- Archive `Last-Modified`: 2025-06-04 — downloaded 2026-10-15
- Archive sha256: `a963f8526dea75be2f9004b8d2c9d2b2888591f2df7f9e64d1b2af65775e783d`

Nothing here is modified. Each software package keeps its own license; see
the license files inside each `source/` tree.

## Layout

```
<package>/
  source/      the package archive, extracted
  *.patch      Nintendo's patches, as shipped (not applied)
  series       patch order, as shipped
```

- When an archive had a single top-level directory, that directory was
  dropped, so `source/` holds its contents directly.
- `MANIFEST.sha256` lists the sha256 of the original zip and of every file
  inside it (archives, patches) before extraction, to check this mirror
  against Nintendo's download.
- Git does not track empty directories, so those from the archives are gone.

## Cloning

Clone on Linux or macOS. Some trees (the Linux kernel in particular) have
files whose names differ only in case, and a Windows checkout silently
overwrites one with the other.

To fetch a single package without the rest:

```sh
git clone --filter=blob:none --sparse https://github.com/DefKorns/snes-classic-oss.git
cd snes-classic-oss
git sparse-checkout set <package>
```
