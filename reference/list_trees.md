# List trees ids in objects returned by [`studies_find_studies`](https://docs.ropensci.org/rotl/reference/studies_find_studies.md) and [`studies_find_trees`](https://docs.ropensci.org/rotl/reference/studies_find_trees.md)

`list_trees` returns all trees associated with a particular study when
used on an object returned by
[`studies_find_studies`](https://docs.ropensci.org/rotl/reference/studies_find_studies.md),
but only the trees that match the search criteria when used on objects
returned by
[`studies_find_trees`](https://docs.ropensci.org/rotl/reference/studies_find_trees.md).

## Usage

``` r
list_trees(matched_studies, ...)

# S3 method for class 'matched_studies'
list_trees(matched_studies, study_id, ...)
```

## Arguments

- matched_studies:

  an object created by `studies_find_trees` or `studies_find_studies`.

- ...:

  Currently unused

- study_id:

  a `study_id` listed in the object returned by `studies_find_trees`

## Value

`list_trees` returns a list of the tree_ids for each study that match
the requested criteria. If a `study_id` is provided, then only the trees
for this study are returned as a vector.

## See also

[`studies_find_studies`](https://docs.ropensci.org/rotl/reference/studies_find_studies.md)
and
[`studies_find_trees`](https://docs.ropensci.org/rotl/reference/studies_find_trees.md).
The help for these functions have examples demonstrating the use of
`list_trees`.
