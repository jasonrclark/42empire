require "rubygems"
require "tmpdir"

require "bundler/setup"
require "jekyll"

task :default => [:'site:publish']

namespace :site do
  desc "Generate blog files"
  task :generate do
    Jekyll::Site.new(Jekyll.configuration({
      "source"      => ".",
      "destination" => "_site"
    })).process
  end

  desc "Generate and publish"
  task :publish => [:generate] do
    `scp -rp _site/* jasonrclark@robotlikes.com:/home/jasonrclark/webapps/42empire`
  end
end
