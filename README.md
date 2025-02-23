
<!-- README.md is generated from README.Rmd. Please edit that file -->

[![Travis build
status](https://travis-ci.org/SamanthaToet/yelpr.svg?branch=master)](https://travis-ci.org/SamanthaToet/yelpr)

# yelpr

R client for accessing the [Yelp Fusion
API](https://www.yelp.com/developers/documentation/v3).

## Installation

You can install the in-development version from GitHub using the
`remotes` package.

``` r
install.packages("devtools")
remotes::install_github("SamanthaToet/yelpr")
```

If you encounter a bug, have usage questions, or want to share ideas to
make this package better, feel free to file an
[issue](https://github.com/SamanthaToet/yelpr/issues).

## Connecting to Yelp

To interface with the Yelp API, you’ll need to register a [Yelp
Developer account](https://www.yelp.com/developers) and then [create an
app](https://www.yelp.com/developers/v3/manage_app). Your app will auto
generate a `Client ID` and `API Key`. Copy the value for the `API Key`
and save that value in your keyring by running the below code:

``` r
keyring::key_set("yelp")
```

You will be promped to paste your `API Key` in a separate password
window.

## Connecting to Google Maps

To interface with the Google Maps API, you’ll need to enable the [Google
Maps Platform](https://cloud.google.com/maps-platform/). Once you enable
the services, copy your `API Key` from the popup window and save that
value in your keyring by running the below code:

``` r
keyring::key_set("google_maps_api")
```

Once your google maps API key is stored, you need to tell `yelpr` about
your key. Run the below code to register your key:

``` r
register_google(keyring::key_get("google_maps_api"))
```

## Example

Get a list of all the restaurants that have chicken wings in
Charlottesville, VA:

``` r
get_yelp_search_data("chicken wings", "Charlottesville, VA")
```

## Code of Conduct

Please note that this project is released with a [Contributor Code of
Conduct](https://github.com/SamanthaToet/yelpr/blob/master/CODE_OF_CONDUCT.md).
By participating in this project you agree to abide by its terms.

## License

MIT © Samantha Toet
