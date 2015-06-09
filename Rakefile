    require 'rubygems'
    require 'rake'
    require 'rdoc'
    require 'date'
    require 'yaml'
    require 'tmpdir'
    require 'jekyll'

    desc "Generate blog files"
    task :generate do
      Jekyll::Site.new(Jekyll.configuration({
        "source"      => ".",
        "destination" => "_site"
      })).process
    end


    desc "Generate and publish blog to gh-pages"
    task :publish => [:generate] do
      Dir.mktmpdir do |tmp|
        system "proxychains4 curl https://taoalpha-github-page.appspot.com/query\?id\=ahZzfnRhb2FscGhhLWdpdGh1Yi1wYWdlchULEghBcGlRdWVyeRiAgICAgICACgw > _site/pageview.json"
        system "curl https://api.douban.com/v2/book/user/taoalpha/collections?status=wish&tag=MyWish > _site/doubanbooks.json"
        system "mv _site #{tmp}"
        system "mv _assets/vendors #{tmp}"
        system "git checkout -B gh-pages"
        system "rm -rf *"
        system "mv #{tmp}/_site/* ."
        message = "Site updated at #{Time.now.utc}"
        system "git add ."
        system "git commit -am #{message.shellescape}"
        system "git push origin gh-pages --force"
        system "git checkout master"
        system "mv #{tmp}/vendors ./_assets/"
        system "echo yolo"
        system "cat todo.log"
      end
    end

task :default => :publish
