# Properties of the Studies

Return the list of study properties that can be used to search studies
and trees used in the synthetic tree.

## Usage

``` r
studies_properties(...)
```

## Arguments

- ...:

  additional arguments to customize the API request (see
  [`rotl`](https://docs.ropensci.org/rotl/reference/rotl.md) package
  documentation).

## Value

A list of the study properties that can be used to find studies and
trees that are contributing to the synthetic tree.

## Details

The list returned has 2 elements `tree_properties` and
`studies_properties`. Each of these elements lists additional arguments
to customize the API request properties that can be used to search for
trees and studies that are contributing to the synthetic tree. The
definitions of these properties are available from
<https://github.com/OpenTreeOfLife/phylesystem-api/wiki/NexSON>

## See also

[`studies_find_trees`](https://docs.ropensci.org/rotl/reference/studies_find_trees.md)

## Examples

``` r
if (FALSE) { # \dontrun{
 all_the_properties <- studies_properties()
 unlist(all_the_properties$tree_properties)
} # }
```
