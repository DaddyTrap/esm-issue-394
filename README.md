# Reproduce

```bash
npm i esm@3.0.34
node -r esm circular1.js
```

## Expected

Simply output `42`, the value in `other.js`

```
42
```

## Actual Output

`42` is **printed**, but an error occurred says that `Other is not defined`.

```
42
file:///home/daddytrap/Work/issue/circular1.js:4
console.log(Other.some_val);

ReferenceError: Other is not defined
    at Object.<anonymous> (file:///home/daddytrap/Work/issue/circular1.js:4:7)
    at Object.<anonymous> (file:///home/daddytrap/Work/issue/circular1.js:1)
```

## Cause?

It seems that this occurs in **circular import** (that's why the file named circular).
