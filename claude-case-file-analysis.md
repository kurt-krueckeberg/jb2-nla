# Rentkammer Case Files: Navigation and Content Review

20 Nov 2026 · Kurt Krueckeberg

The project now lives in [jb2-nla](https://github.com/kurt-krueckeberg/jb2-nla)
(Jupyter Book 2), and its navigation is the `toc:` section of `myst.yml`. That toc is
a near-literal port of the old `_toc.yml`, so the seven Rentkammer case-file folders
are still consistent only at the top level, and folder 139 is still the best model.
The end goal is a printed book made from the Typst PDF, written for readers of the
Krückeberg family history, so every recommendation here must work on paper as well as
on the website, and the wording of the Bückeburg archivists and the Rentkammer clerks
is quoted, never rewritten. Nothing in the repository was changed for this review.

## Navigation consistency

In `myst.yml` all seven folders start with `index.md` → `cover.md` → `content.md`;
188 has no `content.md` because it has no Designatio Actorum. Below that level they
diverge:

- **Case-file titles in `myst.yml`:** each uses a different form. 1237 and 188 carry no dates,
  146 puts the dates after a comma, 147 runs to 121 characters, and 139 has no `title:` at all.
  The 1291 title names "Einliegers Vogt & Nordholz" where the cover has Vogt and Brüggemann;
  Nordholz is their village. These titles appear only in the website sidebar; the PDF takes its
  chapter headings from the page headings.
- **Document titles in `myst.yml`:** none carry dates. Many entries have no `title:`
  (1237/doc6, 1291/doc13, 18 and 21, eight in 689, all of 188), so the sidebar falls back to
  the page's long heading.
- **Nesting:** fixed in the port. In 147, `doc5.md` now sits under `content.md`, as in every
  other folder.
- **Order:** 146 still puts two analysis pages ahead of Document 1, and 689 still puts
  `amt-decree.md` ahead of Document 1.
- **Later documents:** 139 and 146 group them under `other-docs.md`; no other folder has such a
  group.
- **Pages not in the toc:** 18 pages are not listed in `myst.yml`: 13 in 689, 4 in 188 and 1 in
  1237 (`doc4-extra.md`; `actors.md` has been deleted).

## Best folder: 139

The `index.md` of 139 is still the landing page that best tells a layman, in order,
what the file is about, who is involved, the outcome and the timeline. It opens with
two plain paragraphs (the widow's 1824 petition and the 1849 sale before emigration),
then a facts table, then a dated timeline. Its document pages also carry dates in
their headings and nearly all open with a summary. Since the first review, 147 has
gained a landing page of the same kind, which adds two sections worth copying
everywhere: **Genealogical Significance** and a section pointing to the map.

| Folder | Landing page now | Main gap |
| --- | --- | --- |
| 139 | Overview, facts table, timeline | Timeline stops at 1824; the 1849 sale is missing; no Genealogical Significance section |
| 147 | Overview, facts table, summary, Genealogical Significance, map | Toc title (121 characters) does not match the H1 |
| 1237 | H1 "Overview", regency background marked TODO, then a 10-step narrative | Timeline table starts at Document 3; no facts table |
| 689 | Regency background, then a timeline | Never says plainly what the case is; 13 pages not in the toc |
| 146 | Argument that there were two Jobst Heinrichs | Identity analysis, not a case overview; no timeline |
| 1291 | "TODO" | No overview; almost no page summaries |
| 188 | Pointer to 146 | Documents untitled; `doc5.md` unfinished |

## Recommendations

Each folder should reach the 139 pattern: a landing page with a plain overview, a
facts table, a timeline and a closing Genealogical Significance section, followed by
cover, contents list, documents, later documents and supplementary notes. Everything
below uses features built into MyST; none needs a plugin or custom CSS.

### Titles and headings

Every page gets a short heading written for family readers. The archivists' or
clerks' wording follows directly beneath it, in your translation, unchanged, and
labelled in plain English. The heading is what prints as the chapter or section title
in the PDF; the `title:` lines in `myst.yml` label only the website sidebar and
should repeat the short headings.

A case-file landing page, using 1291:

```markdown
# Krückeberg No. 10 Berenbusch: Forest Allotment (1817–1818)

*Archive's title:* [your translation of the Bückeburg archive's title, unchanged]

*Call number:* NLA BU, K 2, A Nr. 1291
```

A document page:

```markdown
# Krückeberg's Petition (1 Jan. 1817)

*Listed in the case file's contents as:* Petition of the shoemaker Krückeberg No. 10 in
Berenbusch.
```

The Latin term "Designatio Actorum" is explained once, on the Case Files Explained page, and
plain-English labels are used everywhere else.

| File | Current `myst.yml` title | Proposed heading and `title:` |
| --- | --- | --- |
| 1237 | Krückeberg No. 10 Berenbusch Land Enlargement Request | Krückeberg No. 10 Berenbusch: Garden Enlargement (1798–1800) |
| 1291 | Allotments to Krückeberg no. 10 & Einliegers Vogt & Nordholz (1817 - 1818) | Krückeberg No. 10 Berenbusch: Forest Allotment (1817–1818) |
| 139 | (none) | Krückeberg No. 10 Berenbusch: Labour Relief & Sale (1824–1849) |
| 689 | Loan to Krückeberg no. 10 Berenbusch (1841-1845) | Krückeberg No. 10 Berenbusch: Loan of 200 Thaler (1841–1845) |
| 146 | Site No. 18 Berenbusch, 1808-1850 | Krückeberg No. 18 Berenbusch: New Settler Holding (1808–1850) |
| 147 | Holding No. 19 Berenbusch (1819-1820) in particular concerning the new settler holding of Triftmeyer No. 19 at Bärenbusch | Triftmeier No. 19 Berenbusch, beside Krückeberg No. 18 (1819–1820) |
| 188 | Sale of the Krückeberg property no. 18 in Berenbusch | Krückeberg No. 18 Berenbusch: Sale (1850) |

147 differs because that case file is about Triftmeier and mentions Krückeberg only as his
neighbour.

### Document pages

Keep Translation and Transliteration as two sections one after the other, as they are now. Do
not use tabs or dropdowns: a printed page cannot show hidden text, and the book needs both
texts visible. Replace the per-page glossaries with one glossary in `rentkammer/terms.md`,
using MyST's `{glossary}` directive and `{term}` role.

### Each folder

1. **139:** extend the timeline through September 1849, rename "Other Documents" to
   "Sale Documents (1849)", and add a Genealogical Significance section.
2. **147:** apply the new heading. The landing page is otherwise done.
3. **1237:** move the regency section to "Rentkammer Explained", as the page's own
   TODO says.  Rebuild the timeline as one row per event starting 29 May 1798, with a
   link to each document. Fold the ten narrative sections into the document pages, and
   fold `doc4-extra.md` into `doc4.md`.
4. **689:** replace the opening with two paragraphs on the debt to Hempel & Söhne and
   the 200 Reichsthaler loan. Keep the timeline. Move `amt-decree.md` and the service
  slip into a "Background documents" group in `myst.yml`, and put the numbering and
  analysis pages in a final "Supplementary notes" group or delete them.
5. **146:** move the two-Jobst-Heinrichs argument into the Genealogical Significance
   section or onto its own page at the end, together with the two Document 1
  analyses. Write a 139-style overview covering 1808–1810 and the 1850 sale.
6. **1291:** write the overview from scratch. It has three petitioners (Krückeberg,
   Vogt, Brüggemann), so the timeline needs a "Party" column.
7. **188:** keep it short, add the facts table and document headings, and either
   finish or drop `doc5.md`, `3-right.md` and `last-page.md`.

## Errors found along the way

All four errors from the first review are still present in jb2-nla, and two more have been
found since.

| File | Problem |
| --- | --- |
| `139/other-docs.md` | Says the sale was in 1850 and its table caption says no. 18; the pages it lists are dated 1849 and concern no. 10 |
| `139/content.md` | Says the documents are from 1822; they are from 1824 |
| `1237/content.md` | The English link for item 2 points to `doc3.md`; item 3 is dated 1800 where the index says 1799 |
| `146/content.md` | Item 2 links to `doc1.md` and item 11 links to `doc10.md` |
| `147/doc5.md` | The transliteration reads "Knückeberg No 18"; the translation and the drawing have "Krückeberg" |
| `myst.yml` | The 1291 title reads "Einliegers Vogt & Nordholz"; the Einliegers were Vogt and Brüggemann, of Nordholz |

`claude-case-file-analysis.md` was copied into jb2-nla and is excluded from the build in
`myst.yml`. It is now out of date: it still describes `_toc.yml`. Replacing it with this
review, or deleting it, would avoid two diverging versions.

## Next step

Restructure 1237 first: its content already exists and only needs rearranging. 1291 and 188
take the most work because their overviews have to be written, not moved.
