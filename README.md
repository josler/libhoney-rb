# libhoney [![Build Status](https://travis-ci.org/honeycombio/libhoney-rb.svg?branch=master)](https://travis-ci.org/honeycombio/libhoney-rb)

Ruby gem for sending events to [Honeycomb](https://honeycomb.io). (See here for more information about [using Honeycomb](https://honeycomb.io/intro/) and [its libraries](https://honeycomb.io/docs/send-data/sdks).)

## Installation

To install the stable release:

```
gem install libhoney
```

If you're using bundler, you can also reference the git repo and stay on the bleeding age by putting this in your `Gemfile`:

```
gem 'libhoney', :git => 'http://github.com/honeycombio/libhoney-rb.git'
```

## Example Usage

Honeycomb can calculate all sorts of statistics, so send the values you care about and let us crunch the averages, percentiles, lower/upper bounds, cardinality -- whatever you want -- for you.

```ruby
require 'libhoney'

# Create a client instance
honeycomb = Libhoney::Client.new(:writekey => "YOUR_WRITE_KEY",
                                 :dataset => "honeycomb-ruby-example")

honeycomb.send_now({
  duration_ms: 153.12,
  method: "get",
  hostname: "appserver15",
  payload_length: 27
})

# Call close to flush any pending calls to Honeycomb
honeycomb.close
```

You can find a more complete example demonstrating usage in [`example/fact.rb`](example/fact.rb)

## Contributions

Features, bug fixes and other changes to libhoney are gladly accepted. Please
open issues or a pull request with your change. Remember to add your name to the
CONTRIBUTORS file!

All contributions will be released under the Apache License 2.0.

