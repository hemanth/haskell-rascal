![](https://raw.githubusercontent.com/hemanth/haskell-rascal/master/imgs/swahili.png)

> Learning Haskell with a rascal!

__What the hell is haskell-rascal?__

First of all, let me define rascal:

> a mischievous or cheeky person, especially a child or man (typically used in an affectionate way). "a lovable rascal"

Ok, now that you know what rascal means, let's learn some haskell!

>Haskell is an advanced purely-functional programming language. An open-source product of more than twenty years of cutting-edge research, it allows rapid development of robust, concise, correct software. With strong support for integration with other languages, built-in concurrency and parallelism, debuggers, profilers, rich libraries and an active community, Haskell makes it easier to produce flexible, maintainable, high-quality software. 

![](http://upload.wikimedia.org/wikipedia/commons/f/fd/Frank_Oppenheimer.jpg)

__"The best way to learn is to teach" -- Frank Oppenheirmer__


This repo will remains W.I.P as a rascal learns haskell by teaching it!


__Installation:__

Easy way is to hit [haskell-platfrom](http://www.haskell.org/platform/), download the required binary, install it! 

P.S: If want to build from source paw [here](https://ghc.haskell.org/trac/ghc/wiki/Building/GettingTheSources)

__CLI FTW:__

```sh
$ ghci
GHCi, version 7.6.3: http://www.haskell.org/ghc/  :? for help
Loading package ghc-prim ... linking ... done.
Loading package integer-gmp ... linking ... done.
Loading package base ... linking ... done.
Prelude> :set prompt "haskell-rascal> "
haskell-rascal> 
```
P.S: You can as well add `:set prompt "haskell-racal> "` to your `~/.ghci` file.

If you want to try it online, you must looks at [ghc.io](ghc.io) or [codeworld](http://codeworld.info/)

Now you are all set to do some haskell with a rascal!

---

# Defining Haskell in a line

"It's a pure functional programming language which is statically typed and lazily evaluated!"

Let's break it down.

__Pure functions:__ 

Pure implies idempotency and functional programming is a one in which functions are first-class. 

__Statically typed:__

A programming language is said to use static typing when type checking is performed during compile-time as opposed to run-time. 

__Lazy evaluation:__

Lazy evaluation is an evaluation strategy which delays the evaluation of an expression until its value is needed and which also avoids repeated evaluations.

# Abstract syntactic and semantic structure.

* Set of modules make a Haskell program at the top most level.

* The top level of a module consists of a collection of declarations.

* The the next lower level are expressions.

* The bottom level is Haskell 's lexical structure.

We shall paw at each of them as we move on the next units of Haskell.

# Simple Arithmetic and Boolean Algebra

![](http://upload.wikimedia.org/wikipedia/commons/d/d8/Bring_radicals_cartoon.PNG)

REPL is your friend :)

```
haskell-rascal> 0/0
NaN
haskell-rascal> 1/0
Infinity
haskell-rascal> 22 / 7
3.142857142857143
haskell-rascal> pi
3.141592653589793
haskell-rascal> ( 43 * 1 ) - 1
42
```

`&&` => boolean and `||` => boolean or. `not` => negatation

```
haskell-rascal> not True 
False
haskell-rascal> True || False
True
haskell-rascal> True && ( False && True )
False
haskell-rascal> not (True && ( False && True ))
True
```

# Types and Type-classes

`:type` aka `:t` is at your help.

```
haskell-rascal> :type True
True :: Bool
haskell-rascal> :t 1
1 :: Num a => a
haskell-rascal> :t 'H'
'H' :: Char
haskell-rascal> :t "H"
"H" :: [Char]
haskell-rascal> :t []
[] :: [a]
```
---

# Lists and tuples

Lists are a **homogenous** data structure, i.e it stores several elements of the same type.

Let's see few examples:

```
haskell-rascal> ["hemanth",1,2]

<interactive>:5:12:
    No instance for (Num [Char]) arising from the literal `1'
    Possible fix: add an instance declaration for (Num [Char])
    In the expression: 1
    In the expression: ["hemanth", 1, 2]
    In an equation for `it': it = ["hemanth", 1, 2]
    
haskell-rascal> ["hemanth",'h']

<interactive>:7:12:
    Couldn't match expected type `[Char]' with actual type `Char'
    In the expression: 'h'
    In the expression: ["hemanth", 'h']
    In an equation for `it': it = ["hemanth", 'h']

haskell-rascal> ['h','e']
"he"

haskell-rascal> [1,2,3]
[1,2,3]

haskell-rascal> "heman" == ['h','m','a','n']
False

haskell-rascal> "he" == ['h','e']
True
```
---

__List functions:__

List processing:
  * (:) (list constructor)
  * ++
  * head
  * last
  * tail
  * init
  * length
  * !! (list index)

Arithmetic Operations:
  * div
  * mod
  * gcd
  * lcm
  * even
  * odd
  * sum
  * product

Extended list processing:
  * maximum
  * minimum
  * reverse
  * elem
  * notElem
  * concat
  * take
  * drop
  * takeWhile
  * dropWhile
  * words
  * unwords
   
```
haskell-rascal> let nums = [1,3,3,7]

haskell-rascal> length nums
4

haskell-rascal> reverse nums
[7,3,3,1]

haskell-rascal> head nums
1

haskell-rascal> last nums
7

haskell-rascal> init nums
[1,3,3]

haskell-rascal> nums !! 3 -- Get the element at the given index.
7

haskell-rascal> minimum nums
1

haskell-rascal> maximum nums 
7

haskell-rascal> 0 : nums
[0,1,3,3,7]

haskell-rascal> nums ++ [-1]
[1,3,3,7,-1]

haskell-rascal> [1,3] ++ [3,7] 
[1,3,3,7]  

haskell-rascal> take 3 nums
[1,3,3]

haskell-rascal> drop 1 nums
[3,3,7]

haskell-rascal> sum nums
14

haskell-rascal> product nums
63

haskell-rascal> 7 `elem` nums
True

haskell-rascal> 0 `elem` nums
False

haskell-rascal> ['a'..'z']
"abcdefghijklmnopqrstuvwxyz"

haskell-rascal> words "May the force be with you"
["May","the","force","be","with","you"]

haskell-rascal> unwords ["haskell","-","rascal"]
"haskell - rascal"

haskell-rascal> takeWhile (<=7) [1..10]
[1,2,3,4,5,6,7]

haskell-rascal> dropWhile (<=7) [1..10]
[8,9,10]

```
---

Tuples unlike lists have a __fixed__ number of elements (immutable) and are heterogenous data structures. 

__Example:__

```
haskell-rascal> let co-ordinates = (70.1,80.1,"L33t Area")
```

__Tuple functions:__

* fst
* snd
* curry
* uncurry 
* swap 

```
haskell-rascal> fst (True,"1")
True

haskell-rascal> snd (True,"1")
"1"

haskell-rascal> zip "leet" [1,3,3,7]
[('l',1),('e',3),('e',3),('t',7)]

haskell-rascal> unzip [('l',1),('e',3),('e',3),('t',7)]
("leet",[1,3,3,7])
```
---

#Functions!

Before we dive into functions, it's worth to know the below:

```
-- By default:
f g h x <=> (((f g) h) x)

-- $ replace parenthesis.
f g $ h x       <=>   f g (h x) ⇔ (f g) (h x)
f $ g h x       <=>   f (g h x) ⇔ f ((g h) x)
f $ g $ h x     <=>   f (g (h x))

-- (.) composition.
(f . g) x       <=>   f (g x)
(f . g . h) x   <=>   f (g (h x))
```

Let's take a `fib` function as an example and try to understand function!

```
haskell-rascal> let fib = 0 : 1 : zipWith (+) fib (tail fib)

haskell-rascal> take 10 fib
[0,1,1,2,3,5,8,13,21,34]
```

Before we procede further understanding the fib function, we must understand what [Thunks](http://en.wikipedia.org/wiki/Thunk_%28functional_programming%29)
are.

In most of the programming langauges that supports tuples, saying `(4+2,7)` would be stored as `(6,7)` but in Haskell it gets stored as `(_,7)` where the `_` is the thunk value.

Lets explore the same in ghci:

```haskell
haskell-rascal> let x = (4+2,7)

haskell-rascal> :print x
x = ((_t1::Integer),7)
```

Notice that `_t1` is the thunk value here, now if we fetch the second element of that tuple, it will be 7, but the first element we **not** be evaluated yet!

```haskell
haskell-racal> snd x
7

haskell-racal> :print x
x = ((_t2::Integer),7)
```

But as soon as we fetch the first or just evaluate `x`, the first value will be evaluated.

```
haskell-racal> fst x
6

haskell-racal> x
(6,7)
```

So, a thunk is basically a value that has not yet been computed yet. 
As per the need it can evaluate or partly-evaluated to a real value.
Partial evaluation of a thunk will resulting in a value with more thunks in it.

Now the above function can be expanded as:

```haskell
fibs                        = 0 : 1 : <thunk>
tail fib                    = 1 : <thunk>
zipWith (+) fib (tail fib)  = <thunk>
```

The first row left shifted is the second row and the third row is the sum of 
the first and the second rows and all of them are **sharing** the same thunk.

`take 2 fibs` will give use `[0, 1]` which is direct and does not need further evaluation.

Now if we say `take 3 fib` Haskell will directly get the 0 and 1, and then it will have to partly evaluate the thunk, so that it can fully evaluate `zipWith (+) fib (tail fib)`, by getting the sum of the first two rows but it can't fully do that, it can begin to sum the first two rows:

```haskell
fibs                         = 0 : 1 : 1: <thunk>
tail fibs                    = 1 : 1 : <thunk>
zipWith (+) fibs (tail fibs) = 1 : <thunk>
```

Likewise it keeps on going creating `<thunk's>` and eval them as and when the need arrives.

P.S: If you says `fib n` and then `fib n-m` where `m<=n` the expresion will not be re-evaled but will just take the first `n-m` numbers from the list it has already evaled!


Now that we could eat and digest thunks, let start with simple functions ;)

```haskell
haskell-rascal> let square n = n * n;
haskell-rascal> square 3
9
```

```haskell
haskell-rascal> :t square
square :: Num a => a -> a
```

^ Is the signature of a function.

Wondering what does `square :: Num a => a -> a` means?

Let us see few more example of the functions we have used already:

```haskell
haskell-rascal> :t fst
fst :: (a, b) -> a

haskell-rascal> :t snd
snd :: (a, b) -> b

haskell-rascal> :t map
map :: (a -> b) -> [a] -> [b]
```

The combination of :: and the type after it is called a type signature. Say we did a `:t "haskell"` we would get `"haskell" :: [Char]` in this case it's indicating that `"haskell"` is of `[Char]` type.

Generalising: x :: y  => "the expression x has the type y".


__Recurison:__

[Recursion](https://encrypted.google.com/search?hl=en&q=recursion) simply defined: A function invoking itself for a finite number of times before returning the result of computation. 

As we had noticed in the above example of `fibs` here is a simple example of `factorial`

```haskell
haskell-rascal> let factorial n = if n > 0 then n * factorial (n-1) else 1

haskell-rascal> factorial (10)
3628800
```

__λ abstraction A.K.A Anonymous function:__

Function without a name?! 

How would I call it?

Let's see a simple example to understand how they work and why are they important. 

```haskell
haskell-rascal> let list = [0..4]
haskell-rascal> let odds x = x + 1 
haskell-rascal> map odds list
[1,2,3,4,5]
```

The above steps adds `1` to every element to the list, that's why the function is named `odds`, but why must even bother creating a function, naming it, after all it's just by map?

Wouldn't be useful if we could condense them all to one single line!?

Yes, that's where lamda abstractions are very useful, so with the help of it, we can rewrite the above code as below and yet get the same effect.

```haskell
haskell-rascal> map (\x->x+1) list 
[1,2,3,4,5]
```





