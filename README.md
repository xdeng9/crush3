# Crush 3
[Play it here](http://joedeng.me/crush3/)

Crush 3 is an interactive single player game inspired by Candy Crush. There's an added bonus game which can be unlocked after the player reach certain level in the game.

<img src="https://github.com/xdeng9/crush3/blob/master/images/crush3-demo.gif" />

## Technologies
- Vanilla JavaScript
- CSS
- HTML

### Check for matches
```Javascript
function checkColMatch() {
        let matchedCells = [];
        for (let i = 0; i < width; i++) {
            for (let j = i; j < width * (width - 1) + i; j+= width) {
                if (cells[j].style.backgroundImage === cells[j + width].style.backgroundImage) {
                    if (matchedCells.length === 0) {
                        matchedCells.push(j);
                        matchedCells.push(j + width);
                    } else matchedCells.push(j + width);

                    if (j + width === width * (width - 1) + i && matchedCells.length >= 3) {
                        for (let cell of matchedCells) cells[cell].style.backgroundImage = '';
                        score += matchedCells.length;
                    }
                } else {
                    if (matchedCells.length >= 3) {
                        for (let cell of matchedCells) cells[cell].style.backgroundImage = '';
                        score += matchedCells.length;
                    }
                    matchedCells = [];
                }
            }
            matchedCells = [];
        } 
    }

    function checkRowMatch() {
        let matchedCells = [];
        for (let i = 1; i < width * width; i++) {
            if (cells[i].style.backgroundImage === cells[i - 1].style.backgroundImage
                && Math.floor(i / width) === Math.floor((i - 1) / width)) {
                    if (matchedCells.length === 0) {
                        matchedCells.push(i - 1);
                        matchedCells.push(i);
                    } else matchedCells.push(i);
                } else {
                    if (matchedCells.length >= 3) {
                        for (let cell of matchedCells) cells[cell].style.backgroundImage = '';
                        score += matchedCells.length;
                    }
                    matchedCells = [];
                }
        }
```



