# Infer the taxonomic context from a list of names

Return a taxonomic context given a list of taxonomic names

## Usage

``` r
tnrs_infer_context(names = NULL, ...)
```

## Arguments

- names:

  Vector of taxon names.

- ...:

  additional arguments to customize the API request (see
  [`rotl`](https://docs.ropensci.org/rotl/reference/rotl.md) package
  documentation).

## Value

A list including the context name, the context ott id and possibly the
names in the query that have an ambiguous taxonomic meaning in the
query.

## Details

Find the least inclusive taxonomic context that includes all the
unambiguous names in the input set. Unambiguous names are names with
exact matches to non-homonym taxa. Ambiguous names (those without exact
matches to non-homonym taxa) are indicated in results.

## Examples

``` r
if (FALSE) { # \dontrun{
res <- tnrs_infer_context(names=c("Stellula calliope", "Struthio camelus"))
} # }
```
