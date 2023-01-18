# Numbers & Letters

Go to main page: [Click to main!](./README.md)

Go to prev page: [Click to prev!](./repeat.md)

Go to next page: [Click to next!](./special_letter.md)

## Introduction

When I was young, I was absorbed in the fancy Internet. One day, I saw a game, the game will give you a square shape of letters, including "I", "O", "l", "1", "0". The only task you need to do is to find out the only one "1" or "0" among the very same-shaped letters, as soon as possible.

```
l O I O l O
I l O l I l
O I l I O I
l O I O l O
I l O l I l
O I 1 I O I
```

That is not so easy, but as it I became familiar with, the advanced level was jump out and give me a new challenge:

```
IOlIOIIOlIOllIOI0IIOIOIIlI
```

How to find out the number letter among those English letter?

## Simple Example

Regexp can pick up various types of letters, like number digits, blank letters, English letters...

It is obvious that

- the number digits are ranged from `0` to `9`, and 
- the English letters are ranged from `a` to `z`, and `A` to `Z`.

Apart from the past articles, in which we match the letter exactly, instead, in this article, we will match the letter in a range.

As I above said, there are three ranges: `0-9`, `a-z`, `A-Z`. (The reason why `z` is separated from `A` is the ASCII code).

Then, we can make square brackets (`[]`) surround the range, to pick up the corresponding types of letters.

```
[0-9]
[a-z]
[A-Z]
```
For example, a given string is `123abcDEF`, the different results were made by the different ranges:

| Range | Result |
| :---: | :--- |
| `[0-9]` | `1`, `2`, `3` |
| `[a-z]` | `a`, `b`, `c` |
| `[A-Z]` | `D`, `E`, `F` |
| `[2-3a-b]` | `2`, `3`, `a`, `b` |
| `[0-9a-z]` | `1`, `2`, `3`, `a`, `b`, `c` |
| `[0-9a-zA-Z]` | `1`, `2`, `3`, `a`, `b`, `c`, `D`, `E`, `F` |

The blank characters are *SPACE* (` `), *TAB* (`\t`), *LINE FEED* (`\n`), *CARRIAGE RETURN* (`\r`), *FORM FEED* (`\f`), and *VERTICAL TAB* (`\v`). Therefore, the blank type can be written as `[ \t\n\r\f\v]`. (Don't forget the first letter in the square brackets is "` `"!) (Too long, hard to remember and type, right? )

## Simplify

Either `[0-9a-zA-Z]` or `[ \t\n\r\f\v]` is too complicated to type, so a good idea is to make an alias for them!

| Alias | Equals | Alias | Equals |
| :---: | :--- | :---: | :--- |
| `\d` | `[0-9]` | `\D` | `[^0-9]`, letters not in `\d` |
| `\w` | `[0-9a-zA-Z]` and a `_` | `\W` | `[^0-9a-zA-Z_]`, letters not in `\w` |
| `\s` | `[ \t\n\r\f\v]` | `\S` | `[^ \t\n\r\f\v]`, letters not in `\s` |

As you see, if we add a `^` to the front of a range, it will match the letters *not* in the range, convert a lower case to its upper case, it achieves the same effect, too.

As an example, `123asdf456qwer` when used with `\d`, the result is `123456`(separately), and when used with `\D`, the result is `asdfqwer`(separately too).

## Other

Dot (or ) `.` matches any character except a *LINE FEED* character (`\n`).

```
a
aa
aaa
aaaa
```
Use `a..`, give us the 3rd line `a` `a` `a`, 4th line frontly `a` `a` `a` (that is, `(aaa)a`, the last `a` is insufficient to have a new times to match `a..`)

## Test

An old saying goes, **Practice makes perfect**. Try yourself to implement the following questions, the more ways you can find, the better.

1. Match `Flood`(not `F` `l` `o` `o` `d`, which is separated, the following question is also require continuous) in `Flood is dangerous!`
2. Match `12_04` in `The date is 12_04_2027.`
3. Match `oo` in `I read a book.`
4. Match names in below: first name is `John`, last name is `Smith`

```
John Smith
John Bohn Smith
Jon Bob Smitt.
John Adam Smith
```

5. Match dynamic datetime, formatted as `Hour:Minute:Second Day_Month_Year`
6. Find `oo` in Pig (Joke)

Go to next page: [Click to next!](./special_letter.md)
