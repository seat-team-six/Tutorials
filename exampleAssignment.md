```
{-# LANGUAGE ParallelListComp #-}
import Prelude hiding (zip, map, length)
```

# 1 Standard functions
In this exercise you should implement all functions
using list comprehension

## 1.1 map
Implement the map function using list comprehension
```
map :: (a -> b) -> [a] -> [b]
map f xs = [f x | x <- xs]
```

## 1.2 length
Implement the `length` function, which returns the length
using list comprehension and the `sum` function
```
length :: [a] -> Int
length xs = sum [1 | _ <- xs]
```

## 1.3 zip
Implement the zip function using list comprehension
zip :: [a] -> [b] -> [(a, b)]
zip xs ys = [(x, y) | x <- xs, y <- ys]

# 2 Sorting Algorithms
In this Exercise we want to implement some simple sorting 
Algorithms
# 2.1 insertion sort
Define a function `isort` which inserts a value at the right place 
and returns the list using list comprehension. The function should expect values which are an `instance` 
of `Ord`.
``` 
isort :: Ord a => [a] -> [a]
isort [] = []
isort (y:xs) = 
  [x | x <- (isort xs), x <= y] ++ [y] ++ [x | x <- (isort xs), x > y]
```

# 2.2 merge sort
Write a function `msort` taking a list of values 
returning the sorted list. Write it in a recursive way!

```
msort :: Ord a => [a] -> [a]
msort [] = []
msort [a]= [a]
msort xs =  merge
                (msort(take (length xs `div` 2) xs))
                (msort(drop (length xs `div` 2) xs))

merge :: Ord a => [a] -> [a] -> [a]
merge a [] = a
merge [] a = a
merge xs ys | head xs < head ys = (head xs) : merge (tail xs) ys
            | otherwise         = (head ys) : merge xs (tail ys)   
```

# 3 Higher order functions
In this exercise we want to implement some higher order functions

## 3.1 map 
Implement the map fuction by using list comprehension
```
map :: (a -> b) -> [a] -> [b]
map f xs = [f x | x <- xs]
```