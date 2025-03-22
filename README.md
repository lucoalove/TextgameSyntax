# Textgame Syntax

Basically you display a scene, and its corresponding choices appear at the bottom. Then when you select a choice it runs some code; in most cases this will append a new scene below the current one, maybe change some variables, and replace the choices with the new scene's choices.

The syntax is split into two parts: **Functional code** and **markup code**.

## Markup code

Here is the contents of `my_scene.html` (assumes `another_scene.html` exists and variable `my_int` has been initialized):
```
<choices>
{
  prompt="Selecting this choice will append another_scene below this scene.",
  action="append_scene('another_scene');"
},
{
  prompt="Selecting this choice will clear all scenes that are currently displayed and display another_scene.",
  action="set_scene('another_scene');"
},
{
  prompt="You can only select this choice if action_condition evaluates to true (it will be grayed out otherwise). It will do nothing because action is empty.",
  action="",
  action_condition="my_int == 5"
},
{
  prompt="This choice will only appear at all if prompt_condition evaluates to true. It will do nothing because action is empty.",
  action="",
  prompt_condition="my_int == 5"
}
</choices>

<p>You can put HTML code here.</p>
```

Choices can contain the keys `prompt`, `action`, `prompt_condition`, and `action_condition` to determine how they display and their behaviour.
- `prompt` The text the choice will display with.
- `action` Code that runs if the choice is selected. Actions can do more than one thing - manipulate the scene (`append_scene`, `set_scene`, and `reload_scene`), modify variables, evaluate conditions, etc.
- `prompt_condition` A boolean statement - the choice will only appear if it evaluates to true, otherwise, the choice will not appear.
- `action_condition` A boolean statement - the choice will only be selectable if it evaluates to true, otherwise, the choice will be grayed out.

What hasn't been planned is dynamic scene content (i.e. having the same layout for 10 different random encounters).

## Functional code

The stuff inside `action` and stuff
