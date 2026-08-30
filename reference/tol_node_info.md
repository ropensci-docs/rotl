# Node info

Get summary information about a node in the synthetic tree

## Usage

``` r
tol_lineage(tax, ...)

tol_node_info(ott_id = NULL, node_id = NULL, include_lineage = FALSE, ...)

# S3 method for class 'tol_node'
tax_rank(tax, ...)

# S3 method for class 'tol_node'
tax_sources(tax, ...)

# S3 method for class 'tol_node'
unique_name(tax, ...)

# S3 method for class 'tol_node'
tax_name(tax, ...)

# S3 method for class 'tol_node'
ott_id(tax, ...)

# S3 method for class 'tol_node'
source_list(tax, ...)

# S3 method for class 'tol_node'
tax_lineage(tax, ...)

# S3 method for class 'tol_node'
tol_lineage(tax, ...)
```

## Arguments

- tax:

  an object returned by `tol_node_info`.

- ...:

  additional arguments to customize the API call (see ?rotl for more
  information)

- ott_id:

  Numeric. The OpenTree taxonomic identifier.

- node_id:

  Character. The OpenTree node identifier.

- include_lineage:

  Logical (default = FALSE). Whether to return the lineage of the node
  from the synthetic tree.

## Value

`tol_node_info` returns an invisible list of summary information about
the queried node:

- node_id:

  String. The canonical identifier of the node.

- num_tips:

  Numeric. The number of descendant tips.

- partial_path_of:

  List. The edge below this synthetic tree node is compatible with the
  edge below each of these input tree nodes (one per tree). Each
  returned element is reported as sourceid:nodeid.

- query:

  The node id that resolved to this node. This can differ from the
  node_id field if the query id is not canonical.

- taxon:

  A list of taxonomic properties. Only returned if the queried node is a
  taxon. Each source has:

- supported_by:

  List. Input tree nodes (one per tree) that support this synthetic tree
  node. Each returned element is reported as sourceid:nodeid.

- terminal:

  List. Input tree nodes (one per tree) that are equivalent to this
  synthetic tree node (via an exact mapping, or the input tree terminal
  may be the only terminal descended from this synthetic tree node. Each
  returned element is reported as sourceid:nodeid.

- conflicts_with:

  Named list of lists. Names correspond to sourceid keys. Each list
  contains input tree node ids (one or more per tree) that conflict with
  this synthetic node.

`tol_lineage` and `tax_lineage` return data frames. `tol_lineage`
indicate for each ancestor its node identifier, the number of tips
descending from that node, and whether it corresponds to a taxonomic
level.

## Details

Returns summary information about a node in the graph. The node of
interest may be specified using either a node id or an taxon id, but not
both. If the specified node or OTT id is not in the graph, an error will
be returned.

If the argument `include_lineage=TRUE` is used, you can use
[`tax_lineage()`](https://docs.ropensci.org/rotl/reference/tax_lineage.md)
or `tol_lineage` to return the taxonomic information or the node
information for all the ancestors to this node, down to the root of the
tree.

## Examples

``` r
if (FALSE) { # \dontrun{
birds <- tol_node_info(ott_id=81461, include_lineage=TRUE)
source_list(birds)
tax_rank(birds)
ott_id(birds)
tax_lineage(birds)
tol_lineage(birds)} # }
```
