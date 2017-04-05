```
import Prelude hiding (map, length)
import qualified Prelude as P
```

# Standard Library functions
In this exercise you should implement all functions using list comprehension or recursive style without employing any standard library function. Work this list top to bottom, as you might need some of the functions for later questions.

## map
Implement the map function
```
map :: (a -> b) -> [a] -> [b]
map = P.map
```

## length
Implement the `length` function, which returns the length of any arbitrary list.
```
length :: [a] -> Int
length [] = 0
length (x:xs) = 1 + length xs
```
