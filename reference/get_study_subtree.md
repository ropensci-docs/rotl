# Study Subtree

Retrieve subtree from a specific tree in the Open Tree of Life data
store

## Usage

``` r
get_study_subtree(
  study_id,
  tree_id,
  subtree_id,
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

  the study identifier (character)

- tree_id:

  the tree identifier (character)

- subtree_id, :

  either a node id that specifies a subtree or “ingroup” which returns
  the ingroup for this subtree.

- object_format:

  the class of the object returned by the function (default, and
  currently only possibility `phylo` from the `ape` package)

- tip_label:

  the format of the tip labels. “`original_label`” (default) returns the
  original labels as provided in the study, “`ott_id`” labels are
  replaced by their ott IDs, “`ott_taxon_name`” labels are replaced by
  their Open Tree Taxonomy taxon name.

- file_format:

  character, the file format to use to save the results of the query
  (possible values, ‘newick’ or ‘nexus’).

- file:

  character, the path and file name where the output should be written.

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

## Examples

``` r
if (FALSE) { # \dontrun{
small_tr <- get_study_subtree(study_id="pg_1144", tree_id="tree5800", subtree_id="node991044")
ingroup  <- get_study_subtree(study_id="pg_1144", tree_id="tree5800", subtree_id="ingroup")
nexus_file <- tempfile(fileext=".nex")
get_study_subtree(study_id="pg_1144", tree_id="tree5800", subtree_id="ingroup", file=nexus_file,
                  file_format="nexus")
} # }
```
