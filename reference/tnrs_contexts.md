# TNRS contexts

This function returns a list of pre-defined taxonomic contexts (i.e.
clades) which can be used to limit the scope of tnrs queries.

## Usage

``` r
tnrs_contexts(...)
```

## Arguments

- ...:

  additional arguments to customize the API request (see
  [`rotl`](https://docs.ropensci.org/rotl/reference/rotl.md) package
  documentation).

## Value

Returns invisibly a list for each major clades (e.g., animals, microbes,
plants, fungi, life) whose elements contains the possible contexts.

## Details

Taxonomic contexts are available to limit the scope of TNRS searches.
These contexts correspond to uncontested higher taxa such as 'Animals'
or 'Land plants'. This service returns a list containing all available
taxonomic context names, which may be used as input (via the
`context_name` argument in other functions) to limit the search scope of
other services including
[`tnrs_match_names`](https://docs.ropensci.org/rotl/reference/tnrs_match_names.md).
