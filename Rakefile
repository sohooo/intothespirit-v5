
require 'nanoc3/tasks'
require 'fileutils'
require 'pathname'

namespace :purge do

  desc "delete teaser thumbnails (featured and thumbnail)"
  task :thumbs do
    teaser_root = Pathname.new "static/assets/images/teaser"

    # original_path  = teaser_root + "original"
    featured_path  = teaser_root + "featured"
    thumbnail_path = teaser_root + "thumbnail"

    [featured_path, thumbnail_path].each do |path|
      path.children.each do |image|
        image.delete
        puts "[del] " + image.to_path
      end
    end
  end

end

desc "Creates a new page"
task :new do
  require 'active_support/core_ext'
  require 'active_support/multibyte'
  @ymd = Time.now.to_s(:db).split(' ')[0]

  path  = Pathname.new ARGV[1]
  title = path.basename.to_s.gsub(path.extname, "")

  unless path.to_path =~ /^content/
    $stderr.puts "\t[error] Wrong path argument.\n\tusage: rake new content/title.md"
    exit 1
  end

  if File.exists?(path)
    $stderr.puts "\t[error] Exists #{path}"
    exit 1
  end

    template = <<TEMPLATE
---
created_at: #{@ymd}
excerpt: 
kind: article
publish: true
tags: [misc]
excerpt:
title: "#{title.titleize}"
---

TODO: Add content to `#{path}.`
TEMPLATE

  page_dir = path.dirname
  FileUtils.mkdir_p(page_dir) if !File.exists?(page_dir)
  File.open(path, 'w') { |f| f.write(template) }
  $stdout.puts "\t[ok] Edit #{path}"
end


namespace :create do

  desc "Creates a new article"
  task :article do
    $KCODE = 'UTF8'
    require 'active_support/core_ext'
    require 'active_support/multibyte'
    @ymd = Time.now.to_s(:db).split(' ')[0]
    if !ENV['title']
      $stderr.puts "\t[error] Missing title argument.\n\tusage: rake create:article title='article title'"
      exit 1
    end

    title = ENV['title'].capitalize
    path, filename, full_path = calc_path(title)

    if File.exists?(full_path)
      $stderr.puts "\t[error] Exists #{full_path}"
      exit 1
    end

    template = <<TEMPLATE
---
created_at: #{@ymd}
excerpt: 
kind: article
publish: true
tags: [misc]
title: "#{title.titleize}"
---

TODO: Add content to `#{full_path}.`
TEMPLATE

    FileUtils.mkdir_p(path) if !File.exists?(path)
    File.open(full_path, 'w') { |f| f.write(template) }
    $stdout.puts "\t[ok] Edit #{full_path}"
  end

  def calc_path(title)
    year, month_day = @ymd.split('-', 2)
    path = "content/" + year + "/" 
    filename = month_day + "-" + title.parameterize('_') + ".md"
    [path, filename, path + filename]
  end
end


