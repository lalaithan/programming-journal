# Programming Journal

*“[B]y their competence in secular fields and by their personal activity, elevated from within by the grace of Christ, let them work vigorously so that by human labor, technical skill and civil culture, created goods may be perfected according to the design of the Creator and the light of his word.” – St. John Paul II*

* [August 7, 2020 (Ruby - AAO)](#august-7-2020)
* [August 6, 2020 (Ruby - AAO)](#august-6-2020)
* [August 5, 2020 (Ruby - AAO)](#august-5-2020)
* [August 4, 2020 (Ruby - CW)](#august-4-2020)
* [August 4, 2020 (Ruby - CW)](#august-3-2020)
* [Resources I Use & Profiles](#resources--profiles)

---

## August 7, 2020

### Ruby

#### App Academy Open - Intro to Programming > Advanced Problems > Prime Factors

>Write a method `prime_factors` that takes in a number and returns an array containing all of the prime factors of the given number.

##### Final Working Solution

First, I initialize an empty array called `factors` to hold the prime factors of the input (`num`). Then I decide to use the previously created `prime?` method to determine if an input is prime already and extend it to return the input if `true`.

---

## August 6, 2020

### Ruby

#### App Academy Open - Intro to Programming > Advanced Problems > Pick Primes

>Write a method `pick_primes` that takes in an array of numbers and returns a new array containing only the prime numbers.

##### Final Working Solution

In the method `pick_primes`, I used `select` on the inputed array in conjunction with a second method that I borrowed from a previous problem called `prime?`.

---

## August 5, 2020

### Ruby

#### App Academy Open - Intro to Programming > Advanced Problems > Most Vowels

>Write a method `most_vowels` that takes in a sentence string and returns the word of the sentence that contains the most vowels.

##### Final Working Solution

In the `most_vowels` method, initialize hash named `tally`. Use `split` to create an array of words from the input `sentence`, then iterate through array. Place each element as `word` into the hash `tally` while sending each `word` to a second method named `count_vowels`. In the second method, initialize `vowel_counter` with a `0` and a container variable with the `vowels`. Using the `count` method, return the integer to be stored with the `word` as a key, value pair in the `tally` hash in the original `most_vowels` method. Finally, using chained `keys` and `max` methods, return the `word` that contains the most vowels.

#### App Academy Open - Intro to Programming > Advanced Problems > Prime

>Write a method `prime?` that takes in a number and returns a boolean, indicating whether the number is prime. A prime number is only divisible by 1 and itself.

##### Final Working Solution

The given method's name prevents just using Ruby's `prime?()` as the solution because it will create an infinite recursion. Since 1 and 2 are prime numbers, use an `if` statement that will return `false` if `num` (input) is below 2. To determine if any other value is prime, enumerate between 2 and the value of `num` exclusive (using `...`) setting each number as `factor`. Use an `if` statement to return `false` if dividing between `num` and `factor` equals 0. Include `return true` at the end of the method for values that don't meet previous tests, signifying they are prime numbers.

---

## August 4, 2020

### Ruby

#### CodeWars Kata #1

> Given a year, return the century it is in.

##### Final Working Solution

Divide input by 100.0. Use `ceil` on quotient and return result.

#### TIL

* The keyword `return` isn't needed when creating methods in Ruby! The last statement that was evaluated in the body of the method is returned by default. If needed, `return` can be used to return from a method earliy.

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

## Resources & Profiles

* [P1xt's Computer Science and Programming Guide](https://github.com/P1xt/p1xt-guides)
* [App Academy Open](https://open.appacademy.io/)
* [DevDocs](https://devdocs.io/)
* [CodeWars](https://www.codewars.com/)
  * [MY CodeWars Profile](https://www.codewars.com/users/lalaithan)
* [Khan Academy Math](https://www.khanacademy.org/)
