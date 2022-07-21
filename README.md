# PythonModules

Modules in Python

    In programming, it is inefficient, unsafe, and poor practice to have a single file with containing all of
    our code. In order to combat this and create an efficient, safe, and well-organized code, we use modules 
    to store our code. Essentially, splitting our code into sections/different files (modules) creates more
    manageable code and allows us to create more complex programs.
    
    Ok, so if our files are now separate from eachother, how can our main module access something in another
    .py file? Imagine you have two files:
    
    main.py
    utility.py
    
    To allow your main.py file to access your utility.py file, you would include the following at the 
    top of your main.py file:
    
    import utility
    
    Boom! It's that easy. All you have to do is type import and the file name without the extension.
    
    Sure, but what if I have a file that's within a folder, how would I import that?
    
    Ok, let's imagine our directory is looking like this now:
    
    main.py
    utility.py
    shopping
        shopping_cart.py
        
    How could we access the shopping folder and import the shopping_cart.py module??
    
    Worry not friend, its as simple as this:
    import shopping.shopping_cart.py

Different ways to import

    Up until now we've only touched import, but things can get more complex than that.
    
    When we're a couple folders deep, things get a little ugly as they could follow a format such as:
    print(shopping.more_shopping.shopping_cart.buy('apple')
    
    This is WAY too much to type just to use the buy function from the shopping_cart.py module
    
    instead, we can import the function itself:
    from shopping.more_shopping.shopping_cart import buy
    
    to then be able to use the buy function:
    print(buy('apple'))
    
    We can import multiple functions from a module:
    from utilities import multiply, divide
    
    We can also import a whole module, like this:
    from shopping.more_shopping import shopping_cart
    
    This can help avoid name collisions between functions
 
\_\_name\_\_

    An important concept is the concept of main, or better said, __main__
    
    A very common line of code is: if __name__ == '__main__':
    
    The name __main__ is given specifcally to the file that we run. This file, typically your
    main.py file, is given the name __main__ by default. 
    
    In a nutshell, that line of code just says: "if our main file is being run, do something"

Python Built-in Modules

    One of the main reasons that Python is used in almost every industry is that Python
    has a very large external module/packages index. Meaning it has a massive amount of 
    functionality that comes with the standard install of Python. For example, there's a
    math module, an email module, etc. These are all tools for our use!
    
    One useful module is the random module. 
    
    We can access it like this:
    import random
    
    This module allows us to generate pseudo-random numbers (psuedo because it is not actually
    random since it uses a complex algorithm to generate numbers that seem random)
    
    This module has functions such as random.random() which generates a random float number
    between 0 and 1. It also has a function, random.randint() that takes two numbers and will
    generate a random number between those two numbers.
    
    You can also give imports custom nicknames using the 'as' keyword:
    
    import random as randosaurus 
    
    Another useful module is the sys module.
    
    import sys
    
    Something interesting that sys can do is it can create a virtual terminal in your IDE.
    You can do this with the following line of code:
    sys.argv
    
Python Package Index

    Python has a humongous community full of developers who all contribute modules and packages
    that we can use for free!
    
    Link to the Python Package Index: https://pypi.org/
    
    You should always check to see if Python has a built in package that suits your needs 
    before installing one from the index.
    
Useful Modules

    Collection module:
    from collections import Counter, defaultdict, OrderedDict
    
    li = [1,2,3,4,5,6,7]
    print(Counter(li)) 
    ^This returns a dictionary that keeps track of how many times an item occured
    in an iterable
    
    dictionary = defaultdict(lambda: 5,{'a': 1, 'b': 2})
    print(dictionary['c'])
    ^This will return 5 as 'c' does not exist within the dictionary. Allows for default values
    to be set so that your code does not error out if something doesn't exist in the dictionary
    
    d = OrderedDict()
    d['a'] = 1
    d['b'] = 2
    
    d2 = OrderedDict()
    d2['b'] = 2
    d2['a'] = 1
    
    print(d2 == d) -> results in False as the OrderedDict class makes it so that order matters
    
    * note, recently Python has made dictionaries ordered by default *
    
    Datatime module:
    import datetime
    
    print(datetime.time(5,45,2)) -> results in 05:45:02
    print(datetime.date.today()) -> results in today's date
    
    Array module:
    from array import array
    
    arr = array('i', [1,2,3])
    print(arr[0]) -> 1
    
    Now why would this matter? It seems like it's a more complicated list!
    
    Turns out, arrays are a little more performant that lists 
