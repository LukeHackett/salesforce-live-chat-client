require 'yard'
require 'rspec/core/rake_task'


task default: %w(clean test)

desc 'Removes all non-essential project files and folders'
task :clean do
  FileUtils.rm_rf 'coverage'
  FileUtils.rm_rf '.yardoc'
  FileUtils.rm_rf 'doc'
end

desc 'Generates the project documentation'
YARD::Rake::YardocTask.new do |task|
  task.files   = ['lib/**/*.rb']
end

desc 'Runs the entire test suite'
RSpec::Core::RakeTask.new(:test) do |spec|
  spec.pattern = FileList['spec/*/*.rb']
end
