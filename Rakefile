require "rake/testtask"
require 'find'

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

desc 'Run files except those that start with .'
task :run_specific_files do 
  Find.find("../todolist_project") do |path|
    puts path
    if !path.start_with?('.')
      puts path if path.file?
    end
  end
end

Rake::TestTask.new(:test) do |t|
  t.libs << "test"
  t.libs << "lib"
  t.test_files = FileList['test/**/*_test.rb']
end