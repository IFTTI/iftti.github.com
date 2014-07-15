desc "Generate jekyll site"
task :gen do
  puts "## Generating Site with Jekyll"
  system "jekyll build --lsi"
end

desc "Deploy to github/gitcafe"
task :deploy do
  puts "### Git push"
  system "git push origin master"
  system "git push gitcafe master:gitcafe-pages"
end

desc "Preview drafts"
task :drafts_preview do
  system "jekyll serve --drafts --lsi"
end

desc "Preview"
task :preview do
  system "jekyll serve --lsi"
end
