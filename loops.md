## Basic for loop

```bash
for i in /etc/rc.*; do
  echo "$i"
done
```

## C-like for loop
```bash
for ((i = 0 ; i < 100 ; i++)); do
  echo "$i"
done
```

## Ranges
```bash
for i in {1..5}; do
    echo "Welcome $i"
done
```

## Range with step size
```bash
for i in {5..50..5}; do
    echo "Welcome $i"
done
```

## Reading lines
```bash
while read -r line; do
  echo "$line"
done <file.txt
```

## Forever
```bash
while true; do
  ···
done
```
