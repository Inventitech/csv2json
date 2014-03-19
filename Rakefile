require 'rubygems'
require 'rake'
require File.join(File.expand_path(File.dirname(__FILE__)), 'lib', 'csv2json-version.rb')

begin
  require 'jeweler'
  Jeweler::Tasks.new do |gem|
    gem.version = CSV2JSON::VERSION
    gem.name = "csv2json"
    gem.summary = %Q{.csv to .json converter}
    gem.description = %Q{handy for converting xls files to json}
    gem.email = "antonin@hildebrand.cz"
    gem.homepage = "http://github.com/darwin/csv2json"
    gem.authors = ["Antonin Hildebrand", "Rafael Souza"]
    gem.add_dependency "json"
    gem.add_development_dependency "shoulda", ">= 0"
    # gem is a Gem::Specification... see http://www.rubygems.org/read/chapter/20 for additional settings
  end
  Jeweler::GemcutterTasks.new
rescue LoadError
  puts "Jeweler (or a dependency) not available. Install it with: gem install jeweler"
end

require 'rake/testtask'
Rake::TestTask.new(:test) do |test|
  test.libs << 'lib' << 'test'
  test.pattern = 'test/**/test_*.rb'
  test.verbose = true
end

begin
  require 'rcov/rcovtask'
  Rcov::RcovTask.new do |test|
    test.libs << 'test'
    test.pattern = 'test/**/test_*.rb'
    test.verbose = true
  end
rescue LoadError
  task :rcov do
    abort "RCov is not available. In order to run rcov, you must: sudo gem install spicycode-rcov"
  end
end

task :test => :check_dependencies

task :default => :test

require 'rdoc/task'
Rake::RDocTask.new do |rdoc|
  version = File.exist?('VERSION') ? File.read('VERSION') : ""

  rdoc.rdoc_dir = 'rdoc'
  rdoc.title = "csv2json #{version}"
  rdoc.rdoc_files.include('README*')
  rdoc.rdoc_files.include('lib/**/*.rb')
end
