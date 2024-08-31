## Below are some common bash string operations:

1. String Length
Get the length of a string.
```bash
string="Hello, World!"
length=${#string}
echo $length  # Output: 13
```

2. Substring Extraction
Extract a substring from a string.
```bash
string="Hello, World!"
substr=${string:7:5}
echo $substr  # Output: World
string:7:5 extracts a substring starting from index 7 and of length 5.
```

3. Substring Replacement
Replace the first occurrence of a substring.
```bash
string="Hello, World!"
new_string=${string/World/Bash}
echo $new_string  # Output: Hello, Bash!
```

Replace all occurrences of a substring.
```bash
string="apple apple apple"
new_string=${string//apple/orange}
echo $new_string  # Output: orange orange orange
```

4. Prefix and Suffix Removal
Remove a prefix.
```bash
filename="photo.jpg"
new_filename=${filename#photo}
echo $new_filename  # Output: .jpg
```

Remove a suffix.
```bash
filename="photo.jpg"
new_filename=${filename%.jpg}
echo $new_filename  # Output: photo
```

5. Pattern Matching in Substrings
Remove the shortest match of a pattern from the beginning.
```bash
string="Hello, World!"
new_string=${string#Hello, }
echo $new_string  # Output: World!
```

Remove the longest match of a pattern from the beginning.
```bash
string="abc/def/ghi"
new_string=${string##*/}
echo $new_string  # Output: ghi
```

Remove the shortest match of a pattern from the end.
```bash
string="file.tar.gz"
new_string=${string%.gz}
echo $new_string  # Output: file.tar
```

Remove the longest match of a pattern from the end.
```bash
string="file.tar.gz"
new_string=${string%%.*}
echo $new_string  # Output: file
```

6. Concatenation
Concatenate strings.
```bash
str1="Hello"
str2="World"
concatenated="$str1, $str2!"
echo $concatenated  # Output: Hello, World!
```

7. Convert to Upper/Lower Case
Convert to lowercase.
```bash
string="HELLO"
lower_string=${string,,}
echo $lower_string  # Output: hello
```

Convert to uppercase.
```bash
string="hello"
upper_string=${string^^}
echo $upper_string  # Output: HELLO
```

8. Default Value Substitution
Use a default value if the string is empty.
```bash
string=""
echo ${string:-"Default Value"}  # Output: Default Value
```

9. Trim Leading/Trailing Whitespace
There is no direct Bash operation for trimming whitespace, but you can use parameter expansion and sed or awk:
```bash
string="  Hello, World!  "
trimmed_string=$(echo "$string" | xargs)
echo ">$trimmed_string<"  # Output: >Hello, World!<
```

Converting an Integer to a String   
In Bash, integers are stored as strings by default. When you assign an integer value to a variable,
it is treated as a string unless you explicitly use it in a mathematical context.

```bash
num=123  # This is an integer stored as a string

# Using the integer as a string
string="Number: $num"
echo $string  # Output: Number: 123
```

Converting a String to an Integer   
If you need to perform arithmetic operations, Bash automatically treats numeric strings as integers.

```bash
string="123"

# Converting string to integer by using it in an arithmetic context
num=$((string + 1))
echo $num  # Output: 124
```
