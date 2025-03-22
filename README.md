# Textgame Syntax

https://en.wikipedia.org/wiki/Hypertext_fiction

All game data is stored in the url as media queries, ex. `https:/example.com/?scene=my_scene&hp=10`. This makes it trivial to save/share gamestates, debug, and cheat.

Basically you display a scene, and its corresponding choices appear at the bottom. Then when you select a choice it runs some code; in most cases this will change the scene, maybe change some variables, and replace the choices with the new scene's choices.

The syntax is split into two parts: **Functional code** and **markup code**.

## Markup code

Here is the contents of `my_scene.html` (assumes `another_scene.html` exists and variable `my_int` has been initialized):
```
<choice>
  PROMPT: Selecting this choice will append another_scene below this scene.
  THATDOES: load_scene('another_scene');
</choice>

<choice>
  PROMPT (my_int > 10):
    This choice 1) will only appear if the first IF evaluates to true and
    2) can only be selected if the second IF evaluates to true (it will
    be grayed out otherwise). It will do nothing because THATDOES is empty.
  THATDOES (my_int == 15):
</choice>

<p>You can put HTML code here.</p>
```

Choices must contain a `PROMPT` and a `THATDOES` keyword, and optionally a boolean expression for either (or both) to determine how the prompt displays and its behaviour.
- `PROMPT` The text the choice will display with.
  - If provided a boolean expression, the choice will only appear if it evaluates to true, otherwise, the choice will not appear.
- `THATDOES` Code that runs if the choice is selected.
  - If provided a boolean expression, the choice will only be selectable if it evaluates to true, otherwise, the choice will be grayed out.

What hasn't been planned is dynamic scene content (ie. displaying variables or displaying different content within a scene depending on the value of an expression).

## Functional code

The stuff inside `THATDOES` and also boolean expressions

can manipulate scenes, modify variables, evaluate conditions, etc.

### Built-in functions

`load_scene(scene_name)` / Changes the scene that is displayed to the given scene.

`reload_scene()` / Reloads the current scene. Has the same effect as calling `load_scene` with the current scene as the parameter.
