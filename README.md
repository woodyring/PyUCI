PyUCI
=====

The Python UCI Chess Engine Interface (PUCEI or PyUCI) allows communication with a UCI-enabled chess engine from Python 2.x

In very early stages of development.

Here is an example where we make Stockfish play itself: (see rungame.py)

```Python
from gameSession import GameSession
from engine import Engine

stockfishpath = './Stockfish/src/stockfish'
eng1 = Engine(stockfishpath)
eng2 = Engine(stockfishpath)

gamesesh = GameSession(eng1,eng2).play()
```

If we want the engine to play a timed game, we can use ```time=(start_time,increment)```,
where all times are in milliseconds, following the UCI standard.

```Python
#Make the clock start at 5 minutes and increment the clock by 5 seconds after each turn.
GameSession(eng1,eng2,time=(300e3,5e3)).play()
```    

or perhaps, for cleaner syntax, use minutes and seconds for the starting time
and increment time, respectively.
```Python
GameSession(eng1,eng2,time=(5,5),time_unit='minsec').play()
```

##TODO:

* Documentation
* Comprehensive testing
* (... more stuff)

###Option integration for full UCI-standard compliance.
* Implementation of safety features for engine crashes (isready, ect.)
* Pondering
* Initizlization set options (to engine)

###Done:
* ~~Make thing to allow use of seconds as time.~~
* ~~Recognise tie games.~~
* ~~Add non-unix support.~~
