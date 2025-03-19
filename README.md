# FIrst-steps-in-JavaScript
performing training tasks for javascript training

# Intro

tasks based on the training program in MISIS. Will be performed based on the [pj5s website](https://editor.p5js.org/)

## 1. We display the inscription

command - conlsole.log("")

ready

![Screenshot_201](https://github.com/user-attachments/assets/ae508f67-5181-4056-a372-e10689fc18e7)

## 2. a simple comparison

command - "let"

let's compare 2 values - 10 and 2.5 by comparing - more or 2.5 than 10

ready

![Screenshot_202](https://github.com/user-attachments/assets/2ca46258-3334-48f7-a4c6-f43db32e25fb)

let's try using another command to shorten lines of code.

ready
![Screenshot_203](https://github.com/user-attachments/assets/14282c06-07da-4c96-b05f-37c0255da359)

## 3. The comparison operator is "are they equal"

first, let's try to compare 2 values - 100 and 100

ready

![Screenshot_204](https://github.com/user-attachments/assets/5628e521-4b5a-41d8-93f8-0830479a4fde)

let's try to compare "is x really not equal to y"

ready

![Screenshot_205](https://github.com/user-attachments/assets/832fb03c-5abd-4fa1-a78e-41162fda151e)

let's also try to add a comparison by data type and value: is 100 really equal to car?

ready

![Screenshot_207](https://github.com/user-attachments/assets/adab651b-1a8f-40f6-8a84-07c8d2659b93)

## 4. Prompt

let's try to display a query on the screen where you need to enter the text - "enter your name".

command - "prompt"

ready

![Screenshot_208](https://github.com/user-attachments/assets/b8a8b7c3-5671-4e10-bd3a-b2e3d13d2436)

let's complicate the query. let's try to calculate the age of the user by the year of birth. if he is 18 or older, we will welcome him, if less, we will send him home.

![Screenshot_209](https://github.com/user-attachments/assets/3da8f746-b3f1-4619-828a-fb74b79438e3)

Try-in:

var1

https://github.com/user-attachments/assets/d4d3e112-fa80-4bf5-94b7-fde2be5cb910

var2

https://github.com/user-attachments/assets/84f847c0-1352-45fe-8928-4e91a81b9f02

you can see the difference between the codes in option 1 and 2 - I wanted to prohibit the user from simply putting "enter" in response to the request. unfortunately, it didn't work out.

## 5. Conditional operator "If... else..."

Let's set a difficult condition: the user must enter a name if his age is greater than or equal to 18 and he has a job - welcome, in other options ("else") - we ask what he is doing here

code:
```
let name = prompt("Enter your name");
let birthYear = prompt("Enter your birth year");
let job = prompt("Do you have a job? Write Yes or No")
let age = 2025 - birthYear;
  if (age >= 18 && job == "Yes") {
    alert("Wellcome!");
  }
  else {
    let message = prompt("What do you do here?");
  }
```

Try-in

v1



https://github.com/user-attachments/assets/94dd2abb-6ca0-4aad-9168-7388f5b0c720

v2



https://github.com/user-attachments/assets/7b1561c2-4597-4996-a87a-ab79721e526b

## 6. Draw simple figures

let's try to place a circle on a background of a given size (300*300) and our chosen color in RGB format (we'll set the color by combining numbers in the RGB range - 250, 100, 50). We will take the diameter of the circle as 20. we will set the coordinates according to the coordinate grid in the picture below

![Screenshot_2](https://github.com/user-attachments/assets/34a08ddc-6ead-41ad-9aee-910a6182a667)

Code:
```
function setup() {
  createCanvas(300, 300);
}

function draw() {
  background(250, 100, 50);
  circle(50, 50, 20);
}
```
Ready

![Screenshot_3](https://github.com/user-attachments/assets/21cf1630-5122-4de6-82a1-b1d38053dc1c)

let's try to move the layer command higher than the circle drawing command. we will set as coordinates for the circle of cursor movement, using the commands "mouseX, mouseY"
```
function setup() {
  createCanvas(300, 300);
  background(250, 100, 50);
}

function draw() {
  
  circle(mouseX, mouseY, 20);
}
```
Result



https://github.com/user-attachments/assets/ee16e26d-24fd-4334-8a3b-5e2566458324

It turned out that the background was drawn 1 time (see the command above), and the circle is drawn many times, so the circle leaves a trace when moving.

however, we can remove the trace effect from the circle if we move or add the command describing the background to the same group as the command for drawing a circle. It turns out that every time the mouse moves, the program not only draws a circle in a new position, but also draws a new background on top of the old one, so that the circle leaves no traces when moving

```
function setup() {
  createCanvas(300, 300);
  
}

function draw() {
   background(250, 100, 50);
  circle(mouseX, mouseY, 20);

}
```



https://github.com/user-attachments/assets/0b9c927e-5a25-43e6-8466-2ae0e05e0098

Interestingly, if we move the team with the background below the team with the circle, but leave it in the same group, we will see only the background and not the circle, because the background is drawn on top of the circle and covers it.

```
function setup() {
  createCanvas(300, 300);
  
}

function draw() {
   circle(mouseX, mouseY, 20);
  background(250, 100, 50);
  

}
```

let's make the circle move to the right. to do this, we will make the horizontal coordinate (x) variable x = x +1;


```
let x = 0;
  function setup() {
  createCanvas(300, 300);
}

function draw() {
  background(250, 100, 50);
  circle(x, 20, 20);
    x = x +1;
}
```

Result



https://github.com/user-attachments/assets/89d3ac39-0b82-492d-8808-5761a2ed9d94

now let's try to make the circle go back when it reaches the edge of the canvas.

I tried to enter the "if/else" condition, but for some reason it didn't work here.

```
let x = 0;
  function setup() {
  createCanvas(300, 300);
}

function draw() {
  background(250, 100, 50);
  circle(x, 20, 20);
    if (x >= 0) {
    x = x +1;
  }
  else (x <= 300);
  x = x -1;
}
```

Let's try to draw a cross.

we need to break the cross into simple shapes that make up it - lines - and set them the xy coordinates of the beginning and end of each

```
function setup (){
  createCanvas(300,300);
}
function draw() {
  background(200);
  line(0, 0, 300, 300);
  line(0, 300, 300, 0);
}
```
![Screenshot_57](https://github.com/user-attachments/assets/b3519826-1268-4a87-9c6f-b8cbc1e85801)

This task can be done differently by drawing 4 straight lines.

```
function setup (){
  createCanvas(300,300);
}
function draw() {
  background(200);
  line(0, 0, 150, 150);
  line(0, 300, 150, 150);
  line(300, 0, 150, 150);
  line(300, 300, 150, 150);
}
```

the result will be the same

![Screenshot_57](https://github.com/user-attachments/assets/a3a409b6-9d36-49ed-a477-51739b57a254)

## Cycles

let's make a counter from 1 to 10

```
for (let i = 0; i <= 10; i = i +1){
  console.log(i);
}
```

Try-in



https://github.com/user-attachments/assets/fd7ab185-1e94-40ff-8ec8-fdde279ae605

now let's combine the counter with an earlier task: let the user himself lead up to what number the countdown will be.

```
let number = prompt("Enter the reference number");
for (let i = number; i >= 0; i = i -1) {
  console.log(i);
}
```

Try-in



https://github.com/user-attachments/assets/2b396ca2-57b6-41c7-88aa-7cf215b63b8e

Let's try to create a cross out of squares.

```
function setup () {
  createCanvas(400, 400);
  for (let i = 0; i <= 400; i = i + 40) {
  square (i,i,20);
  }
  for (let i = 0; i < 400; i = i + 40) {
  square (400 - i, i, 20);
  }
}
```

Try-in

![Screenshot_58](https://github.com/user-attachments/assets/ac9185a3-bd5d-4918-a35e-587d5ccf5ac6)

let's try to fill the entire canvas with color squares.

```
function setup () {
  createCanvas(400, 400);
  for (let i = 0; i < 400; i = i + 40) {
    for (let j = 0; j < 400; j = j + 40) {
  square (i,j,20);
      fill (200, 200, 50);
    }
}
}
```
![Screenshot_60](https://github.com/user-attachments/assets/922307b8-b9fa-4927-b285-28053094b7f3)

but here comes the problem - the top-left square is not filled in for some reason.

fill the canvas with colored squares of different sizes

```
function setup () {
  createCanvas(400, 400);
  for (let i = 0; i < 400; i = i + 40) {
    for (let j = 0; j < 400; j = j + 40) {
  square (i,j,(i + j)/30);
      fill (200, 200, (i + j)/3 );
    }
}
}
```

![Screenshot_61](https://github.com/user-attachments/assets/5d94fdb5-be86-4761-9391-48d2cf9998b4)

let's try to distribute the squares in a wave

```
function setup () {
  createCanvas(400, 400);
  for (let i = 0; i < 400; i = i + 40) {
    for (let j = 0; j < 400; j = j + 40) {
  square (i,sin(j)*100,(i + j)/30);
      fill (200, 200, (i + j)/3 );
    }
}
}
```

Something strange happened.

![Screenshot_62](https://github.com/user-attachments/assets/c87131b2-dbf9-49a6-a6e8-41d80dd5a372)


















  





