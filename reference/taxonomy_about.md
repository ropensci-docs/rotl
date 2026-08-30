# Information about the Open Tree Taxonomy

Summary information about the Open Tree Taxonomy (OTT)

## Usage

``` r
taxonomy_about(...)
```

## Arguments

- ...:

  additional arguments to customize the API request (see
  [`rotl`](https://docs.ropensci.org/rotl/reference/rotl.md) package
  documentation).

## Value

A list with the following properties:

- weburl:

  String. The release page for this version of the taxonomy.

- author:

  String. The author string.

- name:

  String. The name of the taxonomy.

- source:

  String. The full identifying information for this version of the
  taxonomy.

- version:

  String. The version number of the taxonomy.

## Details

Return metadata and information about the taxonomy itself. Currently,
the available metadata is fairly sparse, but includes (at least) the
version, and the location from which the complete taxonomy source files
can be downloaded.

## Examples

``` r
if (FALSE) { # \dontrun{
taxonomy_about()
} # }
```
