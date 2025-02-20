# TextgameSyntax

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

**Scene objects** support markdown.

If **logic objects** don't specify a scene to redirect you to, they will keep you on the same scene but reload it (in case any variables the scene relies on have updated).

## Variables

Char (which stores info on the character's name and text color)

## Markdown

The **CONTINUE** keyword specifies that the program should wait for you to click its link before inserting the rest of the document. Useful applications include:

```
You just kept [waiting...](CONTINUE) and [waiting...](CONTINUE) and [waiting...](CONTINUE) but in the end, no one showed up.
```

```
*(stacy)"How's it going?" You hear a familiar voice call from behind you.

[Stacy!](CONTINUE)

*(stacy)"Yea, it's me. Surprised?"
```
