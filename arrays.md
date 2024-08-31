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

# TODO:  CRUD of arrays
# - add item to array at index
# - update item at index
# - remove item from array at index
# - read item at index - done
#
# - Read in to array from command
