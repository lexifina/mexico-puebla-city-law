# Puebla (city): municipal law in git

Part of [lexifina/global-law](https://github.com/lexifina/global-law), one git history for every country's law: this is the law of Puebla, Puebla, Mexico, which global-law reads at `mexico/puebla/puebla/acts/`.

The municipal law of Municipio de Puebla (Puebla, Mexico) as a git history: its reglamentos, one file per article, one paragraph per line, so `git log`, `git blame` and `git diff` work article by article.

It follows the shared design of [lexifina/global-law](https://github.com/lexifina/global-law), which places it at `mx-pue-puebla/`. The law of the State of Puebla is in [lexifina/mexico-puebla-law](https://github.com/lexifina/mexico-puebla-law), and Mexico's federal law in [lexifina/mexico-law](https://github.com/lexifina/mexico-law).

The text is in Spanish, exactly as the source prints it.

## What this repository holds

2 reglamentos so far, each as its **current consolidated text only** (the oldest version available from the source), added in parts. Puebla has no separate Bando de Policía y Buen Gobierno: its municipal regulations, including the rules on public order and civic justice, are codified in the Código Reglamentario para el Municipio de Puebla (COREMUN), which comes first. The municipality's page links only a few municipal instruments (state laws it also links, such as the Ley Orgánica Municipal, are left out).

| Folder | Reglamento | History |
| --- | --- | --- |
| `codigo-reglamentario/` | Código Reglamentario para el Municipio de Puebla (COREMUN) | current text only, last reform 4 September 2024 |
| `codigo-de-etica-del-h-ayuntamiento/` | Código de Ética del H. Ayuntamiento del Municipio de Puebla | current text only, last reform 7 December 2021 |

## Source

Gobierno Abierto, H. Ayuntamiento de Puebla (gobiernoabierto.pueblacapital.gob.mx), "Normatividad más consultada del H. Ayuntamiento de Puebla", <https://gobiernoabierto.pueblacapital.gob.mx/marco-normativo-del-h-ayuntamiento-de-puebla>. The page links the current text of the Código Reglamentario para el Municipio de Puebla (COREMUN) and other municipal instruments as PDFs with a text layer; each PDF states on its first page the date of its last reform (or publication) in the Periódico Oficial del Estado de Puebla. Each PDF says its content is informative and that the original is the one published in the Periódico Oficial.

## Dates

- Each reglamento is one commit, dated at **noon, America/Mexico_City, on the date of its last reform** as the source records it. Its original text and earlier versions are not shown, because the source does not publish them.
- Versions dated after the retrieval day would go on the `futuro` branch, never merged into `main`.

## Files

`<reglamento>/art-005.md` is Artículo 5, `art-005-bis.md` Artículo 5 bis; `encabezado.md` holds the title and anything printed before Artículo 1. Chapter headings, transitorios and the reform notes the source prints stay in the file of the article they follow. One paragraph per line.

## How it is checked

- Every version is read back from git on its day (`tools/check_repo.py`) and must match `corpus.json`.
- The letters and digits of every version equal those of the source PDF read again with an independent reader (poppler's pdftotext), so no word is lost or added.
- Health checks: no merge commits, commit dates never go backwards, nothing dated in the future, and every commit's trailers parse.

## Limits

This is not an official publication. The binding text is the one published in the Periódico Oficial del Estado de Puebla. Only the reglamentos listed above are included, each as its current text only.
