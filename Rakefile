require 'rake'

DIR = "./files"
directory DIR

desc "default task"
task :default => ["hello", DIR, "hello.txt", :filelist]

desc "echo hello, world"
task "hello" do
  puts "hello, world"
end

#desc "create hello.txt file"
#file "hello.txt" => "hello.md" do |f|
#  sh "cp #{f.source} #{f.name}"
#end


desc "copy markdown file to text file"
rule ".txt" => [".md", DIR] do |f|
  cp f.source, "#{DIR}/#{f.name}"
end

desc "display file list"
task :filelist do
  FILES = Rake::FileList.new("*", ".*") do |fl|
    fl.exclude(/^\.+$/)
  end
  puts FILES.pathmap("%X")
end

