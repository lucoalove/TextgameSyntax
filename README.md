# Textgame Syntax

basically you display a scene, and its corresponding choices appear at the bottom. then when you select a choice it (depending on the choice's action) will append a new scene below the current one, and replace the choices with that scene's choices

actions can have multiple functions - changing the scene, modifying variables, etc.

Here is the contents of `my_scene.html` (assumes `another_scene.html` exists and variable `my_int` has been initialized)
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
