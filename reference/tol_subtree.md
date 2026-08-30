# Extract a subtree from the synthetic tree

Extract a subtree from the synthetic tree from an Open Tree node id.

## Usage

``` r
tol_subtree(ott_id = NULL, node_id = NULL, label_format = NULL, file, ...)
```

## Arguments

- ott_id:

  Numeric. The ott id of the node in the tree that should serve as the
  root of the tree returned.

- node_id:

  Character. The node id of the node in the tree that should serve as
  the root of the tree returned.

- label_format:

  Character. Defines the label type; one of “`name`”, “`id`”, or
  “`name_and_id`” (the default).

- file:

  If specified, the function will write the subtree to a file in newick
  format.

- ...:

  additional arguments to customize the API call (see
  [`rotl`](https://docs.ropensci.org/rotl/reference/rotl.md) for more
  information).

## Value

If no value is specified to the `file` argument (default), a
phylogenetic tree of class `phylo`. Otherwise, the function returns
invisibly a logical indicating whether the file was successfully
created.

## Details

Given a node, return the subtree of the synthetic tree descended from
that node. The start node may be specified using either a node id or an
ott id, but not both. If the specified node is not in the synthetic tree
an error will be returned. There is a size limit of 25000 tips for this
method.

## Examples

``` r
if (FALSE) { # \dontrun{
res <- tol_subtree(ott_id=241841)} # }
```
