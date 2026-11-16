# Taxonomy subtree

Given an ott id, return the inclusive taxonomic subtree descended from
the specified taxon.

## Usage

``` r
taxonomy_subtree(
  ott_id = NULL,
  output_format = c("taxa", "newick", "phylo", "raw"),
  label_format = NULL,
  file,
  ...
)
```

## Arguments

- ott_id:

  The ott id of the taxon of interest.

- output_format:

  the format of the object to be returned. See the ‘Return’ section.

- label_format:

  Character. Defines the label type; one of “`name`”, “`id`”, or
  “`name_and_id`” (the default).

- file:

  the file name where to save the output of the function. Ignored unless
  `output_format` is set to “`phylo`”.

- ...:

  additional arguments to customize the API request (see
  [`rotl`](https://docs.ropensci.org/rotl/reference/rotl.md) package
  documentation).

## Value

If the `file` argument is missing:

- “`taxa`”:

  a list of the taxa names (species) in slot `tip_label`, and
  higher-level taxonomy (e.g., families, genera) in slot `edge_label`,
  descending from the taxa corresponding to the `ott_id` provided.

- “`newick`”:

  a character vector containing the newick formatted string
  corresponding to the taxonomic subtree for the `ott_id` provided.

- “`phylo`”:

  an object of the class `phylo` from the `ape` package.

- “`raw`”:

  the direct output from the API, i.e., a list with an element named
  ‘newick’ that contains the subtree as a newick formatted string.

If a `file` argument is provided (and `output_format` is set to
“`phylo`”), a logical indicating whether the file was successfully
created.

## Details

If the output of this function is exported to a file, the only possible
value for the `output_format` argument is “`newick`”. If the file
provided already exists, it will be silently overwritten.

## Examples

``` r
if (FALSE) { # \dontrun{
req <- taxonomy_subtree(ott_id=515698)
plot(taxonomy_subtree(ott_id=515698, output_format="phylo"))
} # }
```
