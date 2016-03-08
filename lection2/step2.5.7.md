Отметьте функции, которые не могут привести к расходимости ни на каком корректном наборе аргументов.
```haskell
foo a = a
bar = const foo
baz x = const True
quux = let x = x in x
corge = 10
grault x 0 = x
grault x y = x
garply = grault 'q'
waldo = foo
```

Answer:

```haskell
* baz
 waldo
 grault
* corge
 foo
 bar
 quux
 garply
```