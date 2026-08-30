# MRCA of taxa from the synthetic tree

Most Recent Common Ancestor for a set of nodes

## Usage

``` r
tol_mrca(ott_ids = NULL, node_ids = NULL, ...)

# S3 method for class 'tol_mrca'
tax_sources(tax, ...)

# S3 method for class 'tol_mrca'
unique_name(tax, ...)

# S3 method for class 'tol_mrca'
tax_name(tax, ...)

# S3 method for class 'tol_mrca'
tax_rank(tax, ...)

# S3 method for class 'tol_mrca'
ott_id(tax, ...)

# S3 method for class 'tol_mrca'
source_list(tax, ...)
```

## Arguments

- ott_ids:

  Numeric vector. The ott ids for which the MRCA is desired.

- node_ids:

  Character vector. The node ids for which the MRCA is desired.

- ...:

  additional arguments to customize the API call (see
  [`rotl`](https://docs.ropensci.org/rotl/reference/rotl.md) for more
  information).

- tax:

  an object returned by `tol_mrca()`.

## Value

An invisible list of the MRCA node properties:

mrca

:   List of node properties.

nearest_taxon

:   A list of taxonomic properties of the nearest rootward taxon node to
    the MRCA node. Only returned if the MRCA node is a not taxon
    (otherwise the `taxon` list above is returned).

source_id_map

:   Named list of lists. Names correspond to the sourceid keys used in
    the support/conflict properties of the `mrca` list above. Source
    trees will have the following properties:

## Details

Get the MRCA of a set of nodes on the current synthetic tree. Accepts
any combination of node ids and ott ids as input. Returns information
about the most recent common ancestor (MRCA) node as well as the most
recent taxonomic ancestor (MRTA) node (the closest taxonomic node to the
MRCA node in the synthetic tree; the MRCA and MRTA may be the same
node). If they are the same, the taxonomic information will be in the
`mrca` slot, otherwise they will be in the `nearest_taxon` slot of the
list. If any of the specified nodes is not in the synthetic tree an
error will be returned.

Taxonomic methods
([`tax_sources()`](https://docs.ropensci.org/rotl/reference/taxonomy-methods.md),
[`ott_id()`](https://docs.ropensci.org/rotl/reference/taxonomy-methods.md),
[`unique_name()`](https://docs.ropensci.org/rotl/reference/taxonomy-methods.md),
...) are available on the objects returned by `tol_mrca()`. If the MRCA
node is MRTA, the name of the object returned by these methods will
start with ‘ott’, otherwise it will start with ‘mrca’.

## Examples

``` r
if (FALSE) { # \dontrun{
birds_mrca <- tol_mrca(ott_ids=c(412129, 119214))
ott_id(birds_mrca)
tax_sources(birds_mrca)
} # }
```
