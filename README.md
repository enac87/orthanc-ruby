# Orthanc-ruby

##### A Ruby implementation of the [Orthanc](http://orthanc-server.com) DICOM server v0.8.6 REST API

##### Extremely Alpha!! Not ready for production. Anything may change, including resource nesting and naming schemes.

(This is my first API client gem, experienced help or advice would be most appreciated) :)

## Installation

Add this line to your application's Gemfile:

```ruby
gem 'orthanc'
```

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install orthanc

## Usage
The gem tries to follow the Orthanc API naming scheme as closely as possible, converting methods and response items to snake case to make the experience more ruby-like.

  api=Orthanc::Client.new("localhost", "8042")
  api.all_patients
  api.all_patients.first
  api.system.database_version => 5
  api.statistics.count_studies => 14

You get the picture. 

## Development

After checking out the repo, run `bin/setup` to install dependencies. Then, run `bin/console` for an interactive prompt that will allow you to experiment.

To install this gem onto your local machine, run `bundle exec rake install`. To release a new version, update the version number in `version.rb`, and then run `bundle exec rake release` to create a git tag for the version, push git commits and tags, and push the `.gem` file to [rubygems.org](https://rubygems.org).

## Contributing

1. Fork it ( https://github.com/[my-github-username]/orthanc/fork )
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create a new Pull Request

## License

MIT License