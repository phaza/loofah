require 'rubygems'
require 'rake'

begin
  require 'jeweler'
  Jeweler::Tasks.new do |gem|
    gem.name = "loofah"
    gem.summary = %Q{HTML/XML manipulation and sanitization based on Nokogiri}
    gem.description = %Q{HTML/XML manipulation and sanitization based on Nokogiri}
    gem.email = ["mike.dalessio@gmail.com", "bryan@brynary.com"]
    gem.homepage = "http://loofah.rubyforge.org/"
    gem.authors = ["Mike Dalessio", "Bryan Helmkamp"]
    gem.add_dependency "nokogiri", ">= 1.3.3"
    gem.add_development_dependency "mocha", ">= 0.9"
    gem.add_development_dependency "thoughtbot-shoulda", ">= 2.10"
    gem.add_development_dependency "acts_as_fu", ">= 0.0.5"
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

require 'rake/rdoctask'
Rake::RDocTask.new do |rdoc|
  version = File.exist?('VERSION') ? File.read('VERSION') : ""

  rdoc.rdoc_dir = 'rdoc'
  rdoc.title = "loofah #{version}"
  rdoc.rdoc_files.include('README*')
  rdoc.rdoc_files.include('lib/**/*.rb')
end
