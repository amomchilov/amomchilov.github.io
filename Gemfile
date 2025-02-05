source "https://rubygems.org"

group :jekyll_plugins do
  # Locks the exact versions of Jekyll used by GitHub pages
  # https://github.com/github/pages-gem/blob/master/lib/github-pages/dependencies.rb
  gem "github-pages"
end

gem "minima", "~> 2.5" # Jekyll's default theme

# Windows and JRuby does not include zoneinfo files, so bundle the tzinfo-data gem
# and associated library.
platforms :mingw, :x64_mingw, :mswin, :jruby do
  gem "tzinfo", ">= 1", "< 3"
  gem "tzinfo-data"
end

# Performance-booster for watching directories on Windows
gem "wdm", "~> 0.1", :platforms => [:mingw, :x64_mingw, :mswin]

# Lock `http_parser.rb` gem to `v0.6.x` on JRuby builds since newer versions of the gem
# do not have a Java counterpart.
gem "http_parser.rb", "~> 0.6.0", :platforms => [:jruby]
