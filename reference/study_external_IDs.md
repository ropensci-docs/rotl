# Get external identifiers for data associated with an Open Tree study

Data associated with studies contributing to the Open Tree synthesis may
be available from other databases. In particular, trees and alignments
may be available from treebase and DNA sequences and bibliographic
information associated with a given study may be available from the
NCBI. This function retrieves that information for a given study.

## Usage

``` r
study_external_IDs(study_id)
```

## Arguments

- study_id:

  An open tree study ID

## Value

A study_external_data object (which inherits from a list) which contains
some of the following.

doi, character, the DOI for the paper describing this study

external_data_url, character, a URL to an external data repository (e.g.
a treebase entry) if one exists.

pubmed_id character, the unique ID for this study in the NCBI's pubmed
database

popset_ids character, vector of IDs for the NCBI's popset database

nucleotide_ids character, vector of IDs for the NCBI's nucleotide
database

## See also

studies_find_studies (used to discover study IDs)

## Examples

``` r
if (FALSE) { # \dontrun{
flies <- studies_find_studies(property="ot:focalCladeOTTTaxonName", value="Drosophilidae")
study_external_IDs(flies[2,]$study_ids)
} # }
```
