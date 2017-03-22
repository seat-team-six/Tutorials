```
{-# LANGUAGE ParallelListComp #-}
import Prelude hiding (zip, map, foldr, foldl, length, foldr1)
import qualified Prelude as P
```

# 1 Standard Library functions
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
```
zip :: [a] -> [b] -> [(a, b)]
zip xs ys = [(x, y) | x <- xs, y <- ys]
```
## 1.4 foldr
Implement the `foldr` function which takes a function, a starting value and a list 
```
foldr :: (a -> b -> b) -> b -> [a] -> b
foldr = P.foldr
```

## 1.5 foldl
Implement the `foldl` function taking a function, a starting vlaue and a list
```
foldl :: (b -> a -> b) -> b -> [a] -> b 
foldl = P.foldl
```

## 1.6 foldr1
A variant of foldr that has no base case, and thus may only be applied to non-empty lists.
```
foldr1 :: (a -> a -> a) -> [a] -> a 
foldr1 = P.foldr1
```

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

# 3 Other functions

## 3.1 bmiTell
Write the function `bmiTell`:
Your BMI equals your weight divided by your height squared. If your BMI is less than 18.5, you're considered underweight and the function should print "You're underweight, you emo, you!". If it's anywhere from 18.5 to 25 then you're considered normal, and it should print "You're supposedly normal. Pffft, I bet you're ugly!". 25 to 30 is overweight (print "You're fat! Lose some weight, fatty!") and more than 30 is obese (print  "You're a whale, congratulations!"). Call the function bmiTell which takes an a which is a instance of RealFloat: 
hint : bmiTell :: (RealFloat a) => a -> String  
```
bmiTell :: (RealFloat a) => a -> String  
bmiTell bmi  
        | bmi <= 18.5 = "You're underweight, you emo, you!"  
        | bmi <= 25.0 = "You're supposedly normal. Pffft, I bet you're ugly!"  
        | bmi <= 30.0 = "You're fat! Lose some weight, fatty!"  
        | otherwise   = "You're a whale, congratulations!"  
```

## 3.2 bmiTell'
create a function `bmiTell'` function, so it takes your weight and hight as arguments (in this order). Both arguments should be instances of `RealFloat`
```
bmiTell' :: (RealFloat a) => a -> a -> String
bmiTell' weight height = bmiTell (weight / height ^ 2)
```


