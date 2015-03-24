### From Python to Haskell

# General Background

# Data First
In python, in many cases,  the structure of the data you're working with is implied by the code.  In Haskell, it is stated explicitly.  I noticed a subtle shift in how I was coding in haskell in that my first thought is more aligned with "how is the data structured", while in python my first thought was "what does the code say."

Once you have this shift, and you start with looking at data first, it becomes easier to read haskell, because there's a lot you don't have to read.  To understand a function, you look at its type signature.  You only really look at the guts of the function if you're trying to come to a greater understanding of that specific function.


# The Great Synonym Table


Map a function over one argument that is in a container. (i.e. Functors)

function | notes | examples
---------|---------------------|---------
map      | specific to lists   
fmap     | More generic, works on anything that has implemented it
<$>      | Exactly the same as fmap, but its infix.  f <$> d
liftM    | Same as fmap, but in the Monad module.
liftA    | Same as fmap, but in the Applicative module.


Map a function over multiple arguments, each in containers (i.e. Applicative)

function | notes | examples
---------|---------------------|---------
<*>      |  In the Applicative |
`ap`     |  In Monad


Put a value in a container.  How does it know which container?  By the type signature, or it figures it out based on code around it.

function | notes | examples
---------|---------------------|---------
pure     |  In the Applicative 
return   |  In Monad



Bind multiple functions
function | notes | examples
---------|---------------------|---------
'>=='    |  In the Monad module. 
'<-'     |  This is 'do' notation





# A note for people from python.  
https://www.python.org/dev/peps/pep-0020/
When I started and found this list of synonyms, I started to think that this haskell thing was bogus.  I tracked it back to the python principle of 'There should be one-- and preferably only one --obvious way to do it.'  So many synonyms said that there were a number of ways to do things in haskell.  While I still generally agree with the 'only one' principle, Haskell provides an interesting entry.  Because of Haskell's type system, where a function is guaranteed to take a specific input and always return a specific output....you have a huge guarantee of safety.  This level of safety allows you to be more expressive in your code.

