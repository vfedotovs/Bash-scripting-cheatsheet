## Defining functions
```bash
myfunc() {
    echo "hello $1"
}
```

## Same as above (alternate syntax)
```bash
function myfunc {
    echo "hello $1"
}

myfunc "John"
```

## Returning values
```bash
myfunc() {
    local myresult='some value'
    echo "$myresult"
}

result=$(myfunc)
```

## Raising errors
```bash
myfunc() {
  return 1
}

if myfunc; then
  echo "success"
else
  echo "failure"
fi

```
