# Find Trees

Return a list of studies for which trees match a given set of properties

## Usage

``` r
studies_find_trees(
  property = NULL,
  value = NULL,
  verbose = FALSE,
  exact = FALSE,
  detailed = TRUE,
  ...
)
```

## Arguments

- property:

  The property to be searched on (character)

- value:

  The property-value to be searched on (character)

- verbose:

  Should the output include all metadata? (logical, default `FALSE`)

- exact:

  Should exact matching be used for the value? (logical, default
  `FALSE`)

- detailed:

  Should a detailed report be provided? If `TRUE` (default), the output
  will include metadata about the study that include trees matching the
  property. Otherwise, only information about the trees will be
  provided.

- ...:

  additional arguments to customize the API request (see
  [`rotl`](https://docs.ropensci.org/rotl/reference/rotl.md) package
  documentation).

## Value

A data frame that summarizes the trees found (and their associated
studies) for the requested criteria. If a study has more than 5 trees,
the `tree_ids` of the first ones will be shown, followed by `...` to
indicate that more are present.

If `detailed=FALSE`, the data frame will include the study ids of the
study (`study_ids`), the number of trees in this study that match the
search criteria (`n_matched_trees`), the tree ids that match the search
criteria (`match_tree_ids`).

If `detailed=TRUE`, in addition of the fields listed above, the data
frame will also contain the total number of trees associated with the
study (`n_trees`), all the tree ids associated with the study
(`tree_ids`), the tree id that is a potential candidate for inclusion in
the synthetic tree (if any) (`candidate`), the year the study was
published (`study_year`), the title of the study (`title`), the DOI for
the study (`study_doi`).

## Details

The list of possible values to be used as values for the argument
`property` can be found using the function
[`studies_properties`](https://docs.ropensci.org/rotl/reference/studies_properties.md).

## See also

[`studies_properties`](https://docs.ropensci.org/rotl/reference/studies_properties.md)
which lists properties the studies can be searched on.
[`list_trees`](https://docs.ropensci.org/rotl/reference/list_trees.md)
for listing the trees that match the query.

## Examples

``` r
if (FALSE) { # \dontrun{
res <- studies_find_trees(property="ot:ottTaxonName", value="Drosophila",
                          detailed=FALSE)
## summary of the trees and associated studies that match this criterion
res
## With metadata about the studies (default)
res <- studies_find_trees(property="ot:ottTaxonName", value="Drosophila",
                          detailed=TRUE)
## The list of trees for each study that match the search criteria
list_trees(res)
## the trees for a given study
list_trees(res, study_id = "pg_2769")
} # }
```
