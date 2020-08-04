# Programming Journal

---

## August 4, 2020

### Ruby

#### CodeWars Kata #1

> Given a year, return the century it is in.

#### Final Working Solution

Divide input by 100.0. Use `ceil` on quotient and return result.

---

## August 3, 2020

### Ruby

#### CodeWars Kata #1

> Complete the function so that it takes an array of keys and a default value and returns a hash (Ruby) / dictionary (Python) with all keys set to the default value.

##### Unsuccessful Attempts

Unintentonally left off the *whole* solution in these.

```ruby
new_hash.default = default_value
```

```ruby
new_hash = Hash.new(default_value)
```


```ruby
new_hash = Hash.new(default_value)
keys.each {|key| new_hash}
return new_hash
```

##### Final Working Solution

```ruby
    def solution(keys, default_value)
        new_hash = Hash.new(default_value)
        keys.each {|key| new_hash.store(key, default_value)}
        return new_hash
    end
```

#### CodeWars Kata #2

> In this simple assignment you are given a number and have to make it negative. But maybe the number is already negative?

##### Final Working Solution

Used `?:` conditional ternary operator.

---

## Resources I Use

* [P1xt's Computer Science and Programming Guide](https://github.com/P1xt/p1xt-guides)
* [App Academy Open](https://open.appacademy.io/)
* [DevDocs](https://devdocs.io/)
* [Code Wars](https://www.codewars.com/)
* [Khan Academy Math](https://www.khanacademy.org/)
