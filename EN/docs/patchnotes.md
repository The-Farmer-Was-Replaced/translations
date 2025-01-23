# Patch Notes

Breaking Changes:
You'll have to change these in your code.

Functions defined in other files (windows in the game) are no longer imported implicitly. You now have to unlock and use explicit import statements like in Python (See the import unlock).

Breaking Changes from older Patches that you might have missed:
-`Items.Bones` has been renamed to `Items.Bone` so all items are singular.
-`Entities.Carrots` has been renamed to `Entities.Carrot` so all entities are singular.
-`Grounds.Turf` has been renamed to `Grounds.Grassland` to make it easier to understand.
-`Items.Water_Tank` has been renamed to `Items.Water` because the tank refill feature has been removed.
-`Unlocks.Benchmark` has been replaced with `Unlocks.Timing`.
-`get_op_count()` has been renamed to `get_tick_count()`.
-`set_farm_size()` has been renamed to `set_world_size()` to be consistent with `get_world_size()`.
-`get_companion()` now returns a tuple of the form (entity, (x, y)) instead of a list.
-`trade()` has been removed from the game.

Global Variabels:
-Scopes and global variable have been changed to work like in Python. This means you can now use the `global` keyword to write to the global scope.
-There is now an error for using a local variable before it was assigned locally even if there is a global variable with the same name.
-The shadowing error messages have been removed.

Imports:
The old import system automatically imported all functions from all files. This had the big disadvantage that global variables from other files could not be imported and were therefore inaccessible.
The new import system is a slightly simplified version of how imports work in Python. You can import a module using the `import file` or `from file import *` syntax.

Other Changes:
-Added `str()` function.
-Added destructuring support in for loops.
-Various docs changes.
-Fixed passing functions into simulations.
-Fixed using `in` and `not in` with functions.
-Fixed set function allowing lists as keys.