require 'bundler'
require 'rake/testtask'

Bundler.require

Rake::TestTask.new do |test|
  require 'coveralls'
  Coveralls.wear!
  SimpleCov.command_name 'Unit Tests'

  if defined?(::Rails::Railtie)
    test.test_files = FileList['test/*_test.rb']
  else
    test.test_files = %w(test/jbuilder_template_test.rb test/jbuilder_test.rb)
  end
end

task :default => :test
