TweetUrl
===

[![Build Status](https://travis-ci.org/announce/tweet_url.svg?branch=master)](https://travis-ci.org/announce/tweet_url)

## Installation

Add this line to your application's Gemfile:

```ruby
gem 'tweet_url'
```

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install tweet_url

## Usage

Simply,

```rb
require 'tweet_url'

tweet_url = TweetUrl.parse('https://twitter.com/yukihiro_matz/status/755950562227605504')
tweet_url.username  #=> "yukihiro_matz"
tweet_url.status_id  #=> 755950562227605504
```

To handle URL containing multibyte chars, run `gem install addressable` and

```rb
require 'addressable/uri'
require 'tweet_url'

tweet_url = TweetUrl.parse(
  'https://twitter.com/yukihiro_matz/status/755950562227605504#尾骶骨',
  parser: Addressable::URI)
tweet_url.username  #=> "yukihiro_matz"
tweet_url.status_id  #=> 755950562227605504
```
