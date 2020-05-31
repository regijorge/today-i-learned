# Cursor

## SORT
[Ref](https://docs.mongodb.com/manual/reference/method/cursor.sort/)

### Ascending/Descending
#### Ascending
    <CURSOR>().sort(<KEY_PATH>: 1)

#### Descending
    <CURSOR>().sort(<KEY_PATH>: -1)

## SKIP (offset)
    <CURSOR>().skip(<NUMBER>)

## LIMIT
    <CURSOR>().limit(<NUMBER>)
