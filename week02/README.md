# Week 02: Python functions

Students read chapter 3 in Sweigart. They also begin to learn about web scraping; that is covered in a separate part of this repo.

Now we start writing functions in Python3. We’ll write files in [Atom](https://atom.io/) and save them with the `.py` extension.

To run a function named `foobar.py` that’s in the current directory, type this at the bash prompt (`$`):

```bash
python3 foobar.py
```

Students can now write and save their Python3 code in files.

## Using parameters and returns in functions

Sweigart notes that many functions operate as “black boxes”: This describes a function with parameters (it takes arguments) and a `return` statement. Something goes into it (arguments) and something comes out of it (whatever is returned). You don’t need to know how it works; you just need to know what it does.

This is true for many functions we use from imported libraries, such as BeautifulSoup (for web scraping). We run a function such as this:

```python
print( varname.get_text() )
```

... and it prints only the text content from inside an HTML element (such as `title` or `li`) that is stored in `varname`. The variable `varname` contains the HTML tags (possibly quite a lot of tags), but the BeautifulSoup function `get_text()` removes them neatly, giving us just text. How does `get_text()` do that? *We don’t need to know.* That’s the beauty of a function as a black box: It just works.

We don’t need to know how a toaster toasts bread to get toast out of it. We put in two pieces of bread (the *arguments* we pass into a function), and toast is *returned* after the function runs.

## Building functions for each task in a program

Near the end of chapter 3, Sweigart gives us a program that (oddly enough) does not include any functions. In the folder named *modular-code*, we will walk through how to convert that program into a collection of three modular functions.

*Modular* can mean that each function accomplishes *one* task. It’s not sensible to write a function that contains only one line, so don’t take this too literally. However, writing a lot of small, short functions gives you an easy way to test and perfect each part of your program in a very manageable way.

It keeps the larger job &mdash; the complete program &mdash; from overwhelming you.

## Chapter review: chapter 3

These are the takeaways from this chapter.

1. The `def` statement (how and where to use it)
2. *When* is the code in a function executed? (Know the difference between *defining* a function and *running* it.)
3. Parameters, arguments: Where are these, in a function?
    a. How do they work when you *define* the function?
    b. How do they work when you *run* the function? (Note: Instead of run, we may say *call* or *execute* the function. All the same meaning.)
4. The `return` keyword (used in a function)
5. The `NoneType` data type: value is `None`
    a. This will be important in scraping! If you get an error that says something does not work because it cannot be applied to `NoneType`, it means something returned `None` when you were expecting another value. You can also see `None` used explicitly in Mitchell’s error-handling script [here](https://github.com/REMitchell/python-scraping/blob/master/chapter1/3-exceptionHandling.py).
    b. “Python adds `return None` to the end of any function definition with no `return` statement.” (p. 65) In other words, a function with no `return` statement returns `None`.
    c. An empty `return` statement also returns `None`.
6. Keyword arguments: You can forget this for the time being
7. Scope of variables: **Important!**
    a. Any variable has *local* scope or *global* scope. It cannot have both.
    b. A local variable exists only *inside* a function. It cannot be transmitted outside the function (although its *value* can — via `return`).
    c. A global variable exists *outside* any function. It may be used inside a function.
    d. Sometimes you will make a mistake about the scope of a variable, and then your answers or results will not be correct.
        i. “It is a **bad habit** to rely on global variables as your programs get larger and larger.” (p. 67)
        ii. “To simplify your life, **avoid using** local variables that have the same name as a global variable or another local variable.” (p. 69)
    e. Four rules, p. 70
8. Functions as “black boxes”: Describes a function with *parameters* (it takes *arguments*) and a `return` statement. Something goes into it (arguments) and something comes out of it (whatever is returned).
9. Exception handling (also called error handling): `try`/`except` pattern
