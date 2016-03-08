Предположим, что стандартные функции определены следующим образом:
```haskell
id x = x
const x y = x
max x y = if x <= y then y else x
infixr 0 $
f $ x = f x
```
Сколько редексов имеется в следующем выражении
```haskell
const $ const (4 + 5) $ max 42
```

Answer:

```
3
```