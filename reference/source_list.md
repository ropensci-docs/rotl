# List of studies used in the Tree of Life

Retrieve the detailed information for the list of studies used in the
Tree of Life.

## Usage

``` r
source_list(tax, ...)

# S3 method for class 'tol_summary'
source_list(tax, ...)
```

## Arguments

- tax:

  a list containing a `source_id_map` slot.

- ...:

  additional arguments (currently unused)

## Value

a data frame

## Details

This function takes the object resulting from
`tol_about(study_list = TRUE)`,
[`tol_mrca()`](https://docs.ropensci.org/rotl/reference/tol_mrca.md),
[`tol_node_info()`](https://docs.ropensci.org/rotl/reference/tol_node_info.md),
and returns a data frame listing the `tree_id`, `study_id` and `git_sha`
for the studies currently included in the Tree of Life.
