# How this repository was made (Puebla (city))

This file is written by the build on 2026-10-31, the day the source data was retrieved.

## Sources

| Source | Address | Retrieved | Licence |
| --- | --- | --- | --- |
| Gobierno Abierto, H. Ayuntamiento de Puebla (gobiernoabierto.pueblacapital.gob.mx), "Normatividad más consultada del H. Ayuntamiento de Puebla" | <https://gobiernoabierto.pueblacapital.gob.mx/marco-normativo-del-h-ayuntamiento-de-puebla> | 2026-10-31 | Official municipal regulations, not protected by copyright in Mexico: Ley Federal del Derecho de Autor, art. 14: "No son objeto de la protección como derecho de autor a que se refiere esta Ley: [...] VIII. Los textos legislativos, reglamentarios, administrativos o judiciales, así como sus traducciones oficiales. En caso de ser publicados, deberán apegarse al texto oficial y no conferirán derecho exclusivo de edición". Reproduced following the official text, with attribution. |

Every word of law in this repository comes from these sources. Lexifina reads them and records each act's dated versions, and the laws that made each change, in one corpus file. This repository is built from that file.

## What is in it

| Act | Title | Versions | Span |
| --- | --- | ---: | --- |
| `codigo-reglamentario` | Código Reglamentario para el Municipio de Puebla (COREMUN) | 1 | 2024-09-04 to 2024-09-04 |
| `codigo-de-etica-del-h-ayuntamiento` | Código de Ética del H. Ayuntamiento del Municipio de Puebla | 1 | 2021-12-07 to 2021-12-07 |

The build made 2 commits:

| Commits | Kind |
| ---: | --- |
| 2 | first version of an act |
| 0 | one law on its in-force day |
| 0 | changes no amendment note explains, credited to the publisher |

Other counts:
- 0 commits on the branch `futuro`: laws not yet in force on 2026-10-31.
- 0 commits dated 1 January 1970: in force before 1970, with the real day in their `In-force` trailer.
- 2 laws in the record.
- 2 tags.

## Dates

Each commit is dated at noon (America/Mexico_City) on the day the change took effect. The other dates, enacted and published, are trailers.

When a law gives no date of its own, the default rule applies: (not stated) 

## How the history is built

`tools/build.py` turns the corpus into this history in one pass: one commit per law, on the day it took effect. The same corpus always gives the same commit hashes. `tools/check_repo.py` reads every version back from git and compares it with the corpus. `tools/on.py` shows the law as it stood on any date. The corpus format is described in `tools/SCHEMA.md`.

- Corpus: sha256 `b5a92f808a457478a4ea742395d66217f86c8dc25b9db6ac9ed6f8d5218a657e` (2820491 bytes).
- Builder blob hashes (`git hash-object`): `build.py` `a4faa25af85facb64b956b372f6b528aafdd7ec1`, `check.py` `3d00541d258745461ab52b1b0cb4e1716a27a95d`, `on.py` `644a6c0857fbcc72562032b58d57aa113fee0641`.
- Python 3.12.10; git version 2.46.0.windows.1.

## Checks

2 versions of 2 acts read back from git on the day each took effect and on the day before: 0 mismatches. Trailers: 0 commits whose trailers git cannot parse. Health: 0 merge commits on main, 0 commit dates that go backwards, 0 commits dated after the build.

No second build of this corpus has been compared yet.

## Decisions made by hand

- The source (https://gobiernoabierto.pueblacapital.gob.mx/marco-normativo-del-h-ayuntamiento-de-puebla) publishes, for each reglamento municipal vigente, only its current consolidated text and the date of its last reform. Each reglamento is therefore its current text only ("oldest version available"), dated by that last-reform date; the original text and earlier versions are not shown. That date is the one the source gives for the last reform (its publication in the Periódico Oficial del Estado de Puebla), not a separately established day of entry into force.
- Puebla has no separate Bando de Policía y Buen Gobierno: its municipal regulations, including the rules on public order and civic justice, are codified in the Código Reglamentario para el Municipio de Puebla (COREMUN), which comes first. The municipality's page links only a few municipal instruments (state laws it also links, such as the Ley Orgánica Municipal, are left out).
- Units: the heading (encabezado: the title and anything before Artículo 1) and one file per article, holding the article and everything printed after it up to the next article (chapter headings, transitorios and the reform history the PDF prints). Nothing is dropped. One paragraph per line, spacing normalised. Text-layer PDFs only, no OCR; a reglamento whose PDF has no text layer is left out.
- Reglamentos are added in parts of about 50, in the order the source lists them, after the first part.

## What AI did and did not do

The scripts that read the sources and build this repository were written by Claude Code running Claude Opus 5.5 (`claude-opus-5-5`) under Lexifina's direction.

No model wrote, translated or corrected legal text. No model runs at build time. Every word of law in this repository comes from the official sources above.

The commit messages are written by `build.py` from the source data.

Model use at data-build time:
- A model (Claude) wrote the fetch and parse code and chose which reglamentos to include; it wrote no law text. Every word of law comes from the municipality's own published texts.
