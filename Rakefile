desc "default task"
task :default => ["hello", "hello.txt"]

desc "echo hello, world"
task "hello" do
  puts "hello, world"
end

#desc "create hello.txt file"
#file "hello.txt" => "hello.md" do |f|
#  sh "cp #{f.source} #{f.name}"
#end

desc "copy markdown file to text file"
rule ".txt" => ".md" do |f|
  sh "cp #{f.source} #{f.name}"
end
