# Delpher / KB API — Postman Collection (Netherlands)

This is a Postman (v2.1) collection of 14 requests for the **KB, the National Library of the Netherlands**. These are the APIs behind [Delpher](https://www.delpher.nl): more than 100 million historic newspaper articles (1618 to about 1995), including **family notices** (*familieberichten*), plus books, magazines and ANP radio news bulletins.

**Import link** (Postman → Import → Link):
```
https://raw.githubusercontent.com/mikeyeves/Delpher-API-Postman/main/Delpher_KB_API.postman_collection.json
```
No key and no environment file are needed.

## Folders
| Folder | Requests | Notes |
|---|---|---|
| ★ Newspapers (DDD_artikel) | 8 | Search; **family notices**; date range; exact phrase; advertisements; a single newspaper; distribution area; sorting |
| Books, magazines, ANP | 3 | Other Delpher collections |
| Resolver | 3 | Article OCR text (XML), page scan (JPEG 2000), Delpher viewer link |

The search requests show results as a **Visualizer** table, with links to Delpher, the OCR text and the page image.

## Tested at build time
- `Bukovsky` returned **111** newspaper articles. Of those, 35 fall in 1900–1940, 17 are advertisements and 12 are in *Algemeen Dagblad*.
- `"Groot Becskerek"` returned 24 articles.
- `Krupl` as a family notice returned 1.
- Books and magazines returned 27, ANP 15, and BOEKEN 72 for `Banat`.
- The resolver returned 200 for the OCR XML and the page image (image/jp2).

## CQL cheat-sheet
| Goal | query |
|---|---|
| Words (AND by default) | `Krupl Bukovsky` |
| Phrase | `"Groot Becskerek"` |
| OR / NOT | `Krupl OR Krüpl`, `Krupl NOT Krupp` |
| Type | `type=familiebericht` · `artikel` · `advertentie` · `"illustratie met onderschrift"` |
| Date | `date within "01-01-1900 31-12-1940"` or `date=1912` |
| Newspaper | `papertitle="De Telegraaf"` |
| Sort | `… sortBy date/sort.ascending` |

## Tips
- OCR quality varies, so try spelling variants and wildcards (`Bukovs*`).
- Dutch newspapers often wrote Hungarian and Serbian place names in German or Hungarian form (*Groot-Becskerek*, *Temesvar*, *Werschetz*).
- The KB states that the data is for research and non-commercial use. Keep request rates modest.

## Related collections
[Open Archives (Dutch civil records)](https://github.com/mikeyeves/Open-Archives-API-Postman) · [Gallica (France)](https://github.com/mikeyeves/Gallica-API-Postman) · [European Archives](https://github.com/mikeyeves/European-Archives-APIs-Postman)

*Unofficial. Not affiliated with the KB or Delpher.*
