# Crush 3
[Play it here](http://joedeng.me/crush3/)

Crush 3 is an interactive single player game inspired by Candy Crush. There's an added bonus game which can be unlocked after the player reach certain level in the game.

## Technologies
- Vanilla JavaScript
- CSS
- HTML

<img src="https://github.com/xdeng9/crush3/blob/master/images/crush3-demo.gif" />

```JavaScript
function haveMatch(index) {

        ...
        
        while (pos >= 0 && Math.floor(pos / width) === row) {
            if (cells[pos].style.backgroundImage === image)
                count++;
            else break;
            pos--;
        }
        if (count >= 3) return true;

        ...

        return false;
    }
```
