# Baltic angiosperm family phylogeny according to APG V

Open **`index.html`** in a web browser. It is self-contained and works
offline. Scroll or pinch to zoom, drag to pan, click internal nodes to expand or
collapse, and use the family selector for keyboard-accessible selection.
The opening view shows 36 Baltic orders; **Expand families** displays every
APG V family tip. At low zoom labels are thinned; zoom in to read all of them. Family
details show the source names and accepted species/genus counts.

Select a family, then open **Accepted Baltic genera** for its linked genus
list, or **Accepted Baltic species** for species grouped under their genera.
Both lists have a search field and use the original POWO taxon links. Only one
list is open at a time, and long lists scroll within the family panel. Species
lists include accepted species only, including accepted hybrids; subspecies,
varieties, forms, other infraspecific ranks, and unplaced names are excluded.
The 735 genera and 2,732 species match the counts in the saved regional snapshot.
The Orobanchaceae list combines the original Orobanchaceae and Phrymaceae rows.
Lists also work for the 13 non-flowering families in the separate scope panel.

## What the tree represents

- **Order topology:** manually transcribed from Figure 1, printed page 847
  (PDF page 3), in APG V (2026), doi:10.1111/jse.70096. Original polytomies are
  preserved. Orders without Baltic representatives are pruned; this does not
  imply that absent orders have no global representatives.
- **Family membership and displayed sequence:** Appendix B, printed pages
  869-874 (PDF pages 25-30). All 407 family entries and their numbers were
  parsed and checked before matching the Baltic subset. The linear sequence
  determines display order only, not new branching relationships.
- **Family branches within orders:** dashed unresolved membership fans.
  Figure 1 is an order-level synopsis, not a fully resolved family phylogeny.
  Unresolved fans here indicate that within-order resolution was not supplied
  by this construction; they do not claim that published research cannot
  resolve those families.
- **No branch lengths:** this is a cladogram, with no estimated ages,
  substitutions, confidence values, or ancestral-state inference. Do not use
  its display lengths as evolutionary distances.

## Coverage and family changes

The source is the verified `powo.powo_baltic` WCVP v16 snapshot (released
4 June 2026; extraction `wcvp-v16-blt-20261110T113805Z`).

All **117 source family names** are accounted for:

- **104 flowering-plant source names map to 103 APG V family tips.**
  APG V includes Phrymaceae in Orobanchaceae (section 6, point 24, printed
  page 856). Both original source families and their combined regional counts
  remain linked to the Orobanchaceae tip. No database names were overwritten.
- **13 non-flowering families** are listed separately, with counts and source
  links: Aspleniaceae, Cupressaceae, Dennstaedtiaceae, Equisetaceae, Isoetaceae,
  Lycopodiaceae, Marsileaceae, Ophioglossaceae, Pinaceae, Polypodiaceae,
  Salviniaceae, Selaginellaceae, and Taxaceae. APG V has no phylogenetic
  placement for these groups. No unsupported common branch or placement is
  invented for them.

The region is TDWG **BLT**, comprising Estonia, Latvia, Lithuania and Kaliningrad.
The snapshot retains introduced, hybrid, infraspecific, unplaced, extinct and
doubtful records. Displayed species/genus counts include only taxonomically
accepted records at those respective ranks, but do not filter out introduced,
hybrid or geographically uncertain/extinct taxa. One accepted species in the
source is inferred from a Baltic subspecies. These are regional snapshot
counts, not a current native flora count or confirmed Lithuanian occurrences.

## Files

| File | Purpose |
| --- | --- |
| `index.html` | Interactive self-contained browser view |
| `baltic_apgv_full.svg` | Full-size vector figure from R/ape, with all 103 tips |
| `baltic_apgv.nwk` | Family-membership cladogram in Newick format, without lengths |
| `baltic_apgv_phylo.rds` | Same tree as an R `phylo` object |
| `family_mapping.csv` | Every original family, APG V name/order, paper number/page, and mapping change |
| `phylogeny_data.json` | Tree, family counts, non-flowering families, and provenance |
| `preview.png` | Browser screenshot of the order overview |
| `browser_checks.json` | Browser interaction checks at desktop and narrow widths |

The 13 non-flowering families are not Newick tips because they are outside the
source paper's scope. The Newick includes the 103 APG V flowering-family tips
and their unresolved within-order fans; it is not a fully resolved family tree.

## Rebuild in R

From the project root:

```r
source('scripts/build_baltic_phylogeny.R', encoding = 'UTF-8')
tree <- readRDS('output/phylogeny/baltic_apgv_phylo.rds')
ape::Ntip(tree)  # 103
```

Required installed packages: pdftools, jsonlite, digest, ape (and data.table
for the source snapshot). The script reads the saved RDS rather than rerunning
the extraction or changing PostgreSQL. The original source PDF is copied into
`data/raw/apg_v_2026.pdf`; the full parsed classification and the unpruned
68-terminal order backbone (66 orders plus Huaceae and Columelliaceae) are
retained under `data/phylogeny/`.

Browser checks can be rerun from PowerShell with
`./scripts/check_phylogeny.ps1` (requires local Google Chrome). They check all
117 source family choices, zoom buttons, wheel zoom, expansion of all 103 tips,
collapse of an order's family fan, the Phrymaceae merger, the outside-APG scope
message, finite SVG coordinates, and responsive page width. They also verify
list counts, POWO URLs, genus grouping, search/empty/clear states, one-species
families, merged families, and bounded list height. Actual viewport widths of
1440, 900, 500 and 380 CSS pixels are set through Chrome's debugging protocol;
Windows Chrome's window-size flag alone may clamp to a wider viewport.
Open-list previews were inspected in light and dark themes at desktop and phone
widths. Native disclosure controls support keyboard activation. Phone list links
have 44-pixel touch targets, and search inputs use 16-pixel type to avoid iOS
focus zoom.

## Citation

The Angiosperm Phylogeny Group. 2026. Large-scale nuclear and plastid
phylogenomic analyses inform an updated Angiosperm Phylogeny Group
classification: APG V. Journal of Systematics and Evolution 64: 845-874.
https://doi.org/10.1111/jse.70096


## Hosting package

This publication folder contains only the interactive tree and derived exports.
Source PDFs, R workspace images, database backups, and bulk WCVP files stay in
the local analysis project. Rebuild instructions above refer to that project.

WCVP source: Royal Botanic Gardens, Kew, World Checklist of Vascular Plants,
version 16 (4 June 2026), https://doi.org/10.34885/egs6-cp24.
The source download README specifies CC BY 3.0.
