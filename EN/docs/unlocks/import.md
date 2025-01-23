# Import
Putting all your code in a single file quickly becomes unmanageable. 
`import` statements allow you to import functions and global variables from another file.

`import filename`

This is the simplest form of import statement. It will give you access to everything defined in the file named `filename'. Each window in the game is a file, and the filename is the name displayed at the top of the window.

Here's an example with two files:
File named helper:
`def say_hello():
    print("hello from helper")`

Some other file:
`import helper
helper.say_hello()`

Here `import helper` runs the file named `helper` and gives you access to all it's globals.
You can then access variables and functions within the imported module using the `.` operator.
So in this example, `helper.say_hello()` calls `say_hello()` inside helper.

You can also move the globals from the imported module into the current scope where the import statement is executed using the `from` syntax.

`from helper import *`
Imports all globals from helper.

or

`from helper import say_hello`
Imports only the specified globals from helper.

This also imports the helper file, but instead of accessing it through a variable named `helper`, it unpacks globals from `helper` and assigns them directly in the local scope.

`from helper import say_hello
say_hello()`

This form of import is usually not recommended because you may accidentally overwrite variables in the import file due to name collisions.

## What it actually does
The first time you import a file, it will execute the entire file and then give you access to all variables that have been defined during the execution.
If you import the same file again, it will just return the cached globals from the first time again.

This means that import statements can have side effects. If you import a file that calls `harvest()`, it will actually harvest during the import. But when you import it again, it won't harvest again because the file is only run once.

There is a way to avoid such side effects using the `__name__` variable. This is a variable that is automatically set to `"__main__"` when a file is run directly, and to the name of the file when a file is run through `import`.
It is considered good practice to put any code that you don't want to run when the file is imported inside of an `if __name__ == "__main__":` block.

A common file structure in Python is to put the code that should be executed when the file is run into a `main()` function. This way you have a clear distinction between local script variables (defined inside `main()`) and global variables that can be imported (defined outside `main()`).

`a_global = "global value"

def main():
    a_local = "local value"
    //do things

if __name__ == "__main__":
    main()`