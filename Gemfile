source ENV['GEM_SOURCE'] || "https://rubygems.org"

def location_for(place)
  if place =~ /^(git[:@][^#]*)#(.*)/
    [{ :git => $1, :branch => $2, :require => false }]
  elsif place =~ /^file:\/\/(.*)/
    ['>= 0', { :path => File.expand_path($1), :require => false }]
  else
    [place, { :require => false }]
  end
end

gem 'vanagon', *location_for(ENV['VANAGON_LOCATION'] || '0.7.1')
gem 'packaging', '~> 0.4', :github => 'charlesdunbar/packaging', :branch => 'cinext'
gem "beaker-hostgenerator", *location_for(ENV['BEAKER_HOSTGENERATOR_VERSION'] || "~> 0.3")

gem 'rake'
gem 'json'
gem 'rubocop', "~> 0.34.2"
gem 'openstack', :git => 'https://github.com/ruby-openstack/ruby-openstack.git', :tag => 'v2.1.0'
