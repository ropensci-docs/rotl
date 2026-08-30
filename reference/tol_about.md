# Information about the Tree of Life

Basic information about the Open Tree of Life (the synthetic tree)

## Usage

``` r
tol_about(include_source_list = FALSE, ...)

# S3 method for class 'tol_summary'
tax_rank(tax, ...)

# S3 method for class 'tol_summary'
tax_sources(tax, ...)

# S3 method for class 'tol_summary'
unique_name(tax, ...)

# S3 method for class 'tol_summary'
tax_name(tax, ...)

# S3 method for class 'tol_summary'
ott_id(tax, ...)
```

## Arguments

- include_source_list:

  Logical (default = `FALSE`). Return an ordered list of source trees.

- ...:

  additional arguments to customize the API call (see
  [`rotl`](https://docs.ropensci.org/rotl/reference/rotl.md) for more
  information).

- tax:

  an object created with a call to `tol_about`.

## Value

An invisible list of synthetic tree summary statistics:

date_created

:   String. The creation date of the tree.

num_source_studies

:   Integer. The number of studies (publications)used as sources.

num_source_trees

:   The number of trees used as sources (may be \>1 tree per study).

taxonomy_version

:   The Open Tree Taxonomy version used as a source.

filtered_flags

:   List. Taxa with these taxonomy flags were not used in construction
    of the tree.

root

:   List. Describes the root node:

source_list

:   List. Present only if `include_source_list` is `TRUE`. The sourceid
    ordering is the precedence order for synthesis, with relationships
    from earlier trees in the list having priority over those from later
    trees in the list. See `source_id_map` below for study details.

source_id_map

:   Named list of lists. Present only if `include_source_list` is
    `TRUE`. Names correspond to the ‘sourceids’ used in `source_list`
    above. Source trees will have the following properties:

synth_id

:   The unique string for this version of the tree.

## Details

Summary information about the current draft tree of life, including
information about the list of trees and the taxonomy used to build it.
The object returned by `tol_about` can be passed to the taxonomy methods
([`tax_name()`](https://docs.ropensci.org/rotl/reference/taxonomy-methods.md),
[`tax_rank()`](https://docs.ropensci.org/rotl/reference/taxonomy-methods.md),
[`tax_sources()`](https://docs.ropensci.org/rotl/reference/taxonomy-methods.md),
`ott_id`), to extract relevant taxonomic information for the root of the
synthetic tree.

## See also

[`source_list`](https://docs.ropensci.org/rotl/reference/source_list.md)
to explore the list of studies used in the synthetic tree (see example).

## Examples

``` r
if (FALSE) { # \dontrun{
res <- tol_about()
tax_sources(res)
ott_id(res)
studies <- source_list(tol_about(include_source_list=TRUE))} # }
```
