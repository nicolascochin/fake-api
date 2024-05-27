# Fake API

URL: https://fake-api-codecloud.vercel.app

API: https://fake-api-codecloud.vercel.app/articles

## Run Locally

Clone the project

```bash
  git clone https://github.com/nicolascochin/fake-api
```

Go to the project directory

```bash
  cd fake-api
```

Install dependencies

```bash
  npm install
```

Start the server

```bash
  npm start
```

## Generate db.json file

```bash
podman run -it -v ${PWD}:${PWD}:Z -w ${PWD} ruby:3.3-alpine sh
gem install ffaker
gem install actionview
irb
```

```ruby
require 'ffaker'
require 'json'
require 'action_view'
include ActionView::Helpers::TagHelper

a = Array.new(30) {|i| {id: i + 1, heroImage: "https://fakeimg.pl/1020x510/#{FFaker::Color.hex_code}/", title: FFaker::Lorem.words((2..4).to_a.sample).join(' '), description: FFaker::Lorem.words((7..10).to_a.sample).join(' '), publicationDate:

irb(main):022> FFaker::Date.backward, content: FFaker::Lorem.paragraphs((5..10).to_a.sample).map {|p| tag.p(p)}.join('')} }

File.open('db.json', 'w') { |file| file.write(JSON.dump(articles: a))}
```
