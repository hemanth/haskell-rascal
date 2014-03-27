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

![](/http://upload.wikimedia.org/wikipedia/commons/d/d8/Bring_radicals_cartoon.PNG)

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