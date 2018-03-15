# Gracious Test

A simple test application implementing a minimal REST (or RESTful) API for playing a game of hangman.

You are totally free to make this however you want, whatever framework you want, etc. This is just a simple skeleton.

This test is just to show off your abilities and skills, so go nuts :)

## API endpoints

```
1. [POST] /game/new              - create a new game
2. [GET]  /game/:id              - retrieve existing game data
3. [POST] /game/:id/:char        - guessed character for game with id :id
```

All endpoints return the same JSON game-data structure (assuming no errors were encountered).

### API parameters

#### :id

an integer value (i.e. the "game_id" value of an API JSON response)

#### :char

a single, lowercase letter between `a` and `z`


## API response data

all endpoints return the following JSON data structure (assuming no errors);

```json
{
    "game_id"     : <INTEGER>,
    "tries_left"  : <INTEGER>,
    "status"      : <STATUS>,
    "word"        : <WORD_STRING>
}
```

with the following logical replacements:

1. `<INTEGER>`        - an unsigned integer
2. `<STATUS>`         - one of the following string values: busy, fail, success
3. `<WORD_STRING>`    - a string representing the guessed word, unguessed letters are replaced by the `.` (period) character.

an example with real values:

```json
{
    "game_id"     : 1,
    "tries_left"  : 11,
    "status"      : "busy",
    "word"        : "...."
}
```

Example of an error message

```json
{
    "error"      : {
        "code"   : 400,
        "message": "Bad Request"
    }
}
```

## Docker

Dockerizing this test with a working Dockerfile and docker-compose.yml will earn you some extra points, but this is _not_ required nor expected 