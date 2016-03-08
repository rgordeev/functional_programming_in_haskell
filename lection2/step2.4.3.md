Пусть существуют два класса типов ```KnownToGork``` и ```KnownToMork```,
которые предоставляют методы ```stomp (stab)``` и ```doesEnrageGork (doesEnrageMork)``` соответственно:
```haskell
class KnownToGork a where
    stomp :: a -> a
    doesEnrageGork :: a -> Bool

class KnownToMork a where
    stab :: a -> a
    doesEnrageMork :: a -> Bool
```
Класса типов ```KnownToGorkAndMork``` является расширением обоих этих классов, предоставляя дополнительно метод ```stompOrStab```:
```haskell
class (KnownToGork a, KnownToMork a) => KnownToGorkAndMork a where
    stompOrStab :: a -> a
```
Задайте реализацию по умолчанию метода ```stompOrStab```,
которая вызывает метод ```stomp```, если переданное ему значение приводит в
ярость ```Морка```; вызывает ```stab```, если оно приводит в ярость Горка и вызывает сначала
```stab```, а потом ```stomp```, если оно приводит в ярость их обоих. Если не происходит ничего из
вышеперечисленного, метод должен возвращать переданный ему аргумент.

Answer:

```haskell
class KnownToGork a where
    stomp :: a -> a
    doesEnrageGork :: a -> Bool

class KnownToMork a where
    stab :: a -> a
    doesEnrageMork :: a -> Bool

class (KnownToGork a, KnownToMork a) => KnownToGorkAndMork a where
    stompOrStab :: a -> a
    stompOrStab a | doesEnrageGork a && not (doesEnrageMork a) = stab a
                  | doesEnrageMork a && not (doesEnrageGork a) = stomp a
                  | doesEnrageMork a && doesEnrageGork a = (stomp.stab) a
                  | otherwise = a
```