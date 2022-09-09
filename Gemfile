# frozen_string_literal: true
source "https://rubygems.org"
gemspec

rails_version = ENV["RAILS_VERSION"] == "edge" ? { github: "rails/rails" } : ENV["RAILS_VERSION"]
gem "actionpack", rails_version
gem "activesupport", rails_version

group :development, :test do
  gem "rubocop", "~> 0.82.0"
end
