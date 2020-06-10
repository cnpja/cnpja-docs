# gem uninstall eventmachine; 3; y; gem install eventmachine --platform ruby
# bundle exec jekyll serve --livereload

source "https://rubygems.org"

gem "github-pages", "~> 204", group: :jekyll_plugins

# Add performance booster and zone info for Windows
install_if -> { RUBY_PLATFORM =~ %r!mingw|mswin|java! } do
  gem "tzinfo", "~> 1.2"
  gem "tzinfo-data"
end

gem "wdm", "~> 0.1.1", :install_if => Gem.win_platform?
