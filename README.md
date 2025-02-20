# TextgameSyntax

Basically a Twine clone.

```
Int day = 1
Int energy = 5

Scene mall {
    ![A scene of a mall.](mall.jpg)

    It's day @(day).

    You enter through the sliding doors of the mall, busy as usual.

    ?(day == 10){Oh look, the food court opened today!}

    [Visit the food court.](food_court)
    [Visit the arcade.](arcade)
    [Visit the bank.](bank)
}

Logic food_court {
    energy--
    if (day >= 10):
        food_court_open
    else:
        food_court_closed
}
```

## Objects

**Scene objects** are what is displayed to the screen. They support markdown.

**Logic objects** are intermediaries between scene objects that can evaluate conditionals and update variables. If you don't specify a scene to redirect the player to, they will keep you on the same scene but reload it (in case any variables the scene relies on have updated).

## Variables

Char (which stores info on the character's name and text color)

## Special Markdown

**Dialogue:** `*my_char:"Dialogue of my character."` _Note that this will **not** include quotations when displayed._

**Variable embed:** `@(my_variable)` _Embedding a character will display their name in their color._

**Conditionals:** `?(my_variable == 10){This text will only be inserted if the statement evaluates to true.}`

**Links:** `[Click here to go to my scene!](my_scene)`

Links don't only lead to scenes. They can also tell to a logic object to evaluate or take in the **CONTINUE** keyword. This keyword specifies that the program should wait for you to click the link before inserting the rest of the document. Useful applications include:

```
You just kept [waiting...](CONTINUE) and [waiting...](CONTINUE) and [waiting...](CONTINUE) but in the end, no one showed up.
```

```
*stacy:"How's it going?" you hear a familiar voice call from behind you.

[Stacy!](CONTINUE)

*stacy:"Yea, it's me. Surprised?"
```
