# Rentkammer Case Files: Navigation and Content Review

See what to do next: https://claude.ai/share/daeb7bdb-3352-4bee-84de-89682234c02f

22 Nov 2026 · Kurt Krueckeberg

The project now lives in [jb2-nla](https://github.com/kurt-krueckeberg/jb2-nla)
(Jupyter Book 2), and its navigation is the `toc:` section of `myst.yml`. The toc keeps
the structure of the old `_toc.yml`, but every case file and every document now has a
short, dated title. The seven Rentkammer case-file folders are consistent at the top
level and in their titles, and folder 139 is still the best model for a landing page.
The end goal is a printed book made from the Typst PDF, written for readers of the
Krückeberg family history, so every recommendation here must work on paper as well as
on the website, and the wording of the Bückeburg archivists and the Rentkammer clerks
is quoted, never rewritten. Nothing in the repository was changed for this review.

## Navigation consistency

In `myst.yml` all seven folders start with `index.md` → `cover.md` → `content.md`;
188 has no `content.md` because it has no Designatio Actorum. 139 and 146 add a second
group for their sale documents (`sale-related-docs.md`). Below that level:

- **Titles:** every case-file landing page and every document page has a short H1 with
  a date. The case-file entries in `myst.yml` have no `title:` lines, so the sidebar
  shows each page's H1, the same heading that prints in the PDF. Every contents page
  has the H1 "Contents List".
- **Order:** 146 still puts two analysis pages ahead of Document 1, and 689 still puts
  `amt-decree.md` ahead of Document 1.

  This analysis should really be removed and made part the genealogical analysis process.
- **Pages not in the toc:** 18 pages are not listed in `myst.yml`: 13 in 689 (the twelve
  research files listed below and `service-slip-july-10-1841.md`), 4 in 188 (`doc5.md`,
  `3-right.md`, `last-page.md`, `todo.md`) and 1 in 1237 (`doc4-extra.md`).

## Best folder: 139

The `index.md` of 139 is still the landing page that best tells a layman, in order,
what the file is about, who is involved, the outcome and the timeline. Under its H1 it
gives the archive's title, the German title and the call number, then two plain
paragraphs (the widow's 1824 petition and the 1849 sale before emigration), a facts
table and a dated timeline. Its document pages carry dates in their headings, and 10 of
its 12 document pages open with a summary. 147 has a landing page of the same kind,
which adds two sections worth copying everywhere: **Genealogical Significance** and a
section pointing to the map.

| Folder | Landing page now | Main gap |
| --- | --- | --- |
| 139 | Overview, facts table, timeline | Timeline stops at August 1824; the 1849 sale is missing; no Genealogical Significance section |
| 147 | Overview, facts table, summary of Document 5, Genealogical Significance, map | None |
| 1237 | Short overview, regency background marked TODO, timeline from Document 1 | No facts table; timeline rows have no links to the documents |
| 689 | Emigration and regency background, then a timeline | Never says plainly what the case is; timeline stops at 14 Oct. 1841; 13 pages not in the toc |
| 146 | Argument that there were two Jobst Heinrichs | Identity analysis, not a case overview; no timeline |
| 1291 | Archive's title and call number, then "TODO: write the overview" | No overview; only 1 of 22 document pages has a summary |
| 188 | Pointer to 146 | No facts table; `doc5.md` unfinished (its heading is "????") |

## Recommendations

Each folder should reach the 139 pattern: a landing page with a plain overview, a
facts table, a timeline and a closing Genealogical Significance section, followed by
cover, contents list, documents, later documents and supplementary notes. Everything
below uses features built into MyST; none needs a plugin or custom CSS.

### Titles and headings

This is done. Every page has a short heading written for family readers, and the
archivists' or clerks' wording follows beneath it, labelled in plain English
(*Archive's title:* on landing pages, *Listed in the case file's contents as:* on
document pages). The heading is what prints as the chapter or section title in the PDF.
The case-file entries in `myst.yml` no longer have `title:` lines, so the sidebar and
the printed book use the same headings.

The Latin term "Designatio Actorum" is explained once, on the Case Files Explained page, and
plain-English labels are used everywhere else.

### Document pages

Keep Translation and Transliteration as two sections one after the other, as they are now. Do
not use tabs or dropdowns: a printed page cannot show hidden text, and the book needs both
texts visible. Replace the per-page glossaries with one glossary in `rentkammer/terms.md`,
using MyST's `{glossary}` directive and `{term}` role. `terms.md` is currently a
`list-table`, not a `{glossary}`.

### Each folder

Every explanation of the Rentkammer and of the Vormundschaftliche Kammer (the "Guardianship"
or "Regency Chamber") belongs in one place, the "Rentkammer Explained" section
under "Rentkammer Case Files". Three pages currently carry such an explanation:
`1237/index.md`, `1237/doc4-extra.md` and `689/index.md`. Move each explanation there, and
leave a one-line link to it in the page it came from.

1. **139:** extend the timeline through September 1849, correct the date of the
   Rentkammer reply in the timeline (see "Errors"), and add a Genealogical Significance
   section.
2. **147:** done.
3. **1237:** move the regency section of `index.md` ("Background: The Regency Period")
   to "Rentkammer Explained", as the page's own TODO says. Also move the explanation in
   `doc4-extra.md` of why Document 4 is addressed to the Vormundschaftliche Kammer to
   "Rentkammer Explained", then delete `doc4-extra.md` and put a one-line link in
   `doc4.md`. In the timeline, link each row to its document, give row 4½ the date of
   Funck's drawing (30 Mar. 1799) instead of "(undated)", and delete row 7, which is a
   placeholder ("if present—often cover note or filing slip"); the reminder note of
   27 Oct. 1800 needs a row instead. Add a facts table.
4. **689:** move the explanation of the "Guardianship Chamber" or "Regency Chamber" in
   `index.md` to "Rentkammer Explained", and replace the opening with two paragraphs on
   the debt to Hempel & Söhne and the 200 Reichsthaler loan. Keep the timeline and extend
   it through 1845. Move `amt-decree.md` and the service slip into a "Background
   documents" group in `myst.yml`. The numbering and analysis pages are research
   material; see "Analysis to remove from the book" below.
5. **146:** replace the two-Jobst-Heinrichs argument with its conclusion in a
   Genealogical Significance section, and remove the two Document 1 analyses (see
   below). Write a 139-style overview covering 1808–1810 and the 1850 sale.
6. **1291:** write the overview from scratch. It has three petitioners (Krückeberg,
   Vogt, Brüggemann), so the timeline needs a "Party" column.
7. **188:** keep it short, add the facts table, and either finish or drop `doc5.md`,
   `3-right.md` and `last-page.md`.

## Analysis to remove from the book

The book presents the documents and what they show. Research analysis belongs with the
genealogical research, not in the case files. Besides the two 146 analysis pages,
`doc1-analysis.md` and `doc1-2nd-analysis.md`, the following are analysis rather than
presentation.

**Inside the book, to remove:**

1. **The argument on the 146 landing page, `146/index.md`.** The whole page argues that
   the Jobst Heinrich of 1808 is not the Jobst Heinrich of No. 10, and it ends in a note
   headed "Bottom line" in chatbot style ("Yes, Petzen was the parish for Evesen. No,
   that does not guarantee…"). The conclusion is the most important genealogical
   finding of the case file, so keep it in two or three sentences in a Genealogical
   Significance section: the 1808 petitioner was a tailor and Einlieger from Evesen
   without a holding, so he cannot be the shoemaker who already held No. 10 in 1798.
   Remove the argument itself. The page also has two typos: "(17665-18222)" and
   "Berebusch".
2. **"What this Document Tells Us about Jobst Heinrich's Status" in `146/doc6.md`**
   (lines 97–153). It is the same kind of analysis, ending in a "Bottom line" list of ✔
   points. One sentence in the page's Summary is enough.

**Inside the book, to keep:** the "Essential Explanations" in `146/doc6.md` (Michaelmas,
Meyerbrief, the annual dues). They explain terms in the document for the reader, which is
presentation rather than analysis, and could later move into the glossary.

**Outside the book (not listed in `myst.yml`):** twelve pages in 689 are research working
files: `analyze.md`, `docs-1-and-2-analysis.md`, `other-numbering-notes.md`,
`rescript-explained.md`, `workflow.md`, `document-markings.md`, `literal-doc-index.md`,
`event-log.md`, `adoc1.md`, `adoc2.md`, `roster.md` and `glossary.md`. They don't appear in
the book, but they belong with the research notes, not in the case-file folder. Two are
worth mining first: `glossary.md` for the book's glossary, and `roster.md` for a
"principal persons" row on the 689 landing page.

The same goes for the repository's own working files, `claude-case-file-analysis.md`,
`todo.md`, `jb2-conversions-todo.md` and `188/todo.md`, though none of them is in the book
either.

## Errors found along the way

These errors are present in jb2-nla as of 22 Nov 2026. Every link in the seven
contents lists now resolves to an existing page.

| File | Problem |
| --- | --- |
| `139/sale-related-docs.md` | The heading says 1849, but the text says the sale was in 1850 and the table caption says no. 18; the pages it lists are dated 1849 and concern no. 10 |
| `139/content.md` | Says the documents are from 1822; they are from 1824 |
| `139/index.md` | The timeline dates the Rentkammer reply 2 August 1824; the document is dated 4 Aug. 1824 |
| `139/index.md` | The overview has "Wilhelm Boremann" (the facts table and documents have "Bornemann") and "immigrating to American" |
| `1237/content.md` | Item 3 is dated 1800, but the document is dated 11 March 1799 (the clerk's entry may simply differ) |
| `147/doc5.md` | The transliteration reads "Knückeberg No 18"; the translation and the drawing have "Krückeberg" |

This review is the copy of `claude-case-file-analysis.md` in jb2-nla, which `myst.yml`
excludes from the build. Keep only this one copy.

## Next step

Restructure 1237 first: its content already exists and only needs rearranging. 1291 and 188
take the most work because their overviews have to be written, not moved.
