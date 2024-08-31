## Bash has 2 types of arrays

### Indexed Arrays   
Definition: Indexed arrays are a type of array where elements are stored with a numeric index starting from 0.   

Syntax:   
Declaration: declare -a array_name   
Assignment: array_name=(element1 element2 element3)   
Accessing Elements: ${array_name[index]}   

Example   
```bash
# Declare and assign values
fruits=("Apple" "Banana" "Cherry")

# Accessing elements
echo ${fruits[0]}  # Outputs: Apple
echo ${fruits[1]}  # Outputs: Banana
```

Operations:
Length of array: ${#array_name[@]}   
Adding elements: array_name+=(element4)   
Removing elements: unset array_name[index]   


Detailed examples
```
# Indexed array (gets declared with lower case a)
declare -a shopping_list

# manual initialization
shopping_list=("milk" "bread" "butter" "chicken" "avocado" "bananas")

# Iterate over array elements
for item in "${shopping_list[@]}"; do
  echo ${item}
done

# Iterate over the array to print index and item
# "${!fruits[@]}" - index list 0, 1, 2, 3 etc

for index in "${!shopping_list[@]}"; do
  echo "Shopping item at index $index is ${shopping_list[$index]}"
done

# Reading lines from a file into an array
lines=($(cat /path/to/file.txt))

# Iterate over the array elements
for line in "${lines[@]}"; do
  echo "$line"
done
```

### Building array from output of command 

```bash
# Read the output of a command line by line into an array
mapfile -t lines < <(cat /path/to/file.txt)

# Iterate over the array elements
for line in "${lines[@]}"; do
  echo "$line"
done
```

Scenarios:
Append element to array as last element:
```bash
To append an element to the end of an indexed array, use the += operator:

# Declare an indexed array
fruits=("Apple" "Banana" "Cherry")

# Append an element to the end
fruits+=("Mango")

# Output the array
echo "${fruits[@]}"  # Outputs: Apple Banana Cherry Mango
```

Insert element in to array as first elemtent:
```bash
# Declare an indexed array
fruits=("Apple" "Banana" "Cherry")

# Append an element to the end
fruits+=("Mango")

# Insert an element at the first index
fruits=("Orange" "${fruits[@]}")

# Output the array
echo "Array after insertion and appending:"
echo "${fruits[@]}"  # Outputs: Orange Apple Banana Cherry Mango
```

Insert element in to array at index n
```bash 
# Declare a 3-element indexed array
fruits=("Apple" "Banana" "Cherry")

# Insert an element at the second index (index 1, as arrays are 0-indexed)
fruits=("${fruits[@]:0:1}" "Mango" "${fruits[@]:1}")

# Output the array
echo "${fruits[@]}"  # Outputs: Apple Mango Banana Cherry
```

### Associative Arrays   
Definition: Associative arrays store data as key-value pairs, where keys are strings instead of numeric indices.   

Syntax:   
Declaration: declare -A array_name   
Assignment: array_name[key]="value"   
Accessing Elements: ${array_name[key]}   

Example:   
```bash
# Declare and assign values
declare -A capital_cities
capital_cities=([France]="Paris" [Germany]="Berlin" [Italy]="Rome")

# Accessing elements
echo ${capital_cities[France]}  # Outputs: Paris
```

Iterating:   
```bash

for key in "${!capital_cities[@]}"; do
  echo "$key: ${capital_cities[$key]}"
done
```

Operations:   
Length of array: ${#array_name[@]}   
Adding elements: array_name[new_key]="new_value"   
Removing elements: unset array_name[key]   

Key Differences:   
Indexed arrays use numeric indices, whereas associative arrays use string keys.   
Indexed arrays are suitable for ordered lists of items, while associative arrays are ideal for storing and accessing data by a descriptive key.   
