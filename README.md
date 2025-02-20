# TextgameSyntax

Scene objects support markdown.

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
