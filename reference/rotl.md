# An Interface to the Open Tree of Life API

The Open Tree of Life is an NSF funded project that is generating an
online, comprehensive phylogenetic tree for 1.8 million species. `rotl`
provides an interface that allows you to query and retrieve the parts of
the tree of life that is of interest to you.

## Details

`rotl` provides function to most of the end points the API provides. The
documentation of the API is available at:
<https://github.com/OpenTreeOfLife/opentree/wiki/Open-Tree-of-Life-APIs>

## Customizing API calls

All functions that use API end points can take 2 arguments to customize
the API call and are passed as `...` arguments.

- `otl_v`:

  This argument controls which version of the API your call is using.
  The default value for this argument is a call to the non-exported
  function `otl_version()` which returns the current version of the Open
  Tree of Life APIs (v2).

- `dev_url`:

  This argument controls whether to use the development version of the
  API. By default, `dev_url` is set to `FALSE`, using `dev_url = TRUE`
  in your function calls will use the development version.

For example, to use the development version of the API, you could use:
`tnrs_match_names("anas", dev_url=TRUE)`

Additional arguments can also be passed to the
[`GET`](https://httr.r-lib.org/reference/GET.html) and
[`POST`](https://httr.r-lib.org/reference/POST.html) methods.

## Acknowledgments

This package was started during the Open Tree of Life Hackathon
organized by the OpenTree of Life, the NESCent Hackathon
Interoperability Phylogenetic group, and Arbor.

## See also

Useful links:

- <https://docs.ropensci.org/rotl/>

- <https://github.com/ropensci/rotl>

- Report bugs at <https://github.com/ropensci/rotl/issues>

## Author

**Maintainer**: Francois Michonneau <francois.michonneau@gmail.com>
([ORCID](https://orcid.org/0000-0002-9092-966X))

Authors:

- Joseph Brown ([ORCID](https://orcid.org/0000-0002-3835-8062))

- David Winter ([ORCID](https://orcid.org/0000-0002-6165-0029))

Other contributors:

- Scott Chamberlain ([ORCID](https://orcid.org/0000-0003-1444-9135))
  \[reviewer\]
