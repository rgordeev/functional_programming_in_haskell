Реализуйте класс типов
```haskell
class SafeEnum a where
  ssucc :: a -> a
  spred :: a -> a
```
обе функции которого ведут себя как ```succ``` и ```pred```
стандартного класса ```Enum```, однако являются тотальными,
то есть не останавливаются с ошибкой на наибольшем и наименьшем
значениях типа-перечисления соответственно, а обеспечивают циклическое поведение.
Ваш класс должен быть расширением ряда классов типов стандартной библиотеки,
так чтобы можно было написать реализацию по умолчанию его методов,
позволяющую объявлять его представителей без необходимости писать
какой бы то ни было код. Например, для типа Bool должно быть достаточно написать строку
```haskell
instance SafeEnum Bool
```
и получить возможность вызывать
```
GHCi> ssucc False
True
GHCi> ssucc True
False
```

Answer:

```haskell
class (Enum a, Bounded a, Eq a) => SafeEnum a where
  ssucc :: a -> a
  spred :: a -> a
  ssucc a | maxBound == a = minBound
          | otherwise = succ a
  spred a | minBound == a = maxBound
          | otherwise = pred a
```