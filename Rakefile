require "rake/testtask"
require "bundler/gem_tasks"

desc 'Say hello'
task :hello do
  puts "Hello there. This is the 'hello' task."
end

desc 'Run tests'
task :default => :test

desc "Files that don't start with '.'"
task :inventory do
  require 'find'
  Find.find('.') do |name|
    next if name.include?('/.')
    puts name if File.file?(name)
  end
end

Rake::TestTask.new(:test) do |t|
  t.libs << "test"
  t.libs << "lib"
  t.test_files = FileList['test/**/*_test.rb']
end