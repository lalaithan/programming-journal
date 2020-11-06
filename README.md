# Programming Journal

> _“[B]y their competence in secular fields and by their personal activity, elevated from within by the grace of Christ, let them work vigorously so that by human labor, technical skill and civil culture, created goods may be perfected according to the design of the Creator and the light of his word.” – Pope St. John Paul II_

- [Resources I Use & Profiles](#resources--profiles)
- [November 2, 3, 2020 (JavaScript, PHP, Ruby - CW, AAO)](#november-2020)
- [October 15, 19, 31, 2020 (Ruby - AAO)](#october-2020)
- [September 19, 21, 2020 (Ruby - AAO)](#september-2020)
- [August 3, 4, 5, 6, 7, 8, 13, 2020 (JavaScript, Ruby, Jekyll - AAO, CW)](#august-2020)

--

Note:

- CW = CodeWars
- AAO = App Academy Open

---

## November 2020

### JavaScript

#### 11/2 - CodeWars Kata > Basic Variable Assignment

> This code should store "codewa.rs" as a variable called name but it's not working. Can you figure out why?

```javascript
var a == "code";
var b == "wa.rs";
var name == a + b;
```

##### Final Working Solution

JavaScript does not use `==` nor `"`. Replace them with `=` and `'` respectively.

--

### PHP

#### 11/3 - CodeWars Kata > Basic Variable Assignment

> This code should store "codewa.rs" as a variable called name but it's not working. Can you figure out why?

```php
$a == "code";
$b == "wa.rs";
$name == $a + $b;
```

##### Final Working Solution

In PHP, strings should be surrounded by single quotations and assignment uses a single equal symbol, just like JavaScript yesterday. However, in PHP concatenation is accomplished with a `.` instead of a `+`.

--

### Ruby

#### 11/5 - App Academy Open > Software Engineering Foundations > En

Ran `rbenv-installer` script but it said `directory is not present in PATH`.

#### 11/3 - App Academy Open > Full Stack Online - Intro to Programming > Advanced Problems > Anagrams

> Write a method `anagrams?` that takes in two words and returns a boolean indicating whether or not the words are anagrams. Anagrams are words that contain the same characters but not necessarily in the same order. Solve this without using `.sort`.

##### Final Working Solution, pt.2

Begin by writing a second method named `char_count` to count the characters in the input `word1` and `word2`, one `word` at a time. Initialize a new hash with the value `0` and name it `count`. Enumerate through each character of `word`, storing both the `char` (character) and increment the number for count by `1`. Return the hash `count` to the `anagrams?` method. In the `anagrams?` method, compare the equivalency between `word1` and `word2`, returning the result.

#### 11/3 - App Academy Open > Full Stack Online - Intro to Programming > Advanced Problems > Consonant Cancel

> Write a method consonant_cancel that takes in a sentence and returns a new sentence where every word begins with it's first vowel.

##### Final Working Solution

Begin by calling `split` on the input `sentence` and assigning it to a variable called `words`. Call `map` on this new array. Assign each element to `word`. Send `word` to a second method called `remove_first_consonant`. In the new method, create a string with all vowels and assign it to `vowels`. Enumerate over `word` using `each_char.with_index` using `char` and `i` for each character and index respectively. Using an `if` statement, test if the `char` is in `vowels`. If it is, return `word` from that index to the last `char` to the original `consonant_cancel` method to replace current element in place; assign all results to new_words. Call `join(" ")` on `new_words` and return the final value.

#### 11/3 - App Academy Open > Full Stack Online - Intro to Programming > Advanced Problems > Same Char Collapse

> Write a method `same_char_collapse` that takes in a string and returns a collapsed version of the string. To collapse the string, we repeatedly delete 2 adjacent characters that are the same until there are no such adjacent characters. If there are multiple pairs that can be collapsed, delete the leftmost pair. For example, we take the following steps to collapse "zzzxaaxy": zzzxaaxy -> zxaaxy -> zxxy -> zy

##### Final Working Solution

Initialize a variable named `reducible` with the value `true`. Use a `while` loop that loops while `reducible` remains `true`. Inside the loop, call `split("")` on the input `str` and store the result in a variable called `chars`. Set the `reducible` variable to `false`. Enumerate through `chars` using `each.with_index` assigning each `char` and `i`. Use an `if` statement to test if the current character is equiavalent to the one following character. If it is, remove the current character along with the next one. Set `reducible` to `true` and `break` the `if` statement. After the enumeration, call `join("")` on `chars` and assign it to `str`. At the completion of the `while` loop, return `str`.

--

#### 11/2 - App Academy Open > Full Stack Online - Intro to Programming > Advanced Problems > Pyramid Sum

> Write a method `pyramid_sum` that takes in an array of numbers representing the base of a pyramid. The function should return a 2D array representing a complete pyramid with the given base. To construct a level of the pyramid, we take the sum of adjacent elements of the level below.

##### Final Working Solution, pt. 2

First, initialize a new array `pyramid` with the input `base` as one element (eg., `pyramid = [base]`). Create a `while` loop to run as long as `pyramid.length` is less than the `length` of the array in `base`. Inside the loop, assign the first element of `pyramid` to `prev_level`. To simplify this method, create a second method named `adjacent_sum` to receive the array in `prev_level`. In the `adjacent_sum` method, initialize an empty array and assign it the name `new_arr`. Call the `each_with_index` method on the input `arr` (array in `prev_level`), assigning `i` to the index. Create an `if` statement to run while `i` doesn't equal `arr.length - 1`. Inside the `if` statement, add the element at index `i` to the element at index `i+1`, then append the resulting value to `new_arr`. `Return` the value of `new_arr` to the `while` loop still running in the original `pyramid_sum` method, to be assigned to the variable named `next_level`. Next, place `next_level` at the beginning of the `pyramid` array by calling `unshift`. Once the `while` loop completes, `return` the resulting `pyramid` array.

#### 11/2 - App Academy Open > Full Stack Online - Intro to Programming > Advanced Problems > All Else Equal

> Write a method `all_else_equal` that takes in an array of numbers. The method should return the element of the array that is equal to half of the sum of all elements of the array. If there is no such element, the method should return nil.

##### Final Working Solution

First, create a second method `sum_array` to add the elements of the array together. Inside `sum_array`, initialize a new variable `sum` to `0`. Next, enumerate over the contents of `arr` (input array) using `each`, assigning each element as `num`, adding each `num` to the value of `sum`. At the completion, `return sum` to the original `all_else_equal` method. Inside `all_else_equal`, assign the resulting value of `sum` to `sum` (a new variable inside this method). Enumerate over the orginal input `arr`, assigning each value to `ele` and test `if ele` is equivalent to the value of `sum / 2.0`. We use `2.0` instead of `2` to allow decimal answers. If this test returns true, return the value of `ele` and end the method. If the result of the test is false, return `nil` and end the method.

#### 11/2 - App Academy Open > Full Stack Online - Intro to Programming > Advanced Problems > Anagrams

> Write a method `anagrams?` that takes in two words and returns a boolean indicating whether or not the words are anagrams. Anagrams are words that contain the same characters but not necessarily in the same order. Solve this without using `.sort`.

##### Final Working Solution, pt. 1

Begin by writing a second method named `char_count` to count the characters in the input `word1` and `word2`, one at a time. Initialize a new hash and name it `count`.

> tbc....

---

## October 2020

### Ruby

#### 10/31 - App Academy Open > Full Stack Online - Intro to Programming > Advanced Problems > Adjacent Sum

> Write a method `adjacent_sum` that takes in an array of numbers and returns a new array containing the sums of adjacent numbers in the original array. See the examples.

##### Final Working Solution

First, initialize an empty array called `new_arr`. Enumerate over the input `arr` using `each_with_index` and assigning each element `ele` with the indeces `i`. Next, use an `if` statement to check if the index isn't the last one by testing `i` against the `length` of `arr` minus `1`. For each value of `i`, add it to the value next to it and append the value onto the end of `new_arr`. Once the enumeration of the array is complete, return `new_arr`.

#### 10/31 - App Academy Open > Full Stack Online - Intro to Programming > Advanced Problems > Pyramid Sum

> Write a method `pyramid_sum` that takes in an array of numbers representing the base of a pyramid. The function should return a 2D array representing a complete pyramid with the given base. To construct a level of the pyramid, we take the sum of adjacent elements of the level below.

##### Final Working Solution, pt. 1

> tbc...

--

#### 10/19 - App Academy Open > Full Stack Online - Intro to Programming > Advanced Problems > Double Letter Count

> Write a method that takes in a string and returns the number of times that the same letter repeats twice in a row.

##### Final Working Solution

Declare a variable called `count` with the value `0`. Next, apply an enumerable using `each_char` and `with_index` setting each as `char` and `i`. Create an `if` statement to test if the current character is the same as the next character in the string. If so, then add `1` to `count`. After the enumeration is complete, return the value of `count`.

--

#### 10/15 -App Academy Open > Full Stack Online - Intro to Programming > Advanced Problems > Vowel Ciper

> Write a method `vowel_cipher` that takes in a string and returns a new string where every vowel becomes the next vowel in the alphabet.

##### Final Working Solution

Since there aren't many vowels to store, a hash named `changes` can be used to store what each vowel should change to. There is still a need to store all the `vowels` into a string to use as a check. Store an enumeration into a variable called `new_word`. To set up the enumeration, run the `split` method on the incoming `string` value, dividing at every character. Run the `map` method on the resulting array and name each value `char`. Use an `ifelse` statement to check if `char` is also in `vowels`. If it isn't, then return the value of `char` (to be stored in the string `new_word`). If it is, use `char` to locate the value the new letter should be in `changes` and return the value of `char`. At the conclusion of the method, run `join` (joining at every character) on `new_word` and `return` the result.

---

## September 2020

### Ruby

#### 9/21 - App Academy Open > Full Stack Online - Intro to Programming > Advanced Problems > Caesar Ciper

> Write a method `caesar_cipher` that takes in a string and a number. The method should return a new string where every character of the original is shifted `num` characters in the alphabet.

##### Final Working Solution

Define a string `alphabet` to hold the letters of the alphabet and a `new_word` variable with `""` where the new word will be stored after the cipher runs. Enumerate over the `str` input with the `each_char` method, naming the current character `char`. Store the index of the character as it appears in the string `alphabet` into `old_idx`. Add `old_idx` to the `num` input that tells the program how many characters to shift and store the value in `new_idx`. Compute `new_idx` mod `26` and iterate through the `alpabet` string until the value of the most recent computation. Add that character to the end of the variable `new_word`. Return `new_word` after the enumeration is complete.

--

#### 9/19- App Academy Open > Full Stack Online - Intro to Programming > Advanced Problems > Fibonacci

> The fibonacci sequence is a sequence of numbers whose first and second elements are 1. To generate further elements of the sequence we take the sum of the previous two elements. For example the first 6 fibonacci numbers are 1, 1, 2, 3, 5, 8. Write a method `fibonacci` that takes in a number `length` and returns the fibonacci sequence up to the given length.

##### Final Working Solution

First, check if input `length` is 0 or 1. For `length == 0`, return an empty array `[]`. For `length == 1`, return `[1]`. Next, declare an array `fibseq` initialized with the values `[1,1]` as the first numbers of the Fibonacci sequence that is longer than `1` will always be 1, 1. Use `while` to loop for the length of `fibseq`, assigning the last index value to the variable `last` and the second to last index value to `second_to_last`. Then, add the values of `last` and `second_to_last` and store the result in the variable `next_ele`. Finally, append `next_ele` to the `fibseq` array which will be returned after the loop completes.

#### 9/19 - App Academy Open > Full Stack Online - Intro to Programming > Advanced Problems > Caesar Cipher

> Write a method `caesar_cipher` that takes in a string and a number. The method should return a new string where every character of the original is shifted `num` characters in the alphabet.

##### Final Working Solution

Define a variable `alphabet` to hold the letters of the alphabet and a `new_word` variable with `""` where the new word will be stored after the cipher runs. (To be continued)

---

## August 2020

#### Today I Learned...

- 8/4 - The keyword `return` isn't needed when creating methods in Ruby! The last statement that was evaluated in the body of the method is returned by default. If needed, `return` can be used to return from a method earliy.

--

### Personal Projects > Personal Website

- 8/8 - Installed Jekyll on Linux Mint to use for personal website. Later decided not to use it.

--

### JavaScript

#### 8/10 - Codewars Kata > Sum of positive

> You get an array of numbers, return the sum of all of the positives ones. Note: if there is nothing to sum, the sum is default to 0.

##### Final Working Solution

First, I used `filter` to filter any element with a value below `0` into a new array called `pos_nums`. Next, I used `reduce` with a initial value of `0`, as per the instructions, to add all the values on the last array.

--

### Ruby

#### 8/13 - App Academy Open > Full Stack Online - Intro to Programming > Advanced Problems > Summation Sequence

> A number's summation is the sum of all positive numbers less than or equal to the number. For example: the summation of 3 is 6 because 1 + 2 + 3 = 6, the summation of 6 is 21 because 1 + 2 + 3 + 4 + 5 + 6 = 21. Write a method `summation_sequence` that takes in a two numbers: `start` and `length`. The method should return an array containing `length` total elements. The first number of the sequence should be the `start` number. At any point, to generate the next element of the sequence we take the summation of the previous element. You can assume that `length` is not zero.

##### Final Working Solution

First, initialize an array with the value from `start` and name it `sum_array`. Use a `while` loop to run while the length of `sum_aray` is less than the value of the `length` input. Assign the value of the last index of the array `sum_array` to the variable `prev`. At this point, it is clear this will be two complex for one method, so two will be needed. Create a new method named `summation`, then pass the value of `prev` (to become `number`) to it. Inside the `summation` method initialize a new variable `summationsum` with the value of `0` inside. Enumerate over the array from `1` to the value of `number` inclusive (naming the current value `i`) adding `i` to the value of `summationsum` and then make it the new value. At the completion of this loop, return the value of `summationsum` to the first method `summation_sequence` to be appended to the `sum_array` array. After the completion of the `while` loop in the `summation_sequence` method, return the value of `sum_array`.

--

#### 8/8 - App Academy Open > Full Stack Online - Intro to Programming > Advanced Problems > Greatest Factor Array

> Write a method `greatest_factor_array` that takes in an array of numbers and returns a new array where every even number is replaced with it's greatest factor. A greatest factor is the largest number that divides another with no remainder. For example the greatest factor of 16 is 8. (For the purpose of this problem we won't say the greatest factor of 16 is 16, because that would be too easy, ha)

##### Final Working Solution

I created a new array called `gcf array` and put the following inside: ran `map` on in inputed array (`arr`) and named each element `num`. An `ifelse` statement that said `if num % 2 == 0`, run a new method called `replace_gf` with the value of `num`, `else` place the value of `num` into the `gcf_arr`. The `replace_gf` method receives a value (`num`) and beginning with the number `1`, does a reverse enumeration with `reverse_each` excluding `num`, assigning `factor` to each enumeration variable. On each enumeration, this will `return factor if num % factor == 0`. At the end of the `greatest_factor_array` method, I returned the completed `gcf_arr`.

#### 8/8 - App Academy Open > Full Stack Online - Intro to Programming > Advanced Problems > Perfect Square

> Write a method `perfect_square?` that takes in a number and returns a boolean indicating whether it is a perfect square. A perfect square is a number that results from multiplying a number by itself. For example, 9 is a perfect square because 3\*3 = 9, 25 is a perfect square because 5\*5 = 25.

##### Final Working Solution

To solve this, I wrote a loop to run from 1 to num, inclusive, assigning each enumeration variable to `factor`. I then used an `if` statement to `return true if factor * factor == num`. I put `return false` outside of the loop if the condition was never met for inputs that aren't a perfect square.

#### 8/8 - App Academy Open > Full Stack Online - Intro to Programming > Advanced Problems > Triple Sequence

> Write a method `triple_sequence` that takes in two numbers, start and length. The method should return an array representing a sequence that begins with `start` and is `length` elements long. In the sequence, every element should be 3 times the previous element. Assume that the length is at least 1.

##### Final Working Solution

Initialized an array named `sequence` with the value for `start`. Set a `while` loop to loop for the length of array found from the value of `length` using the `length` method (i.e., `sequence.length`) while it is less than the actual value of `length`, so it will stop at one less than the actual value. Inside the `while` loop, append the product of the value of `sequence[-1]` and `3` to the end of the `sequence` array. When loop has concluded, return `sequence`.

#### 8/8 - Codewars Kata > Keep Hydrated

> Nathan loves cycling. Because Nathan knows it is important to stay hydrated, he drinks 0.5 litres of water per hour of cycling. You get given the time in hours and you need to return the number of litres Nathan will drink, rounded to the smallest value.

##### Final Working Solution

Use the `floor()` method on the product of `time` and `0.5`.

#### 8/8 - Codewars Kata > Even or Odd

> Create a function that takes an integer as an argument and returns "Even" for even numbers or "Odd" for odd numbers.

##### Final Working Solution

Using a ternary `if` statement, test the input `number` modulo `2` and return `"Even"` if the result is `0`, else return `"Odd"`.

--

#### 8/7 - App Academy Open > Full Stack Online - Intro to Programming > Advanced Problems > Prime Factors

> Write a method `prime_factors` that takes in a number and returns an array containing all of the prime factors of the given number.

##### Final Working Solution

First, I initialized an empty array called `factors` to hold the prime factors of the input (`num`). Then I decided to use the previously created `prime?` method to determine if an input is prime already and extend it to return the input if `true`. When I decided to run it, I was getting an empty array and figured out I was including too many numbers and needed an extra `.` in my `prime?` method.

--

#### 8/6 - App Academy Open > Full Stack Online - Intro to Programming > Advanced Problems > Pick Primes

> Write a method `pick_primes` that takes in an array of numbers and returns a new array containing only the prime numbers.

##### Final Working Solution

In the method `pick_primes`, I used `select` on the inputed array in conjunction with a second method that I borrowed from a previous problem called `prime?`.

--

#### 8/5 - App Academy Open > Full Stack Online - Intro to Programming > Advanced Problems > Most Vowels

> Write a method `most_vowels` that takes in a sentence string and returns the word of the sentence that contains the most vowels.

##### Final Working Solution

In the `most_vowels` method, initialize hash named `tally`. Use `split` to create an array of words from the input `sentence`, then iterate through array. Place each element as `word` into the hash `tally` while sending each `word` to a second method named `count_vowels`. In the second method, initialize `vowel_counter` with a `0` and a container variable with the `vowels`. Using the `count` method, return the integer to be stored with the `word` as a key, value pair in the `tally` hash in the original `most_vowels` method. Finally, using chained `keys` and `max` methods, return the `word` that contains the most vowels.

#### 8/5 - App Academy Open > Full Stack Online - Intro to Programming > Advanced Problems > Prime

> Write a method `prime?` that takes in a number and returns a boolean, indicating whether the number is prime. A prime number is only divisible by 1 and itself.

##### Final Working Solution

The given method's name prevents just using Ruby's `prime?()` as the solution because it will create an infinite recursion. Since 1 and 2 are prime numbers, use an `if` statement that will return `false` if `num` (input) is below 2. To determine if any other value is prime, enumerate between 2 and the value of `num` exclusive (using `...`) setting each number as `factor`. Use an `if` statement to return `false` if dividing between `num` and `factor` equals 0. Include `return true` at the end of the method for values that don't meet previous tests, signifying they are prime numbers.

--

#### 8/4 - CodeWars Kata #1

> Given a year, return the century it is in.

##### Final Working Solution

Divide input by 100.0. Use `ceil` on quotient and return result.

--

#### 8/3 - CodeWars Kata #1

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

#### 8/3 - CodeWars Kata #2

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
