# Repeat

Go to main page: [Click to main!](./README.md)

Go to prev page: [Click to prev!](./an_easy_start.md)

Go to next page: [Click to next!](./number_&_letter.md)

## Introduction

> **A**uthor: Congratulations! Belly won the competition!
> 
> **Y**ou: Yeah! I'm so happy, too.
> 
> **A**: And with the result spreading, Belly has become a famous cat!
> 
> **Y**: What? Really?
> 
> **A**: Yes! And now, Belly has a lot of fans!
> 
> ```
> Leave your comments here!
> ------------------------
> 2027-11-28 12:58 user7861: I love Belllly!~
> 2027-11-28 20:12 user8765: Cute Belly WINNNNN!
> 2027-11-30 04:25 user1234: I lovvvvve Bellyyyyy!
> ```
> 
> **Y**: Ah, It seems that they are all deeply in love with Belly!
> 
> **A**: Yes, you see, they use the repeat letter to express their love!
> 
> ```
> Belllly WINNNNN lovvvvve Bellyyyyy
> ```
> 
> **Y**: You are right! I didn't notice that!
> 
> **A**: Let's make a notice!
> 
> **Y**: But how can I pick them all up?

## Simple Example

Regexp can pick up the **repeat** character for you! For a given letter, let's say, "v", there are some situations:

| Situation | Description |
| :---: | :--- |
| **v**abcdef | repeat once |
| **vv**abcde | repeat twice |
| **vvv**abcd | repeat three times |
| **vvv**...**v** | repeat many times |
| abcdef | no repeat |

And there is a simple grammar rule:

```
v{m,n}
```

Means that, you want to pick up those string parts, which have at least **m** to at most **n** times of **v**. First is the match character, followed by a pair of curly brackets, and in the brackets is the number of repeat times.

There is an example, the long string is:

```
lve             0  times
love            1  time
loove           2  times
loooove         4  times
looooooooooove  11 times
```

| Regexp | Meaning | Result |
| :---: | :---: | :--- |
| `lo{1,3}ve` | Begin is "l", end are "ve", "o" repeat {1,3} times| love loove |
| `lo{4,}ve` | Begin is "l", end are "ve", "o" repeat at least 4 times | loooove looooooooooove |
| `lo{,4}ve` | Begin is "l", end are "ve", "o" repeat at most 4 times | lve love loove loooove |

## Simplify

> **Y**: So, I can use `Bel{1,}y` to pick those names that have at least one "l" in it, right?
> 
> **A**: Yes, but there is a more simple way to denote it! It's the plus sign `+`!
> 
> **Y**: What does it mean?
> 
> **A**: It equals to `{1,}`.
> 
> **Y**: Um... Do you mean that I can write `Bel+y` instead of `Bel{1,}y`?
> 
> **A**: Yes, that's why it's called "simplify"!
> 
> **Y**: Cool! It does save a lot of time and more easier to read I think If I have familiar with it after a week maybe.
> 
> **A**: Have fun with it, and there are three simplifications:

| Regexp | Equals |
| :---: | :---: |
| `+` | `{1,}` |
| `*` | `{0,}` |
| `?` | `{0,1}` |

> **Y**: I cant wait to try it! Have you prepared new python script for me?
> 
> **A**: Nope, instead, I found a good tool for you! It's called [RegExr](https://regexr.com/)! It can help you to understand the regexp grammar! (This is not an AD, I just like it!)

Go to next page: [Click to next!](./number_&_letter.md)