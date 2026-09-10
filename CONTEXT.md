# CONTEXT.md

A seed glossary for `ps2-covers`. `/matt-domain-modeling` extends it as terms get
resolved — an entry that isn't here yet is fine, not a gap to fill upfront.

## Glossary

**Serial** — the disc identifier a PS2 game ships with, e.g. `SLES-53225`. Upper case,
one hyphen. It is the primary key of this repository: `GameIndex.yaml` keys on it, every
cover filename is one, and consumers request covers by it. Never call it "ID", "code",
or "game number".

**Prefix** — the leading letters of a serial (`SLES`, `SLUS`, `SLPM`, …). It encodes
region and publisher, and it is the row unit of the README stats table.

**Default cover** — the flat 2D cover scan. Lives in `covers/default/`, `.jpg`, 512×736.

**3D cover** — the rendered box image. Lives in `covers/3d/`, `.png`. Either scanned or
generated from a default cover by `tools/generic_3d_cover/main.py`.

**Generic 3D cover** — a 3D cover that was machine-generated rather than sourced. Listed
in `generic_3d_cover_list.txt`, which exists so a better one can replace it.

**GameIndex** — `tools/GameIndex.yaml`, the serial database vendored from PCSX2. It is
the authority on which serials exist and what each game is called. Not authored here.

**Coverage** — the share of indexed serials that have a default cover, per prefix.
`tools/update_stats.py` computes it; the README table and `missing_covers.txt` report it.

**Consumer** — a program that fetches a cover by raw URL: the PCSX2 Cover Downloader,
or PSCoverDL. Consumers are why a filename is a public API.

## Decisions

None recorded yet. `docs/adr/` does not exist; `/matt-domain-modeling` creates it with
the first ADR.
