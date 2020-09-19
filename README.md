# Programming Journal

> _“[B]y their competence in secular fields and by their personal activity, elevated from within by the grace of Christ, let them work vigorously so that by human labor, technical skill and civil culture, created goods may be perfected according to the design of the Creator and the light of his word.” – St. John Paul II_

- [Resources I Use & Profiles](#resources--profiles)
- [September 19, 2020 (Ruby - AAO)](#september-19-2020)
- [August 10, 2020 (JavaScript - CW)](#august-10-2020)
- [August 8, 2020 (Ruby - AAO & CW, Jekyll)](#august-8-2020)
- [August 7, 2020 (Ruby - AAO)](#august-7-2020)
- [August 6, 2020 (Ruby - AAO)](#august-6-2020)
- [August 5, 2020 (Ruby - AAO)](#august-5-2020)
- [August 4, 2020 (Ruby - CW)](#august-4-2020)
- [August 3, 2020 (Ruby - CW)](#august-3-2020)

---

## September 19. 2020

### Ruby

#### App Academy Open > Full Stack Online - Intro to Programming > Advanced Problems > Fibonacci

> The fibonacci sequence is a sequence of numbers whose first and second elements are 1. To generate further elements of the sequence we take the sum of the previous two elements. For example the first 6 fibonacci numbers are 1, 1, 2, 3, 5, 8. Write a method `fibonacci` that takes in a number `length` and returns the fibonacci sequence up to the given length.

##### Final Working Solution

First, check if input `length` is 0 or 1. For `length == 0`, return an empty array `[]`. For `length == 1`, return `[1]`. Next, declare an array `fibseq` initialized with the values `[1,1]` as the first numbers of the Fibonacci sequence that is longer than `1` will always be 1, 1. Use `while` to loop for the length of `fibseq`, assigning the last index value to the variable `last` and the second to last index value to `second_to_last`. Then, add the values of `last` and `second_to_last` and store the result in the variable `next_ele`. Finally, append `next_ele` to the `fibseq` array which will be returned after the loop completes.

#### App Academy Open > Full Stack Online - Intro to Programming > Advanced Problems > Caesar Cipher

> Write a method `caesar_cipher` that takes in a string and a number. The method should return a new string where every character of the original is shifted `num` characters in the alphabet.

##### Final Working Solution

Define a variable `alphabet` to hold the letters of the alphabet and a `new_word` variable with `""` where the new word will be stored after the cipher runs. (To be continued)

---

## August 13, 2020

### Ruby

#### App Academy Open > Full Stack Online - Intro to Programming > Advanced Problems > Summation Sequence

> A number's summation is the sum of all positive numbers less than or equal to the number. For example: the summation of 3 is 6 because 1 + 2 + 3 = 6, the summation of 6 is 21 because 1 + 2 + 3 + 4 + 5 + 6 = 21. Write a method `summation_sequence` that takes in a two numbers: `start` and `length`. The method should return an array containing `length` total elements. The first number of the sequence should be the `start` number. At any point, to generate the next element of the sequence we take the summation of the previous element. You can assume that `length` is not zero.

##### Final Working Solution

First, initialize an array with the value from `start` and name it `sum_array`. Use a `while` loop to run while the length of `sum_aray` is less than the value of the `length` input. Assign the value of the last index of the array `sum_array` to the variable `prev`. At this point, it is clear this will be two complex for one method, so two will be needed. Create a new method named `summation`, then pass the value of `prev` (to become `number`) to it. Inside the `summation` method initialize a new variable `summationsum` with the value of `0` inside. Enumerate over the array from `1` to the value of `number` inclusive (naming the current value `i`) adding `i` to the value of `summationsum` and then make it the new value. At the completion of this loop, return the value of `summationsum` to the first method `summation_sequence` to be appended to the `sum_array` array. After the completion of the `while` loop in the `summation_sequence` method, return the value of `sum_array`.

def summation_sequence(start, length)
sum_array = [start]
while sum_array.length < length
prev = sum_array[-1]
sum_array << summation(prev)
end
sum_array
end

def summation(number)
summationsum = 0
(1..number).each do |i|
summationsum += i
end
return summationsum
end

print summation_sequence(3, 4) # => [3, 6, 21, 231]
print summation_sequence(5, 3) # => [5, 15, 120]

---

## August 10, 2020

### JavaScript

#### Codewars Kata > Sum of positive

> You get an array of numbers, return the sum of all of the positives ones. Note: if there is nothing to sum, the sum is default to 0.

##### Final Working Solution

First, I used `filter` to filter any element with a value below `0` into a new array called `pos_nums`. Next, I used `reduce` with a initial value of `0`, as per the instructions, to add all the values on the last array.

---

## August 8, 2020

### Ruby

#### App Academy Open > Full Stack Online - Intro to Programming > Advanced Problems > Greatest Factor Array

> Write a method `greatest_factor_array` that takes in an array of numbers and returns a new array where every even number is replaced with it's greatest factor. A greatest factor is the largest number that divides another with no remainder. For example the greatest factor of 16 is 8. (For the purpose of this problem we won't say the greatest factor of 16 is 16, because that would be too easy, ha)

##### Final Working Solution

I created a new array called `gcf array` and put the following inside: ran `map` on in inputed array (`arr`) and named each element `num`. An `ifelse` statement that said `if num % 2 == 0`, run a new method called `replace_gf` with the value of `num`, `else` place the value of `num` into the `gcf_arr`. The `replace_gf` method receives a value (`num`) and beginning with the number `1`, does a reverse enumeration with `reverse_each` excluding `num`, assigning `factor` to each enumeration variable. On each enumeration, this will `return factor if num % factor == 0`. At the end of the `greatest_factor_array` method, I returned the completed `gcf_arr`.

#### App Academy Open > Full Stack Online - Intro to Programming > Advanced Problems > Perfect Square

> Write a method `perfect_square?` that takes in a number and returns a boolean indicating whether it is a perfect square. A perfect square is a number that results from multiplying a number by itself. For example, 9 is a perfect square because 3\*3 = 9, 25 is a perfect square because 5\*5 = 25.

##### Final Working Solution

To solve this, I wrote a loop to run from 1 to num, inclusive, assigning each enumeration variable to `factor`. I then used an `if` statement to `return true if factor * factor == num`. I put `return false` outside of the loop if the condition was never met for inputs that aren't a perfect square.

#### App Academy Open > Full Stack Online - Intro to Programming > Advanced Problems > Triple Sequence

> Write a method `triple_sequence` that takes in two numbers, start and length. The method should return an array representing a sequence that begins with `start` and is `length` elements long. In the sequence, every element should be 3 times the previous element. Assume that the length is at least 1.

##### Final Working Solution

Initialized an array named `sequence` with the value for `start`. Set a `while` loop to loop for the length of array found from the value of `length` using the `length` method (i.e., `sequence.length`) while it is less than the actual value of `length`, so it will stop at one less than the actual value. Inside the `while` loop, append the product of the value of `sequence[-1]` and `3` to the end of the `sequence` array. When loop has concluded, return `sequence`.

#### Codewars Kata > Keep Hydrated

> Nathan loves cycling. Because Nathan knows it is important to stay hydrated, he drinks 0.5 litres of water per hour of cycling. You get given the time in hours and you need to return the number of litres Nathan will drink, rounded to the smallest value.

##### Final Working Solution

Use the `floor()` method on the product of `time` and `0.5`.

#### Codewars Kata > Even or Odd

> Create a function that takes an integer as an argument and returns "Even" for even numbers or "Odd" for odd numbers.

##### Final Working Solution

Using a ternary `if` statement, test the input `number` modulo `2` and return `"Even"` if the result is `0`, else return `"Odd"`.

### Personal Projects > Personal Website

- Installed Jekyll on Linux Mint to use for personal website.

---

## August 7, 2020

### Ruby

#### App Academy Open > Full Stack Online - Intro to Programming > Advanced Problems > Prime Factors

> Write a method `prime_factors` that takes in a number and returns an array containing all of the prime factors of the given number.

##### Final Working Solution

First, I initialized an empty array called `factors` to hold the prime factors of the input (`num`). Then I decided to use the previously created `prime?` method to determine if an input is prime already and extend it to return the input if `true`. When I decided to run it, I was getting an empty array and figured out I was including too many numbers and needed an extra `.` in my `prime?` method.

---

## August 6, 2020

### Ruby

#### App Academy Open > Full Stack Online - Intro to Programming > Advanced Problems > Pick Primes

> Write a method `pick_primes` that takes in an array of numbers and returns a new array containing only the prime numbers.

##### Final Working Solution

In the method `pick_primes`, I used `select` on the inputed array in conjunction with a second method that I borrowed from a previous problem called `prime?`.

---

## August 5, 2020

### Ruby

#### App Academy Open > Full Stack Online - Intro to Programming > Advanced Problems > Most Vowels

> Write a method `most_vowels` that takes in a sentence string and returns the word of the sentence that contains the most vowels.

##### Final Working Solution

In the `most_vowels` method, initialize hash named `tally`. Use `split` to create an array of words from the input `sentence`, then iterate through array. Place each element as `word` into the hash `tally` while sending each `word` to a second method named `count_vowels`. In the second method, initialize `vowel_counter` with a `0` and a container variable with the `vowels`. Using the `count` method, return the integer to be stored with the `word` as a key, value pair in the `tally` hash in the original `most_vowels` method. Finally, using chained `keys` and `max` methods, return the `word` that contains the most vowels.

#### App Academy Open > Full Stack Online - Intro to Programming > Advanced Problems > Prime

> Write a method `prime?` that takes in a number and returns a boolean, indicating whether the number is prime. A prime number is only divisible by 1 and itself.

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

- The keyword `return` isn't needed when creating methods in Ruby! The last statement that was evaluated in the body of the method is returned by default. If needed, `return` can be used to return from a method earliy.

---

## August 3, 2020

### Ruby

#### CodeWars Kata #1

> Complete the function so that it takes an array of keys and a default value and returns a hash (Ruby) / dictionary (Python) with all keys set to the default value.

##### Unsuccessful Attempts

Unintentonally left off the _whole_ solution in these.

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

- [P1xt's Computer Science and Programming Guide](https://github.com/P1xt/p1xt-guides)
- [App Academy Open](https://open.appacademy.io/)
- [DevDocs](https://devdocs.io/)
- [CodeWars](https://www.codewars.com/)
  - [MY CodeWars Profile](https://www.codewars.com/users/lalaithan)
- [Khan Academy Math](https://www.khanacademy.org/)
