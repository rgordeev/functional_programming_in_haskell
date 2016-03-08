Напишите функцию с сигнатурой:
```haskell
avg :: Int -> Int -> Int -> Double
```
вычисляющую среднее значение переданных в нее аргументов:
```
GHCi> avg 3 4 8
5.0
```

Answer:

```haskell
avg :: Int -> Int -> Int -> Double
avg a b c = (fromIntegral (a + b + c)) / 3
```