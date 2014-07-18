desc "Generate jekyll site"
task :gen do
  puts "## Generating Site with Jekyll"
  system "jekyll build --lsi"
end

desc "Deploy to gitcafe/github"
task :deploy do
  puts "### Git push"
  system "git push iftti-gitcafe master:gitcafe-pages"
  system "git push iftti-github master"
end

desc "Preview drafts"
task :drafts_preview do
  system "jekyll serve --drafts --lsi"
end

desc "Preview"
task :preview do
  system "jekyll serve --lsi"
end
