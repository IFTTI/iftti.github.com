desc "Generate jekyll site"
task :gen do
  raise "### Site Dir(_site/) not found!" unless File.directory?("./_site")

  puts "### Clear _site/"
  system "cd ./_site && git rm -q -r -f ./"

  puts "## Generating Site with Jekyll"
  system "jekyll build --lsi"

  puts "### Git commit"
  system "cd ./_site && git add . && git diff HEAD; git commit -a"
end

desc "Deploy to gitcafe/github"
task :deploy do
  puts "### Git push"
  system "cd _site && git push iftti-gitcafe master:gitcafe-pages"
  system "cd _site && git push iftti-github master"
end

desc "Sync"
task :sync do
  puts "Sync"
  system "./_crawler/site_crawler.rb"
end

desc "Drafts"
task :drafts do
  puts "### cd _drafts; git commit"
  system "git add _drafts && git commit -am 'Update _drafts at #{Time.now}'"
end

desc "Commit RAW"
task :raw do
  puts "### cd _raw; Git commit"
  system "cd _raw && git add . && git commit -am 'Update at #{Time.now}' && git push origin raw"
end
task :add_raw do
  system "git add _raw"
end

desc "Push"
task :push do
  puts "Push"
  system "git push origin master"
end

desc "Pull"
task :pull do
  puts "Pull"
  system "git pull origin master"
end

desc "RAW, Drafts, Push"
task :raw_drafts_push => [:raw, :add_raw, :drafts, :push] do
end

desc "Preview drafts"
task :drafts_preview do
  system "jekyll serve --drafts --lsi"
end

desc "Preview"
task :preview do
  system "jekyll serve --lsi"
end
