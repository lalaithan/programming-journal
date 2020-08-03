# Programming Journal

---

## August 3, 2020

### Ruby

#### CodeWars Kata

> Complete the function so that it takes an array of keys and a default value and returns a hash (Ruby) / dictionary (Python) with all keys set to the default value.

##### Tried

* [ ]

```ruby
new_hash.default = default_value
```

* [ ]

```ruby
new_hash = Hash.new(default_value)
```

* [ ]

```ruby
    new_hash = Hash.new(default_value)
    keys.each {|key| new_hash}
    return new_hash
```

##### Final Working Solution

* [x]

```ruby
    def solution(keys, default_value)
        new_hash = Hash.new(default_value)
        keys.each {|key| new_hash.store(key, default_value)}
        return new_hash
    end
```
