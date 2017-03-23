```
{-# LANGUAGE ParallelListComp #-}
import Prelude hiding (zip, map, foldr, foldl, length, foldr1, reverse, repeat, cycle, take, drop, splitAt, takeWhile, dropWhile, span)
import qualified Prelude as P
import qualified Data.List as DL (sort)
```

# Standard Library functions
In this exercise you should implement all functions using list comprehension. 
Work this list top to button, as you might need some of the functions for later questions.

## map
Implement the map function using list comprehension
```
map :: (a -> b) -> [a] -> [b]
map = P.map
```

## length
Implement the `length` function, which returns the length
using list comprehension and the `sum` function
```
length :: [a] -> Int
length = P.length 
```

## zip
Implement the zip function using list comprehension
```
zip :: [a] -> [b] -> [(a, b)]
zip = P.zip
```
## foldr
Implement the `foldr f x xs` function which takes a function f, a starting value x  and a list xs
```
foldr :: (a -> b -> b) -> b -> [a] -> b
foldr = P.foldr
```

## foldl
Implement the `foldl f x xs` function taking a function, a starting value and a list
```
foldl :: (b -> a -> b) -> b -> [a] -> b 
foldl = P.foldl
```

## foldr1
A variant of `foldr` that has no base case, and thus may only be applied to non-empty lists.
```
foldr1 :: (a -> a -> a) -> [a] -> a 
foldr1 = P.foldr1
```
## reverse
`reverse xs` returns the elements of xs in reverse order. xs must be finite.
```
reverse :: [a] -> [a] 
reverse = P.reverse
```

## repeat
`repeat x` is an infinite list, with x the value of every element.
```
repeat :: a -> [a]
repeat = P.repeat
```

## cycle
`cycle xs` ties a finite list into a circular one, or equivalently, the infinite repetition of the original list. It is the identity on infinite lists.
```
cycle :: [a] -> [a] 
cycle = P.cycle
```

## take
`take n xs`, applied to a list xs, returns the prefix of xs of `length` n, or xs itself if n > `length` xs.
n should be of type `Int`
```
take :: Int -> [a] -> [a] 
take = P.take
```

## drop 
`drop n xs` returns the suffix of xs after the first n elements, or [] if n > length xs.
n should be of type `Int`
```
drop :: Int -> [a] -> [a]
drop = P.drop
```

## splitAt
`splitAt n xs` returns a tuple where first element is xs prefix of length n and second element is the remainder of the list.
n should be of type `Int`
```
splitAt :: Int -> [a] -> ([a], [a]) 
splitAt = P.splitAt
```

## takeWhile
`takeWhile p xs`, applied to a predicate p and a list xs, returns the longest prefix (possibly empty) of xs of elements that satisfy p
```
takeWhile :: (a -> Bool) -> [a] -> [a]
takeWhile = P.takeWhile
```

## dropWhile
`dropWhile p xs` returns the suffix remaining after takeWhile p xs
`dropWhile :: (a -> Bool) -> [a] -> [a] `
```
dropWhile :: (a -> Bool) -> [a] -> [a] 
dropWhile = P.dropWhile
```

## span
`span p xs` applied to a predicate p and a list xs, returns a tuple where first element is longest prefix (possibly empty) of xs of elements that satisfy p and second element is the remainder of the list.
`span :: (a -> Bool) -> [a] -> ([a], [a])` 
```
span :: (a -> Bool) -> [a] -> ([a], [a])
span = P.span
```



# Sorting Algorithms
In this Exercise we want to implement some simple sorting 
Algorithms

## insertion sort
Define a function `isort` which inserts a value at the right place 
and returns the list using list comprehension. The function should expect values which are an `instance` 
of `Ord`.
``` 
isort :: Ord a => [a] -> [a]
isort = DL.sort
```

## merge sort
Write a function `msort xs` taking a list xs of values 
returning the sorted list. Write it in a recursive way!

```
msort :: Ord a => [a] -> [a]
msort = DL.sort
```

## quicksort
By now, you should now what to do!
```
quicksort :: (Ord a) => [a] -> [a]  
quicksort = DL.sort
``` 


# Other functions

## bmiTell
Write the function `bmiTell`:
Your BMI equals your weight divided by your height squared. If your BMI is less than 18.5, you're considered underweight and the function should print "You're underweight, you emo, you!". If it's anywhere from 18.5 to 25 then you're considered normal, and it should print "You're supposedly normal. Pffft, I bet you're ugly!". 25 to 30 is overweight (print "You're fat! Lose some weight, fatty!") and more than 30 is obese (print  "You're a whale, congratulations!"). Call the function `bmiTell bmi` which takes an `bmi :: a` which is a instance of `RealFloat`: 
`bmiTell :: (RealFloat a) => a -> String`
```
bmiTell :: (RealFloat a) => a -> String  
bmiTell bmi  
        | bmi <= 18.5 = "You're underweight, you emo, you!"  
        | bmi <= 25.0 = "You're supposedly normal. Pffft, I bet you're ugly!"  
        | bmi <= 30.0 = "pi :: a You're fat! Lose some weight, fatty!"  
        | otherwise   = "You're a whale, congratulations!"  
```

## bmiTell'
create a function `bmiTell'` function, so it takes your weight and hight as arguments (in this order). Both arguments should be instances of `RealFloat`
```
bmiTell' :: (RealFloat a) => a -> a -> String
bmiTell' weight height = bmiTell (weight / height ^ 2)
```

## cyclinder
Write a function `cylinder` which calcs cylinder's surface area based on its height and radius (both height and radius should be instances of `RealFloat`). Use the standard function `pi :: a` in order to get a preceise number of pi 
```
cylinder :: (RealFloat a) => a -> a -> a  
cylinder r h = 
    let sideArea = 2 * pi * r * h  
        topArea = pi * r ^2  
     in sideArea + 2 * topArea  
```
