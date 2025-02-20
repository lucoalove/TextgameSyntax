# TextgameSyntax

Scene objects support markdown.

If logic elements don't specify a scene to redirect you to, they will keep you on the same scene but reload it (so that any values the scene relies on can be updated).

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
