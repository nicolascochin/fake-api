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
irb
```

```ruby
require 'ffaker'
require 'json'
a = Array.new(30) {|i| {id: i + 1, image: "https://fakeimg.pl/180x40/#{FFaker::Color.hex_code}/", title: FFaker::Lorem.sentence,  content: FFaker::Lorem.paragraphs(5)} }
File.open('db.json', 'w') { |file| file.write(JSON.dump(articles: a))}
```
