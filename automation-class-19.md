# Python Regular Expression
*  Regular expressions/regex is used to check for a pattern exist in some text.
* Rexex has many applications like in text editors, search engines etc.
* Regex also used to validate some pattern of text such as phone numbers, emails, links etc.
* Regex also used in data science, data mining that deal with text.
* We import the re library for regex support `import re`.
## Basic Pattern
* Basic patterns is used to match ordinary characters that are exact with no special meanings. etc `"A", "z", "8"`
* The match() function returns a match object if the text matches the pattern as below:

```
pattern = r"Cookie"
sequence = "Cookie"
if re.match(pattern, sequence):
    print("Match!")
else: print("Not a match!")

output: Match

```
* the `r` in the beginning of the pattern tells Python to treat this as a literal string.

## Wild Card Characters
* Wild Card Characters are special characters that have different meaning than their exact look.
* The `search()` function scans a text for the first location a match exists.
* The `group()` function returns the matching string.
* The `.` period,  matches any single characters except newline character.
```
re.search(r'Co.k.e', 'Cookie').group()
output: Cookie

```
* The `^` caret, matches the start of the string.

```
re.search(r'^Eat', "Eat cake!").group()
output: Eat
```
* The `$` matches the end of a string as in 

``` 
re.search(r'cake$', "Cake! Let's eat cake").group()

output: cake

```

* `[abc] - Matches a or b or c.` matches a or b or c.
* `[a-zA-Z0-9]` matches any letter from (a to z) or (A to Z) or (0 to 9)
* `\` can be used in front of all the metacharacters to remove their special meaning
```
`re.search(r'Not a\sregular character', 'Not a regular character').group()
'Not a regular character'
```

* `\w ` - Lowercase 'w'. matches any single letter, digit, or underscore.
* `\W` - Uppercase 'W'. matches any character not part of \w (lowercase w).
* `\s` - Lowercase 's'. matches a single whitespace character like: space, newline, tab, return.
* `\S` - Uppercase 'S'. matches any character not part of \s (lowercase s).
```
print("Lowercase s:", re.search(r'Eat\scake', 'Eat cake').group())
print("Uppercase S:", re.search(r'cook\Se', "Let's eat cookie").group()
    Lowercase s: Eat cake
    Uppercase S: cookie

```

* `\d` - Lowercase d. matches decimal digit 0-9.
* `\D` - Uppercase d. matches any character that is not a decimal digit.
* `\t` - Lowercase t. Matches tab.
* `\n` - Lowercase n. Matches newline.
* `\r` - Lowercase r. Matches return.
* `\A` - Uppercase a. Matches only at the start of the string. Works across multiple lines as well.
* `\Z` - Uppercase z. Matches only at the end of the string.
* `^ `and `\A` are effectively the same, and so are `$` and `\Z`
* `\b` - Lowercase b. Matches only the beginning or end of the word.

## Repetitions
* `+` checks for repeatition by checking for a characters that appears once or more.
```
re.search(r'Co+kie', 'Cooookie').group()
cooookie

```
* `*` checks if whether the characters appears zero and more times.
* `?` checks for if a characters appears zero times or just once.
* `{5}` - checks exactly 5 number of times.
* `{5,}` - checks at least 5 times or more.
* `{5, 8}` - Repeat at least 5 times but no more than 8 times.

## Grouping in Regular Expressions
* We use the grouping to find things like email address:
```
statement = 'Please contact us at: support@datacamp.com'
match = re.search(r'([\w\.-]+)@([\w\.-]+)', statement)
if statement:
  print("Email address:", match.group()) # The whole matched text
  print("Username:", match.group(1)) # The username (group 1)
  print("Host:", match.group(2)) # The host (group 2)

  ```

* `search() versus match()` search searches everywhere in the string while match usually checks for a match at beginning of the string.
* `findall()` finds all matching and return a list.
* `sub()` finds the matching string and replaces the parts need to be replaced by the passed string.

```
statement = "Please contact us at: xyz@datacamp.com"
new_email_address = re.sub(r'([\w\.-]+)@([\w\.-]+)', r'support@datacamp.com', statement)
print(new_email_address)

output: Please contact us at: support@datacamp.com

```
<br />

## References

[Python Regular Expression](https://www.datacamp.com/community/tutorials/python-regular-expression-tutorial)

<br />

## [<-- Back](README.md)
