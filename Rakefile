# frozen_string_literal: true
require "rake/testtask"
require "rubocop/rake_task"
require "bundler/gem_tasks"

task default: [:test, :rubocop]

Rake::TestTask.new(:test) do |t|
  t.ruby_opts = ["-W0", "-W:deprecated"]
  t.libs << "test"
  t.libs << "lib"
  t.test_files = FileList["test/**/test_*.rb"]
end

RuboCop::RakeTask.new
