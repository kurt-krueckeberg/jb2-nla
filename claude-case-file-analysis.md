# Rentkammer Case Files: Navigation and Content Review

## Navigation consistency

In `myst.yml` all seven folders start with `index.md` → `cover.md` → `content.md`; 188 has no
`content.md` because it has no Designatio Actorum. Below that level they diverge:

- **Chapter titles:** each uses a different form. 1237 and 188 carry no dates, 146 puts the
  dates after a comma, 147 runs to 121 characters, and 139 has no `title:` at all. In MyST a
  toc `title:` is a navigation-only short title; MyST's own `short_title` field is capped at 40
  characters, and only the 146 chapter title fits within it.
- **Document titles:** none carry dates. Many entries have no `title:` (1237/doc6, 1291/doc13,
  18 and 21, eight in 689, all of 188), so the sidebar falls back to the page's long H1.
- **Nesting:** fixed in the port. In 147, `doc5.md` now sits under `content.md`, as in every
  other folder.
- **Order:** 146 still puts two analysis pages ahead of Document 1, and 689 still puts
  `amt-decree.md` ahead of Document 1.
- **Later documents:** 139 and 146 group them under `other-docs.md`; no other folder has such a
  group.
- **Orphans:** 18 pages are not listed in `myst.yml`: 13 in 689, 4 in 188 and 1 in 1237
  (`doc4-extra.md`; `actors.md` has been deleted).

## Best folder: 139

The `index.md` of 139 is still the landing page that best tells a layman, in order, what the file is about, who is involved, the outcome and the timeline. It opens with two plain paragraphs (the widow's 1824 petition and the 1849 sale before emigration), then a facts table, then a dated timeline. Its document pages also carry dates in their headings and nearly all open with a summary. Since the first review, 147 has gained a landing page of the same kind, which adds two sections worth copying everywhere: **Genealogical Significance** and a section pointing to the map.

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

Each folder should reach the 139 pattern: a landing page with a plain overview, a facts table, a timeline and a closing Genealogical Significance section, followed in `myst.yml` by cover, Designatio Actorum, documents, later documents and supplementary notes. Everything below uses features built into MyST; none needs a plugin or custom CSS.

1. **139:** extend the timeline through September 1849, add a `title:` to its `myst.yml` entry,
   rename "Other Documents" to "Sale Documents (1849)", and add a Genealogical Significance
   section.
2. **147:** shorten its `myst.yml` title to match the H1, "New Settler Holding of Triftmeier,
   No. 19 in Berenbusch (1819-1820)", or a shorter form of it. The landing page is otherwise
   done.
3. **1237:** move the regency section to "Rentkammer Explained", as the page's own TODO says.
   Give the page a real H1 instead of "Overview". Rebuild the timeline as one row per event
   starting 29 May 1798, with a link to each document. Fold the ten narrative sections into the
   document pages, and fold `doc4-extra.md` into `doc4.md`.
4. **689:** replace the opening with two paragraphs on the debt to Hempel & Söhne and the 200
   Reichsthaler loan. Keep the timeline. Move `amt-decree.md` and the service slip into a
   "Background documents" group in `myst.yml`, and put the numbering and analysis pages in a final
   "Supplementary notes" group or delete them.
5. **146:** move the two-Jobst-Heinrichs argument into the Genealogical Significance section or
   onto its own page at the end, together with the two Document 1 analyses. Write a 139-style
   overview covering 1808–1810 and the 1850 sale.
6. **1291:** write the overview from scratch. It has three petitioners (Krückeberg, Vogt,
   Brüggemann), so the timeline needs a "Party" column.
7. **188:** keep it short, add the facts table and `myst.yml` titles, and either finish or drop
   `doc5.md`, `3-right.md` and `last-page.md`.
8. **All folders, navigation:** give every `myst.yml` entry a `title:` of at most 40
   characters, in one form for chapters, "Subject, No. X Berenbusch (years)", and one for
   documents, "Type of document (date)". The page's H1 keeps the full title.
9. **All folders, document pages:** MyST's built-in `{tab-set}` can put Translation and
   Transliteration in two tabs, `{dropdown}` can hold docket details, and `{glossary}` with
   `{term}` can replace the per-page glossaries with one list in `rentkammer/terms.md`. No page
   uses any of these yet.

## Errors found along the way

All four errors from the first review are still present in jb2-nla, and a fifth has been added.

| File | Problem |
| --- | --- |
| `139/other-docs.md` | Says the sale was in 1850 and its table caption says no. 18; the pages it lists are dated 1849 and concern no. 10 |
| `139/content.md` | Says the documents are from 1822; they are from 1824 |
| `1237/content.md` | The English link for item 2 points to `doc3.md`; item 3 is dated 1800 where the index says 1799 |
| `146/content.md` | Item 2 links to `doc1.md` and item 11 links to `doc10.md` |
| `147/doc5.md` | The transliteration reads "Knückeberg No 18"; the translation and the drawing have "Krückeberg" |

`claude-case-file-analysis.md` was copied into jb2-nla and is excluded from the build in `myst.yml`. It is now out of date: it still describes `_toc.yml`. Replacing it with this review, or deleting it, would avoid two diverging versions.

## Next step

Restructure 1237 first: its content already exists and only needs rearranging. 1291 and 188
take the most work because their overviews have to be written, not moved.
