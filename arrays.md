# Bash has 2 tyes of arrays:
 - indexed arrays
 - asociative arrays

```
#!/usr/bin/env bash


# Indexed array (gets declared with lower case a)
declare -a shopping_list

# manual initialization
shopping_list=("milk" "bread" "butter" "chicken" "avocado" "bananas")

# iterate over array elements
for item in "${shopping_list[@]}"; do
  echo ${item}
done

# Iterate over the array to print index and item
# "${!fruits[@]}" - index list  like for x in range(List)

for index in "${!shopping_list[@]}"; do
  echo "Shopping item at index $index is ${shopping_list[$index]}"
done

# Example: Reading lines from a file into an array
lines=($(cat /path/to/file.txt))

# Iterate over the array elements
for line in "${lines[@]}"; do
  echo "$line"
done
```

# Building array from output of command 

```bash
# Read the output of a command line by line into an array
mapfile -t lines < <(cat /path/to/file.txt)

# Iterate over the array elements
for line in "${lines[@]}"; do
  echo "$line"
done
```

```
# TODO:
# - add item to array at index
# - update item at index
# - remove item from array at index
# - read item at index - done
```
