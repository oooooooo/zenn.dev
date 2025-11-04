---
title: "CSV"
free: false
---

## 書き出し

```ruby
CSV.open(filename, 'w') do |csv|
  csv << []
end
```

## 読み込み

```ruby
CSV.foreach(filename) do |row|
end
```