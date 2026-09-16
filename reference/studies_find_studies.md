# Find a Study

Return the identifiers of studies that match given properties

## Usage

``` r
studies_find_studies(
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

  The property value to be searched on (character)

- verbose:

  Should the output include all metadata (logical default `FALSE`)

- exact:

  Should exact matching be used? (logical, default `FALSE`)

- detailed:

  If `TRUE` (default), the function will return a data frame that
  summarizes information about the study (see ‘Value’). Otherwise, it
  only returns the study identifiers.

- ...:

  additional arguments to customize the API request (see
  [`rotl`](https://docs.ropensci.org/rotl/reference/rotl.md) package
  documentation).

## Value

If `detailed=TRUE`, the function returns a data frame listing the study
id (`study_ids`), the number of trees associated with this study
(`n_trees`), the tree ids (at most 5) associated with the studies
(`tree_ids`), the tree id that is a candidate for the synthetic tree if
any (`candidate`), the year of publication of the study (`study_year`),
the title of the publication for the study (`title`), and the DOI
(Digital Object Identifier) for the study (`study_doi`).

If `detailed=FALSE`, the function returns a data frame with a single
column containing the study identifiers.

## See also

[`studies_properties`](https://docs.ropensci.org/rotl/reference/studies_properties.md)
which lists properties against which the studies can be searched.
[`list_trees`](https://docs.ropensci.org/rotl/reference/list_trees.md)
that returns a list for all tree ids associated with a study.

## Examples

``` r
if (FALSE) { # \dontrun{
## To match a study for which the identifier is already known
one_study <- studies_find_studies(property="ot:studyId", value="pg_719")
list_trees(one_study)

## To find studies pertaining to Mammals
mammals <- studies_find_studies(property="ot:focalCladeOTTTaxonName",
                                value="mammalia")
## To extract the tree identifiers for each of the studies
list_trees(mammals)
## ... or for a given study
list_trees(mammals, "ot_308")

## Just the identifiers without other information about the studies
mammals <- studies_find_studies(property="ot:focalCladeOTTTaxonName",
                                value="mammalia", detailed=FALSE)
} # }
```
