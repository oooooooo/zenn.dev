---
title: "ファイル"
free: false
---

## 文字列を frozen する

rubocop -A で追加してくれる。

```ruby
# frozen_string_literal: true
```

- [Ruby: What does the comment "frozen_string_literal: true" do? - Stack Overflow](https://stackoverflow.com/questions/37799296/ruby-what-does-the-comment-frozen-string-literal-true-do)

## ファイルを一気に読む
```ruby
file = File.open(filename).read
```

## JSON を POST
```ruby
require 'json'
require 'net/http'

def json_post(url, params)
  uri = URI.parse(url)
  http = Net::HTTP.new(uri.host, uri.port)
  http.use_ssl = uri.scheme == 'https'

  headers = { 'Content-Type' => 'application/json' }
  http.post(url, params.to_json, headers)
end

url = 'https://api.example.com'
params = { foo: 'bar' }
response = json_post(url, params)
p response.code
p response.body
```

