desc "Build the site"
task :build_site do
  sh "bower install"
  sh "bundle install"
  sh "bundle exec middleman build"
end

desc "Deploy to GitHub pages"
task :deploy => [:build_site] do
  sh "git checkout master"
  sh "ls | grep -v 'build' | xargs rm -rf"
  sh "mv build/* ."
  sh "rm -rf build/"
  sh "git add ."
  sh "git commit -m \"Deploy to GitHub\""
  sh "git push origin master"
  sh "git checkout source"
end