require 'rubygems'
require 'rake/gempackagetask'
<<<<<<< HEAD:Rakefile
require 'rubygems/specification'
require 'date'
require 'spec/rake/spectask'
require 'tasks/redis.tasks'


GEM = 'redis'
GEM_VERSION = '0.0.3'
AUTHORS = ['Ezra Zygmuntowicz', 'Taylor Weibley']
EMAIL = "ez@engineyard.com"
HOMEPAGE = "http://github.com/ezmobius/redis-rb"
SUMMARY = "Ruby client library for redis key value storage server"

spec = Gem::Specification.new do |s|
  s.name = GEM
  s.version = GEM_VERSION
  s.platform = Gem::Platform::RUBY
  s.has_rdoc = true
  s.extra_rdoc_files = ["LICENSE"]
  s.summary = SUMMARY
  s.description = s.summary
  s.authors = AUTHORS
  s.email = EMAIL
  s.homepage = HOMEPAGE
  
  # Uncomment this to add a dependency
  # s.add_dependency "foo"
  
  s.require_path = 'lib'
  s.autorequire = GEM
  s.files = %w(LICENSE README.markdown Rakefile) + Dir.glob("{lib,spec}/**/*")
end

task :default => :spec

desc "Run specs"
Spec::Rake::SpecTask.new do |t|
  t.spec_files = FileList['spec/**/*_spec.rb']
  t.spec_opts = %w(-fs --color)
=======
require "spec/rake/spectask"
begin; require 'rubygems'; rescue LoadError; end
begin
  require 'hanna/rdoctask'
rescue LoadError
  require 'rake/rdoctask'
end
require 'rake/clean'

GEM = "nanite"
VER = "0.4.0"
AUTHOR = "Ezra Zygmuntowicz"
EMAIL = "ezra@engineyard.com"
HOMEPAGE = "http://github.com/ezmobius/nanite"
SUMMARY = "self assembling fabric of ruby daemons"

Dir.glob('tasks/*.rake').each { |r| Rake.application.add_import r }

spec = Gem::Specification.new do |s|
  s.name = GEM
  s.version = ::VER
  s.platform = Gem::Platform::RUBY
  s.has_rdoc = true
  s.extra_rdoc_files = ["README.rdoc", "LICENSE", 'TODO']
  s.summary = SUMMARY
  s.description = s.summary
  s.author = AUTHOR
  s.email = EMAIL
  s.homepage = HOMEPAGE

  s.bindir       = "bin"
  s.executables  = %w( nanite-agent nanite-mapper nanite-admin )

  s.add_dependency('amqp', '>= 0.6.0')

  s.require_path = 'lib'
  s.files = %w(LICENSE README.rdoc Rakefile TODO) + Dir.glob("{lib,bin,specs}/**/*")
>>>>>>> e7751e617bc246e33c3ef259b123e7981011d119:Rakefile
end

Rake::GemPackageTask.new(spec) do |pkg|
  pkg.gem_spec = spec
end

<<<<<<< HEAD:Rakefile
desc "install the gem locally"
task :install => [:package] do
  sh %{sudo gem install pkg/#{GEM}-#{GEM_VERSION}}
end

desc "create a gemspec file"
task :make_spec do
  File.open("#{GEM}.gemspec", "w") do |file|
    file.puts spec.to_ruby
  end
end
=======
task :install => [:package] do
  sh %{sudo gem install pkg/#{GEM}-#{VER}}
end

desc "Run unit specs"
Spec::Rake::SpecTask.new do |t|
  t.spec_opts = ["--format", "specdoc", "--colour"]
  t.spec_files = FileList["spec/**/*_spec.rb"]
end

desc 'Generate RDoc documentation'
Rake::RDocTask.new do |rd|
  rd.title = spec.name
  rd.rdoc_dir = 'rdoc'
  rd.main = "README.rdoc"
  rd.rdoc_files.include("lib/**/*.rb", *spec.extra_rdoc_files)
end
CLOBBER.include(:clobber_rdoc)

desc 'Generate and open documentation'
task :docs => :rdoc do
  case RUBY_PLATFORM
  when /darwin/       ; sh 'open rdoc/index.html'
  when /mswin|mingw/  ; sh 'start rdoc\index.html'
  else 
    sh 'firefox rdoc/index.html'
  end
end
>>>>>>> e7751e617bc246e33c3ef259b123e7981011d119:Rakefile
