# External Editor
The in-game text editor is usually sufficient to play this game, but of course it cannot compete with more sophisticated text editors like Visual Studio Code.

The game saves all code files as .py files, so you can edit them with Python editors. 
Note that this is for convenience only. The in-game language isn't actually Python, but it's close enough that Python IntelliSense works decently on it.
You can find the files in the [save folder](persistent_data_path/Saves).

Each save also contains a `__builtins__.py` file, which contains built-in Python definitions that match the in-game builtins to enable IntelliSense. 
The game will ignore pythons import statements, so you can add them to help your external editor pick up on function definitions from other files.

To see external changes in-game without having to reload the save, you must enable the "File Watcher" option. If you create or delete files externally, you will still need to reload the save to see them.

## Using VS Code
Visual Studio Code is the recommended code editor to use with The Farmer Was Replaced.

You can install it [here](https://code.visualstudio.com/download).

After downloading it, install the Python extension in VS Code.

Once you have that, open the [folder](persistent_data_path/Saves) that holds your `.py` files in VS Code. Make sure you open the whole folder, not just the individual files, otherwise the `__builtins__.py` file won't work.

The Python extension doesn't automatically import functions from other files like the game does. So to avoid getting "not defined" warnings in the editor when calling functions from other files, you will need to add the line

`from filename import *`

to the top of each file that calls the functions of that file (replace `filename` with the name of the file).
The game will ignore these statements.

In the game, make sure you have the "File Watcher" option turned on. Now, every time you save in VS Code, the changes will automatically show up in the game.

That's it! Now you can write your code in a professional code editor!