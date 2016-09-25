## DarkSky.net Wrapper

This is a wrapper for the darksky.net API. You need an API key to
use it (https://darksky.net/dev/). Please consult the API docs at
https://darksky.net/dev/.


## Example Use


```perl
use 5.016;
use DarkSky::API;
use Data::Dumper;

my $lat  = 43.6667;
my $long = -79.4167;
my $key = "c9ce1c59d139c3dc62961cbd63097d13"; # example DarkSky.net API key

my $forecast = DarkSky::API->new(
    key       => $key,
    longitude => $long,
    latitude  => $lat,
);

say "current temperature: " . $forecast->{currently}->{temperature};

my @daily_data_points = @{ $forecast->{daily}->{data} };

# Use your imagination about how to use this data.
# in the meantime, inspect it by dumping it.
for (@daily_data_points) {
    print Dumper($_);
}
```

## Links

Patches/suggestions welcome

Github: https://github.com/mlbright/DarkSky-API

CPAN: coming soon