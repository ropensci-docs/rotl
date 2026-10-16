# Subtree from the Open Tree of Life

Return the induced subtree on the synthetic tree that relates a list of
nodes.

## Usage

``` r
tol_induced_subtree(
  ott_ids = NULL,
  node_ids = NULL,
  label_format = NULL,
  file,
  ...
)
```

## Arguments

- ott_ids:

  Numeric vector. OTT ids indicating nodes to be used as tips in the
  induced tree.

- node_ids:

  Character vector. Node ids indicating nodes to be used as tips in the
  induced tree.

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
phylogenetic tree of class `phylo`.

Otherwise, the function returns invisibly a logical indicating whether
the file was successfully created.

Note that the tree returned when specifying a file name with the `file`
argument is the “raw” Newick string returned by Open Tree of Life. This
string contains singleton nodes, and therefore will be different from
the tree returned as a `phylo` object which will not contain these
singleton nodes.

## Details

Return a tree with tips corresponding to the nodes identified in the
input set that is consistent with the topology of the current synthetic
tree. This tree is equivalent to the minimal subtree induced on the
draft tree by the set of identified nodes.

## Examples

``` r
if (FALSE) { # \dontrun{
## Result as a `phylo` object
res <- tol_induced_subtree(ott_ids = c(292466, 267845, 316878, 102710))

## Raw Newick string from Open Tree of Life
tree_file <- tempfile(fileext = ".tre")
tol_induced_subtree(ott_ids = c(292466, 267845, 316878, 102710),
                    file=tree_file)

} # }
```
