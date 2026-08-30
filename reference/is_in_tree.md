# Check that OTT ids occur in the Synthetic Tree

Some valid taxonomic names do not occur in the Synthetic Tree. This
convenience function allows you to check whether a given Open Tree
Taxonomy identifier (OTT id) is in the tree. A taxonomic name may not
occur in the synthetic tree because (1) it is an extinct or invalid
taxon, or (2) it is part of a group that is not monophyletic in the
tree.

## Usage

``` r
is_in_tree(ott_ids, ...)
```

## Arguments

- ott_ids:

  a vector of Open Tree Taxonomy identifiers

- ...:

  additional arguments to customize the API request (see
  [`rotl`](https://docs.ropensci.org/rotl/reference/rotl.md) package
  documentation).

## Value

A named logical vector. `TRUE` indicates that the OTT id is in the
synthetic tree, and `FALSE` that it is not.

## Examples

``` r
if (FALSE) { # \dontrun{
  plant_families <- c("Asteraceae", "Solanaceae", "Poaceae", "Amaranthaceae",
                      "Zamiaceae", "Araceae", "Juncaceae")
  matched_names <- tnrs_match_names(plant_families)
  ## This fails because some ott ids are not in the tree
  ## plant_tree <- tol_induced_subtree(ott_id(matched_names))
  ## So let's check which ones are actually in the tree first:
  in_tree <- is_in_tree(ott_id(matched_names))
  ## This now works:
  plant_tree <- tol_induced_subtree(ott_id(matched_names)[in_tree])
} # }
```
