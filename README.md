# Programming Journal

*“[B]y their competence in secular fields and by their personal activity, elevated from within by the grace of Christ, let them work vigorously so that by human labor, technical skill and civil culture, created goods may be perfected according to the design of the Creator and the light of his word.” – St. John Paul II*

* [Resources I Use & Profiles](#resources--profiles)
* [August 8, 2020 (Ruby - AAO, Jekyll)](#august-8-2020)
* [August 7, 2020 (Ruby - AAO)](#august-7-2020)
* [August 6, 2020 (Ruby - AAO)](#august-6-2020)
* [August 5, 2020 (Ruby - AAO)](#august-5-2020)
* [August 4, 2020 (Ruby - CW)](#august-4-2020)
* [August 3, 2020 (Ruby - CW)](#august-3-2020)


---

## August 8, 2020

### Ruby

#### App Academy Open > Full Stack Online - Intro to Programming > Advanced Problems > Greatest Factor Array

>Write a method `greatest_factor_array` that takes in an array of numbers and returns a new array where every even number is replaced with it's greatest factor. A greatest factor is the largest number that divides another with no remainder. For example the greatest factor of 16 is 8. (For the purpose of this problem we won't say the greatest factor of 16 is 16, because that would be too easy, ha)

##### Final Working Solution

I created a new array called `gcf array` and put the following inside: ran `map` on in inputed array (`arr`) and named each element `num`. An `ifelse` statement that said `if num % 2 == 0`, run a new method called `replace_gf` with the value of `num`, `else` place the value of `num` into the `gcf_arr`. The `replace_gf` method receives a value (`num`) and beginning with the number `1`, does a reverse enumeration with `reverse_each` excluding `num`, assigning `factor` to each enumeration variable. On each enumeration, this will `return factor if num % factor == 0`. At the end of the `greatest_factor_array` method, I returned the completed `gcf_arr`.

#### App Academy Open > Full Stack Online - Intro to Programming > Advanced Problems > Perfect Square

>Write a method `perfect_square?` that takes in a number and returns a boolean indicating whether it is a perfect square. A perfect square is a number that results from multiplying a number by itself. For example, 9 is a perfect square because 3\*3 = 9, 25 is a perfect square because 5\*5 = 25.

##### Final Working Solution

To solve this, I wrote a loop to run from 1 to num, inclusive, assigning each enumeration variable to `factor`. I then used an `if` statement to `return true if factor * factor == num`. I put `return false` outside of the loop if the condition was never met for inputs that aren't a perfect square.

#### App Academy Open > Full Stack Online - Intro to Programming > Advanced Problems > Triple Sequence

>Write a method `triple_sequence` that takes in two numbers, start and length. The method should return an array representing a sequence that begins with `start` and is `length` elements long. In the sequence, every element should be 3 times the previous element. Assume that the length is at least 1.

##### Final Working Solution

Initialized an array named `sequence` with the value for `start`. Set a `while` loop to loop for the length of array found from the value of `length` using the `length` method (i.e., `sequence.length`) while it is less than the actual value of `length`, so it will stop at one less than the actual value. Inside the `while` loop, append the product of the value of `sequence[-1]` and `3` to the end of the `sequence` array. When loop has concluded, return `sequence`.

### Personal Projects > Personal Website

* Installed Jekyll on Linux Mint to use for personal website.

---

## August 7, 2020

### Ruby

#### App Academy Open > Full Stack Online - Intro to Programming > Advanced Problems > Prime Factors

>Write a method `prime_factors` that takes in a number and returns an array containing all of the prime factors of the given number.

##### Final Working Solution

First, I initialized an empty array called `factors` to hold the prime factors of the input (`num`). Then I decided to use the previously created `prime?` method to determine if an input is prime already and extend it to return the input if `true`. When I decided to run it, I was getting an empty array and figured out I was including too many numbers and needed an extra `.` in my `prime?` method.

---

## August 6, 2020

### Ruby

#### App Academy Open > Full Stack Online - Intro to Programming > Advanced Problems > Pick Primes

>Write a method `pick_primes` that takes in an array of numbers and returns a new array containing only the prime numbers.

##### Final Working Solution

In the method `pick_primes`, I used `select` on the inputed array in conjunction with a second method that I borrowed from a previous problem called `prime?`.

---

## August 5, 2020

### Ruby

#### App Academy Open > Full Stack Online - Intro to Programming > Advanced Problems > Most Vowels

>Write a method `most_vowels` that takes in a sentence string and returns the word of the sentence that contains the most vowels.

##### Final Working Solution

In the `most_vowels` method, initialize hash named `tally`. Use `split` to create an array of words from the input `sentence`, then iterate through array. Place each element as `word` into the hash `tally` while sending each `word` to a second method named `count_vowels`. In the second method, initialize `vowel_counter` with a `0` and a container variable with the `vowels`. Using the `count` method, return the integer to be stored with the `word` as a key, value pair in the `tally` hash in the original `most_vowels` method. Finally, using chained `keys` and `max` methods, return the `word` that contains the most vowels.

#### App Academy Open > Full Stack Online - Intro to Programming > Advanced Problems > Prime

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
