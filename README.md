# Baltic angiosperm family phylogeny

Interactive APG V order backbone for Baltic-region plant families, with zoom,
panning, expandable orders, and family counts. Open `index.html` to explore.

Select a family and open **Accepted Baltic genera** or **Accepted Baltic species**
to browse searchable POWO-linked lists. Species are grouped by genus and include
only accepted species, including hybrids. Subspecies, varieties and forms are
excluded. Lists are embedded and work offline; POWO links open in a new tab.

Coverage: 103 flowering-family tips in 36 orders; all 117 WCVP source family
names are accessible, including 13 non-flowering families outside APG V.
The Baltic botanical region includes Estonia, Latvia, Lithuania and Kaliningrad.
Family fans within orders do not imply resolved family relationships. Branch
lengths have no time or distance units. See [methods and citations](METHODS.md).

## Downloads

- [Full vector tree](baltic_apgv_full.svg)
- [Newick tree](baltic_apgv.nwk)
- [R phylo object](baltic_apgv_phylo.rds)
- [Family mapping](family_mapping.csv)
- [Tree data and provenance](phylogeny_data.json)

## GitHub Pages

In repository Settings > Pages, choose **Deploy from a branch**, then
**main** and **/(root)**, and save. The site entry point is `index.html`.
An empty `.nojekyll` file disables Jekyll processing. No build step is needed.

This repository contains only the standalone visualization, derived exports,
and methods. The local R workspace and database backups are stored separately.
The APG V article is cited rather than redistributed. WCVP data attribution
and source details are retained in the methods and embedded provenance.