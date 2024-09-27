# Mazes
If you use fertilizer on a full-grown bush, it will grow into a maze of hedges with a 10% probability. For some reason the drone can't fly over the hedges, even though they don't look that high.

There is a treasure hidden somewhere in the hedge. Use `harvest()` on the treasure to receive gold equal to the area of the maze. (For example, a 5x5 maze will yield 25 gold.)

If you use `harvest()` anywhere else the maze will simply disappear.

`get_entity_type()` is equal to `Entities.Treasure` if the drone is over the treasure and `Entities.Hedge` everywhere else in the maze.

Mazes do not contain any loops unless you reuse the maze (see below how to reuse a maze). So there is no way for the drone to end up in the same position again without going back.

You can check if there is a wall by trying to move through it. 
`move()` returns `True` if it succeeded and `False` otherwise.

If you have no idea how to get to the treasure, take a look at Hint 1. It shows you how to approach a problem like this.


For an extra challenge you can also reuse the maze by using fertilizer on the treasure. 
This has a 10% probability of increasing the treasure by one full maze and moving it to a random position in the maze.
Using `measure()` on a treasure returns the position it will go to next as a tuple `(x_position, y_position)`.

For example, while above the treasure, the following code gives you the position where the treasure will be after you fertilize it:
`next_x, next_y = measure()`

Each time the treasure is relocated a random wall may be removed from the maze. So reused mazes can contain loops.

Note that loops in the maze make it much more difficult so if you are a beginner you may not want to reuse mazes. Reusing mazes doesn't give you more gold than spawning a new maze. It's only worth it if the extra information and the shortcuts help you solve the maze faster.

The same maze can be solved a maximum of 300 times. This corresponds to 299 relocations. After that, fertilizing the treasure won't have any effect anymore.

<spoiler=show hint 1>Here's a general approach to solving the problem:

Create a maze and imagine that you are the drone.

Think about how you would try to find the treasure if you were in the maze.

Write down your strategy step by step so that someone else could follow it without thinking.

Now try translating your steps into code.
</spoiler>
<spoiler=show hint 2>For mazes without cycles: All the walls are really just one large connected wall. If you follow the wall, it will lead you through the whole maze.</spoiler>
<spoiler=show hint 3>It may be useful to keep track of the direction the drone is facing so you can make left and right turns. The drone never actually rotates, but you can still keep a "virtual" rotation in code.
The following index trick could be helpful for this:

`directions = [North, East, South, West]
index = 0`

`# rotate right`
`# the % 4 makes it wrap around
index = (index + 1) % 4`

`# rotate left
index = (index - 1) % 4

move(directions[index])`</spoiler>
<spoiler=show hint 4>If you can't solve it, you can always make your life easy and do it less efficiently. 
You don't have to be able to reach the treasure every time, you can always harvest and spawn a new maze.
There is even a small chance that the treasure will appear right under the drone when you create a maze.</spoiler>