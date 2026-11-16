# Study Tree

Returns a specific tree from within a study

## Usage

``` r
get_study_tree(
  study_id = NULL,
  tree_id = NULL,
  object_format = c("phylo"),
  tip_label = c("original_label", "ott_id", "ott_taxon_name"),
  file_format,
  file,
  deduplicate = TRUE,
  ...
)
```

## Arguments

- study_id:

  the identifier of a study (character)

- tree_id:

  the identifier of a tree within the study

- object_format:

  the class of the object to be returned (default and currently only
  possible value `phylo` from the `ape` package).

- tip_label:

  the format of the tip labels. “`original_label`” (default) returns the
  original labels as provided in the study, “`ott_id`” labels are
  replaced by their ott IDs, “`ott_taxon_name`” labels are replaced by
  their Open Tree Taxonomy taxon name.

- file_format:

  the format of the file to be generated (`newick` default, `nexus`, or
  `json`).

- file:

  the file name where the output of the function will be saved.

- deduplicate:

  logical (default `TRUE`). If the tree returned by the study contains
  duplicated taxon names, should they be made unique? It is normally
  illegal for NEXUS/Newick tree strings to contain duplicated tip names.
  This is a workaround to circumvent this requirement. If `TRUE`,
  duplicated tip labels will be appended `_1`, `_2`, etc.

- ...:

  additional arguments to customize the API request (see
  [`rotl`](https://docs.ropensci.org/rotl/reference/rotl.md) package
  documentation).

## Value

if `file_format` is missing, an object of class `phylo`, otherwise a
logical indicating whether the file was successfully created.

## Examples

``` r
if (FALSE) { # \dontrun{
 tree <- get_study_tree(study_id="pg_1144", tree_id="tree2324")

 ## comparison of the first few tip labels depending on the options used
 head(get_study_tree(study_id="pg_1144", tree_id="tree2324", tip_label="original_label")$tip.label)
 head(get_study_tree(study_id="pg_1144", tree_id="tree2324", tip_label="ott_id")$tip.label)
 head(get_study_tree(study_id="pg_1144", tree_id="tree2324", tip_label="ott_taxon_name")$tip.label)
} # }
```
