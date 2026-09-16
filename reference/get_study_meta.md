# Study Metadata

Retrieve metadata about a study in the Open Tree of Life datastore

## Usage

``` r
get_tree_ids(sm)

get_publication(sm)

candidate_for_synth(sm)

get_study_year(sm)

# S3 method for class 'study_meta'
get_tree_ids(sm)

# S3 method for class 'study_meta'
get_publication(sm)

# S3 method for class 'study_meta'
candidate_for_synth(sm)

# S3 method for class 'study_meta'
get_study_year(sm)

get_study_meta(study_id, ...)
```

## Arguments

- sm:

  an object created by `get_study_meta`

- study_id:

  the study identifier (character)

- ...:

  additional arguments to customize the API request (see
  [`rotl`](https://docs.ropensci.org/rotl/reference/rotl.md) package
  documentation).

## Value

named-list containing the metadata associated with the study requested

## Details

`get_study_meta` returns a long list of attributes for the studies that
are contributing to the synthetic tree. To help with the extraction of
relevant information from this list, several helper functions exists:

- get_tree_ids:

  The identifiers of the trees associated with the study.

- get_publication:

  The citation information of the publication for the study. The DOI (or
  URL) for the study is available as an attribute to the returned object
  (i.e., `attr(object, "DOI")` ).

- candidate_for_synth:

  The identifier of the tree(s) from the study used in the synthetic
  tree. This is a subset of the result of `get_tree_ids`.

- get_study_year:

  The year of publication of the study.

## Examples

``` r
if (FALSE) { # \dontrun{
req <- get_study_meta("pg_719")
get_tree_ids(req)
candidate_for_synth(req)
get_publication(req)
get_study_year(req)
} # }
```
