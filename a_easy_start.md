# A Easy Start

Go to main page: [Click to main!](./README.md)

Go to next page: [Click to next!](./repeate.md)

## Introduction

> **A**uthor: Cat is cute! let's say that you have a cat!
>
> **Y**ou: Okay, if so, what's my cat's name?
> 
> **A**: Um... Ah! It should depend on you!
>
> **Y**: Well, I want to name it "Belly!".
> 
> **A**: You have a virtual cat named "Belly" now!
> 
> ```
> /__/\
> \OiO |
> |    \  ~Meow
> |Belly\
> |_|_|_/
> ```
> 
> **A**: So cute isn't it? Let's sign up for a beautiful cat competition!
>
> **Y**: Emm...? How to ...
> 
> *[A Few Moments Later...]*
> 
> **A**: Wow! The registration seems successful! Let's check it out!
>
> **Y**: Okay!
> 
> *[Click the candidate list]*
> 
> **Y**: Oh! That's a lot of cats! How to find my cat?
> 
> ```
> There are 1035 cats that have registered for the competition!
> ------------------------------------------------------------
> Adam
> Adolf
> Alex
> Apple
> ...
> ```
> 
> **A**: That's the best time to use regexp!

## Simple Example

If you want to find some **exact** string, don't hesitate! Just type it!

> Alice: What's string you want to find?
>
> Bob: My friend name, "Tony".
>
> Alice: Oh, the regexp is exactly "Tony"!
>
> Bob: That's too easy!

> Alice: What's string you want to find?
>
> Bob: The fruit I eat, "strawberry".
>
> Alice: The regexp is exactly "strawberry".
>
> Bob: That's too easy!

## Try It Out

Hi, I prepared a python script for you! Just paste it to a file, and run it!

```python
import re  # the regular expression module

print("""You should input twice. 
First input a long string, Second input a short string.
The program will find the short string in the long string.""")
print("Start:")
long_string = input("Long string: ")
short_string = input("Short string: ")
results = re.findall(short_string, long_string)
print(f"Program found {len(results)} time(s) \"{short_string}\" in \"{long_string}\".")
```

let Bob try it out!

> Program: You should input twice.
>
> Program: First input a long string, Second input a short string.
>
> Program: The program will find the short string in the long string.
>
> Program: Start:
>
> Program: Long string: 
>
> Bob: Strawberry is my favorite fruit! I like strawberry!
>
> Program: Short string:
>
> Bob: strawberry
>
> Program: Program found 1 time(s) "strawberry" in "Strawberry is my favorite fruit! I like strawberry!".

Story continues...

> **Y**: I want to find "belly" but I find nothing, instead of "Belly".
>
> **A**: That's why I say "exact string", "belly" is not equal to "Belly".
>
> **Y**: Oh, I see.

Regexp is case sensitive, defaultly.

Go to next page: [Click to next!](./repeate.md)