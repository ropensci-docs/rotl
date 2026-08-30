# Lineage of a taxon

Extract the lineage information (higher taxonomy) from an object
returned by
[`taxonomy_taxon_info`](https://docs.ropensci.org/rotl/reference/taxonomy_taxon_info.md).

## Usage

``` r
tax_lineage(tax, ...)

# S3 method for class 'taxon_info'
tax_lineage(tax, ...)
```

## Arguments

- tax:

  an object created by
  [`taxonomy_taxon_info`](https://docs.ropensci.org/rotl/reference/taxonomy_taxon_info.md)
  using the argument `include_lineage=TRUE`.

- ...:

  additional arguments (currently unused).

## Value

A list with one slot per taxon that contains a data frame with 3
columns: the taxonomy rank, the name, and unique name for all taxa
included in the lineage of the taxon up to the root of the tree.

## Details

The object passed to this function must have been created using the
argument `include_lineage=TRUE`.
