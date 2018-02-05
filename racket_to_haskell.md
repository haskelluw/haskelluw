# Racket versus Haskell

### Hello World
Racket
```racket
#lang racket

"helloworld"
```
Haskell
```
module Main where

main = print "helloworld"
```
When you run a haskell program, haskell will execute the main function, and
thats it.

### Simple Math
Racket
```racket
(+ 4 (3 * 2))
```
Haskell
```
4 + 3 * 2
```

### Function Definition e.g Selector (With contracts/type signature)

Racket
```racket
-- a racket contract
(define (f x y) x)
```
Haskell
```
f :: a -> b -> a
f x y = x
```
While Type Signatures are (mostly) optional in Haskell, if you functions don't
type check, your program won't compile, e.g `f :: Int -> Int; f x = "NOT AN INT"` doesn't compile.
### Function Application e.g mapping

Racket
```scheme
(map add1 '(1 2 3)) -- '(2 3 4)
```
Haskell
```
map (1 +) [1, 2, 3] -- [1, 2, 3]
```

### Composing Functions

Racket
```racket
((compose add1 abs) -1) -- 2
```
Haskell
```
(+ 1) . abs $ -1 -- 2
```

### Structs/Algebraic Data Types

Racket
```racket
(define-struct maybe-error (value error))
```

Haskell
```
data MaybeError a = Value a | String
```
Given Racket's dynamic nature, as opposed to Haskell's strongly typed nature,
structs and algebraic data types are quite different, but are used to achieve
the same results.
