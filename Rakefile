require "rake/testtask"
require 'find'
require "bundler/gem_tasks"

desc 'Say hello'
task :hello do
  puts "Hello there. This is the 'hello' task."
end

desc 'Run tests'
task :test do
  sh 'ruby ./test/todolist_project_test.rb'
end

desc 'Run tests'
task :default => :test

desc 'Print files that do not start with .'
task :inventory do 
  Find.find(".") do |path|
    if !path.start_with?('./.') && File.file?(path)
      puts path[2..-1]
    end
  end
end

Rake::TestTask.new(:test) do |t|
  t.libs << "test"
  t.libs << "lib"
  t.test_files = FileList['test/**/*_test.rb']
end