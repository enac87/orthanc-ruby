# Orthanc-ruby

#### A Ruby implementation of the [Orthanc](http://orthanc-server.com) DICOM server v0.8.6 REST API

---

**Alpha!! Not ready for production. Anything may change, including resource nesting and naming schemes.**

---

###Attention: The gem now implements the orthanc resources as multilevel methods, to make it more Ruby-like

_(This is my first API client gem, experienced help or advice would be most appreciated)_ :)


## Installation

**NOTE:** If you need an instance of Orthanc to test against, you can build a ready-to-use Orthanc server VM with the [orthanc-vagrant](https://github.com/chafey/orthanc-vagrant) project.

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
    api.patients # All patients as instances for method chaining
    api.patients_list # Patient array, from Orthanc response
    pat = api.patients.first # First patient (instance)

  pat.shared_tags(simplify:true) # Patient's shared tags (simplified)

    api.system.database_version => 5
    api.statistics.count_studies => 14

You get the picture.

You can see what Orthanc API resources have been mapped in the gem, and their status [here](https://docs.google.com/spreadsheets/d/1KWQHNGS-NEYppo3XW4TkNbZYk_AraPhWOmSwxcsScvU/edit?usp=sharing)

Basic documentation can be found in [here](http://www.rubydoc.info/github/simonmd/orthanc-ruby/master/Orthanc/Client)

## Backlog

 - Methods that return a file should be handled by ruby
 - Test attachments (not sure how they are implemented in Orthanc)
 - Handle network errors, return false if 500 Server error? (eg. echo)
 - Test peers
 - Write automated tests

## Contributing

1. Fork it ( https://github.com/[my-github-username]/orthanc/fork )
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create a new Pull Request

## License

MIT License
