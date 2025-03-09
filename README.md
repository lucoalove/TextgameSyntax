# Story Game Engine

actions can have multiple functions - changing the scene, modifying variables, etc.

Here is the contents of `my_scene.html` (assumes `another_scene.html` exists and variable `my_int` has been initialized)
```
<choices>
{
  prompt="Clicking this will append another_scene below this scene.",
  action="append_scene('another_scene');"
},
{
  prompt="Clicking this will clear all scenes that are currently displayed and display another_scene.",
  action="set_scene('another_scene');"
},
{
  prompt="You can only click this if action_condition evaluates to true (it will be grayed out otherwise). It will do nothing because action is empty.",
  action="",
  action_condition="my_int == 5"
},
{
  prompt="This button will only appear at all if prompt_condition evaluates to true. It will do nothing because action is empty.",
  action="",
  prompt_condition="my_int == 5"
}
</choices>

<p>You can put HTML code here.</p>
```
