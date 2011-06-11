require 'tempfile'

desc 'list syscalls for an empty file'
task :nothing do
  Tempfile.open('foo.rb') do |tf|
    tf.write ''
    tf.flush
    sh "dtruss ruby #{tf.path} 2> nothing-#{RUBY_VERSION}.log"
  end
end

desc 'list syscalls to require rubygems'
task :rubygems do
  Tempfile.open('foo.rb') do |tf|
    tf.puts "require 'rubygems'"
    tf.flush
    sh "dtruss ruby #{tf.path} 2> rubygems-#{RUBY_VERSION}.log"
  end
end

desc 'list syscalls to require rubygems and nokogiri'
task :nokogiri do
  Tempfile.open('foo.rb') do |tf|
    tf.puts "require 'rubygems'"
    tf.puts "require 'nokogiri'"
    tf.flush
    sh "dtruss ruby #{tf.path} 2> nokogiri-#{RUBY_VERSION}.log"
  end
end
