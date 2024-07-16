## step 1

html, create the buttons heading and all that

## step 2

link all the sheets and find some rest css code

## step 3

create a function to populate the sketch board.

a parameter of size is added the the function so that the size of the board can be changed dependent on what the user enters into the set size input box

```js
function populateBoard(size) {
  let board = document.querySelector(".board");
  board.style.gridTemplateColumns = `repeat(${size}, 1fr)`;
  board.style.gridTemplateRows = `repeat(${size}, 1fr)`;

  for (let i = 0; i < 256; i++) {
    //256 is 16*16
    let square = document.createElement("div");
    square.style.backgroundColor = "blue";
    board.insertAdjacentElement("beforeend", square);
  }
}
```

## step 4

the function changeSize(input) is created with param of input. the funcion is then called in the html input section, so when a number is entered into the input box, it will change the amount of square that populare the sketch pad

```js
populateBoard(16);

function changeSize(input) {
  populateBoard(input);
}
```

<input
            type="text"
            placeholder="Size of Board"
            value="16"
            onchange="changeSize(this.value)"
          />

## step 5

this section of code is added to the function in step three

```js
let squares = board.querySelectorAll("div");
squares.forEach((div) => div.remove());
```

before this code was added we had as problem with teh divs not filling the sketch box area when the user entered a new value

then this line of code was added before the for loop. and the code below that was an edit to the populateBoard function

```js
let amount = size * size;
```

    ```js
    for (let i = 0; i < amount; i++){}
    ```

## step 6

The game would tend to crash when the user put a number within the input that was too large, so i added a fuction to make sure that the amount of squares staye between 2 and 100

```js
function changeSize(input) {
  if (input >= 2 && input <= 100) {
    populateBoard(input);
  } else {
    console.log("too many squares");
  }
}
```

## step 7

Next i added an event listener to the for loop, saying that when the mouse passes over a box, it is filled in black. So essentially we are drawing

```js
square.addEventListener("mouseover", () => {
  square.style.backgroundColor = "black";
});
```

## step 8

The next step is to make the other buttons on the page function, first i tackled the reset button. a couple lines of code were reused from the populateBoard function:

```js
resetBtn.addEventListener("click", function () {
  let board = document.querySelector(".board");
  let squares = board.querySelectorAll("div");
  squares.forEach((div) => (div.style.backgroundColor = "white"));
});
```

## step 9

## step 10

## step 11

## step 12

## step 13

## step 14

## step 15

## step 16

## step 17

## step 18

## step 19

## step 20
