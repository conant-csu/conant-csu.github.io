source "https://rubygems.org"

# Plain jekyll rather than the github-pages meta-gem: the meta-gem's current
# dependency pins (ffi, etc.) require Ruby >= 3.0, but this machine's system
# Ruby is 2.6.10. Jekyll itself is what GitHub Pages runs under the hood;
# this just avoids the meta-gem's extra version-locking layer.
gem "jekyll", "~> 4.3"

gem "webrick"

# Pin: newer ffi (pulled in transitively via jekyll-sass-converter -> sassc)
# requires Ruby >= 3.0; this machine runs system Ruby 2.6.10.
gem "ffi", "< 1.17"
