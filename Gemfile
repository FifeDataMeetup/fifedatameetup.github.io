source "https://rubygems.org"

# Use the same Jekyll version and plugins as GitHub Pages.
# To upgrade, run `bundle update github-pages`.
gem "github-pages", group: :jekyll_plugins

# Needed to run `jekyll serve` on Ruby 3.x
gem "webrick"
gem "csv"
gem "base64"
gem "bigdecimal"

# Windows and JRuby do not include zoneinfo files
platforms :mingw, :x64_mingw, :mswin, :jruby do
  gem "tzinfo", ">= 1", "< 3"
  gem "tzinfo-data"
end
