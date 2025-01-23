require "rake/testtask"
require "find"

desc 'Say hello'
task :hello do
  puts "Hello there. This is the 'hello' task."
end

#desc 'Run tests'
#task :test do
#  sh 'ruby ./test/todolist_project_test.rb'
#end

desc 'default Run tests'
task :default => :test1

Rake::TestTask.new(:test1) do |t|
  t.libs << "test"
  t.libs << "lib"
  t.test_files = FileList['test/**/*_test.rb']
end

desc 'Show files'
task :file_list do
  puts Rake::FileList['**/*'].select { |place| File.file?(place) }
end

desc 'Display inventory of all files'
task :inventory do
  Find.find('.') do |name|
    next if name.include?('/.')
    puts name if File.file?(name)
  end
end