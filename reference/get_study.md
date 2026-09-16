# Get all the trees associated with a particular study

Returns the trees associated with a given study

## Usage

``` r
get_study(
  study_id = NULL,
  object_format = c("phylo", "nexml"),
  file_format,
  file,
  ...
)
```

## Arguments

- study_id:

  the study ID for the study of interest (character)

- object_format:

  the class of the object the query should return (either `phylo` or
  `nexml`). Ignored if `file_format` is specified.

- file_format:

  the format of the file to be generated (`newick`, `nexus`, `nexml` or
  `json`).

- file:

  the file name where the output of the function will be saved.

- ...:

  additional arguments to customize the API request (see
  [`rotl`](https://docs.ropensci.org/rotl/reference/rotl.md) package
  documentation).

## Value

if `file_format` is missing, an object of class `phylo` or `nexml`,
otherwise a logical indicating whether the file was successfully
created.

## Details

If `file_format` is missing, the function returns an object of the class
`phylo` from the `ape` package (default), or an object of the class
`nexml` from the `RNeXML` package.

Otherwise `file_format` can be either `newick`, `nexus`, `nexml` or
`json`, and the function will generate a file of the selected format. In
this case, a file name needs to be provided using the argument `file`.
If a file with the same name already exists, it will be silently
overwritten.

## See also

[`get_study_meta`](https://docs.ropensci.org/rotl/reference/get_study_meta.md)

## Examples

``` r
if (FALSE) { # \dontrun{
that_one_study <- get_study(study_id="pg_719", object_format="phylo")
if (require(RNeXML)) { ## if RNeXML is installed get the object directly
   nexml_study <- get_study(study_id="pg_719", object_format="nexml")
} else { ## otherwise write it to a file
   get_study(study_id="pg_719", file_format="nexml", file=tempfile(fileext=".nexml"))
}
} # }
```
