ROOT_DIR = File.expand_path(File.dirname(__FILE__))

require 'rubygems' rescue nil
require 'rake'
require 'rspec/core/rake_task'

task :default => :spec

desc "Run all specs in spec directory."
RSpec::Core::RakeTask.new(:spec) do |t|
  t.rspec_opts = ['--options', "\"#{ROOT_DIR}/spec/spec.opts\""]
end

desc "Run benchmarks"
RSpec::Core::RakeTask.new(:benchmark) do |t|
  t.rspec_opts = ['--options', "\"#{ROOT_DIR}/spec/spec.opts\""]
  t.pattern = 'spec/*_benchmark.rb'
end

# gemification with jeweler
begin
  require 'jeweler'
  Jeweler::Tasks.new do |gemspec|
    gemspec.name = "kestrel-client"
    gemspec.summary = "Ruby Kestrel client"
    gemspec.description = "Ruby client for the Kestrel queue server"
    gemspec.email = "rael@twitter.com"
    gemspec.homepage = "http://github.com/freels/kestrel-client"
    gemspec.authors = ["Matt Freels", "Rael Dornfest"]
    gemspec.add_dependency 'memcached', '>= 0.19.6'
  end
  Jeweler::GemcutterTasks.new
rescue LoadError
  puts "Jeweler not available. Install it with: gem install jeweler"
end
