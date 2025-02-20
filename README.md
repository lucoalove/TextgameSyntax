# TextgameSyntax

Scene objects support markdown.

```
Scene mall {
    The mall, busy as usual. [day == 10|Oh look, the food court opened today!]

    [Visit the food court.|food_court]
}

Logic food_court {
    if (day >= 10):
        goto food_court_open
    else:
        goto food_court_closed
}
```
