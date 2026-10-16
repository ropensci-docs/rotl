# Strip OTT ids from tip labels

Strip OTT ids from tip labels

## Usage

``` r
strip_ott_ids(tip_labels, remove_underscores = FALSE)
```

## Arguments

- tip_labels:

  a character vector containing tip labels (most likely the `tip.label`
  element from a tree returned by
  [`tol_induced_subtree`](https://docs.ropensci.org/rotl/reference/tol_induced_subtree.md)

- remove_underscores:

  logical (defaults to FALSE). If set to TRUE underscores in tip labels
  are converted to spaces

## Value

A character vector containing the contents of `tip_labels` with any OTT
ids removed.

## Examples

``` r
if (FALSE) { # \dontrun{
genera <- c("Perdix", "Setophaga", "Cinclus", "Struthio")
tr <- tol_induced_subtree(ott_ids=c(102710, 285198, 267845, 292466))
tr$tip.label %in% genera
tr$tip.label <- strip_ott_ids(tr$tip.label)
tr$tip.label %in% genera
} # }
```
