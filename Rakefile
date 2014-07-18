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

desc "Preview drafts"
task :drafts_preview do
  system "jekyll serve --drafts --lsi"
end

desc "Preview"
task :preview do
  system "jekyll serve --lsi"
end
