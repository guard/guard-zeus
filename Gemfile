source 'http://rubygems.org'

# Specify your gem's dependencies in guard-spin.gemspec
gemspec

group :development do
  gem 'guard-bundler', '~> 2.0'
  gem 'guard-rspec', '~> 4.3'
  gem 'guard-rubocop'
  gem 'rubocop'
end

group :test do
  gem 'rake'
  gem 'rspec', '~> 3.1'
end

if RbConfig::CONFIG['target_os'] =~ /darwin/i
  gem 'growl', require: false
end
if RbConfig::CONFIG['target_os'] =~ /linux/i
  gem 'libnotify', '~> 0.9.1', require: false
end
