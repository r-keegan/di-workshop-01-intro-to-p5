# Workshop 1: Introducing JavaScript with P5.js

Collaborators: [your github username] & [your partners github username]

Make sure you’re working in pairs - on a single laptop. You’ll be **pair
programming**. In pair programming, there are two roles - **driver** and
**navigator**.

The **driver** is at the keyboard. They’re responsible for typing and figuring
out syntax. They shouldn’t make decisions though! That’s the responsibility of
the **navigator**. They make decisions, and ask the driver to implement them.

Start by forking this repo:
![fork button](https://readme-pics.s3.amazonaws.com/fork_button.jpg)

Forking creates a copy of this repo in your own GitHub account. Add your partner
as a collaborator by going to 'Settings' > 'Collaborators & teams' and entering
their GitHub username in the 'Collaborators' box. That means you'll both have
access to the repo.

You should now have a copy of this git repository in your own github account.
Now, we need to get a copy on our own laptop for us to work with. Start by
opening a terminal and creating a projects/ada folder if you don't already have
one:

```sh
cd Desktop
mkdir Projects
cd Projects
```

Next, we need to clone the repo. This copies all the files and history from
github to our own computer:

```sh
git clone https://github.com/<your github username>/di-workshop-01-intro-to-p5.git
cd di-workshop-01-intro-to-p5
```

You can see that it's a git repository and some of the history by running these
commands:

```sh
git status
git log
```

> **Note:** If you get stuck in `git log`, it's because you're in something
> called a pager. This is a really old bit of software from before computers
> could scroll in the way we're used to. You can move up and down in the pager
> with your arrow keys, and exit it by pressing `q`

Finally, we need to install some bits and pieces that in our new repo to finish
setting it up:

```sh
npm install
```

---

We’ll be working with some software called P5. P5 is a **JavaScript library**
for drawing shapes - it’s used for making simple games and cool generative art.

For each of the **bold** questions below:

<h3 align="center">
  🗣 Discuss &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
  👩‍💻 Change &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
  👀 Observe &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
  🔄 Repeat
</h3>

1. **🗣 Discuss** the question with your partner
1. **👩‍💻 Change the code** - what do you expect your changes to do?
1. **👀 Observe the results** - what happened when you ran your code? How did it
   differ from your expectations
1. **🔄 Repeat** - keep discussing, changing, and running the code until you
   feel you understand it

**The aim of this workshop is _exploration_, hopefully leading to
_understanding_. It’s really important that you _take your time_. The questions
below are _guidelines_, meant to prompt your _curiosity_. If you can’t answer a
question, use a search engine or ask someone nearby. Don’t move on until you
_fully understand_ what’s happening.**

**Explore and have fun! Be curious!**

# Setup

Now you've got the repo cloned and installed, we need to start it up:

```sh
npm start
```

This runs a web server - a little program that your browser can connect to so
that the files you write in this project can run in there. Now, when you visit
http://localhost:5000/, you'll see all your files right there.

Open the workshop folder in your editor. In VSCode, choose File > Open and
select the folder - _not any of the files inside it_. You should see all the
workshop files in the left-hand file pane.

Open this file - README.md - in your editor. Make notes in here about everything
you do. If you don't know the answer to a question, it's your job to experiment
with the code to see what you can find out.

# Sketch A

Open the `part-a` sketch in your browser, and open `part-a/sketch.js` in your
editor. The code in `sketch.js` is what's running on the page. Every time you
make a change in `sketch.js`, you need to save the file (ctrl-S or cmd-S) and
refresh your web browser (ctrl-r or cmd-r) to see the change.

---

Look at these lines:

```js
var r = 255
var g = 80
var b = 0
```

**What might these lines do?**
This sets the colour of the square to red.

**What happens if you change the numbers?**
This changes the colour of the square.

**What numbers are allowed / What numbers have an effect?**
Each channel (Red, Green, and Blue are each channels) is 8 bits, so they are each limited to 256, in this case 255 since 0 is included. 

Look at this line:

```js
createCanvas(400, 400)
```

**What does createCanvas do?**
 Creates a canvas element in the document, and sets the dimensions of it in pixels.

**What happens if you change the numbers?**
It changes the size of the canvas

**What numbers are allowed/what numbers have an effect?**
Maximum height/width: 32,767 pixels Maximum area: 268,435,456 pixels (e.g., 16,384 x 16,384)

**What happens if you add/remove a number?**
If you remove a number, the canvas disappears. If you add a number the canvas takes the first two numbers.

**Can you guess what the `function setup() {` part does? What happens if you
change the name of setup?**

Variables declared within setup() are not accessible within other functions, There can only be one setup() function for each program and it should not be called again after it's initial execution.

Look at this line:

```js
background(r, g, b)
```

**What does background do?**
Combines all the channels/variables of Red, Blue and Green to create a combined colour.

**What happens if you change the order of the letters in background? What does
this tell you about how the computer uses them?**
They change colour based on the order it is set. Meaning it must impliment them sequentially.

**What happens if you change the number of letters?**
It again changes the colour, but only up to 4.

**What happens if you change the letters for different ones?**
it either disappears, crashes or turns white.

# Sketch B

Open the `part-b` sketch in your browser, and open `part-b/sketch.js` in your
editor.

Read the code and play with the sketch in your browser.

> **Note**: There's two main sections in the code - the bit called `setup` and
> the bit called `draw`. The code in the `setup` section runs **once**, when
> your program first starts up. The code in the `draw` section runs again and
> again and again - 60 times every second.

Look at these lines:

```js
function setup() {
  createCanvas(400, 400)
  background(0, 0, 0)
}
```

**What does setup do?**
Variables declared within setup() are not accessible within other functions, There can only be one setup() function for each program and it should not be called again after it's initial execution.

**What do `{` `}` mean? What happens if you remove one?**
The program crashes

**What do the numbers in `background(0, 0, 0)` do? What happens when you change
them? How is this different from Sketch A?**
We are no longer setting the variables to red, green and blue. There is already a background function which will set the RGB when the numbers are specified.

Now look at these lines:

```js
function draw() {
  fill(255, 0, 0)
  ellipse(mouseX, mouseY, 30, 30)
}
```

**What does draw do?**
Called directly after setup(), the draw() function continuously executes the lines of code contained inside its block until the program is stopped

Now look at:

```js
fill(255, 0, 0)
```

**What do these numbers do? What happens when you change them?**
It allows you to set the colour of the draw shape

**What does fill mean? What happens if you change it to stroke?**
Stoke and fill are similar however, fill is an opqaue colour and stoke has just an outline of the preset colour.

**What happens if you remove (or comment out) this line? What about if you
include both fill and stroke on seperate lines?**
The colour defauklts ot white if commented out, the fill and stoke are set according to your RGB presets.

Now look at this line:

```js
ellipse(mouseX, mouseY, 30, 30)
```

**What does `ellipse` do?**
Sets the shape

**What happens if you change the numbers?**
It changes the size of the ellipse - elongates it, makes it smaller, etc.

**What do `mouseX` and `mouseY` mean?**
It is the coordinates of the mouse location on an X and Y plane.


**What happens if you change the order of the items between the `(` `)`?**
The planes are implemented sequentially causing the drawing with the mouse to look odd.
---

**What happens if you add `background(0)` after `draw() {`? Why?**

Replace the ellipse with a triangle. Use https://p5js.org/reference/ (the 2D
primitives section) to help.

Play around with the sketch - how else can you change it?

# Sketch C

Open the `part-c` sketch in your browser, and open `part-c/sketch.js` in your
editor.

Read the code, then play with the sketch and observe what happens - try clicking
the mouse on the sketch.

Look at:

```js
if (mouseIsPressed) {
  fill(255, 0, 0)
} else {
  fill(0, 255, 0)
}
```

**What does `mouseIsPressed` mean?**
The mousePressed variable stores whether or not a mouse button is currently being pressed.


**What happens if you change `mouseIsPressed` to `keyIsPressed`?** You’ll need
to click on the sketch so it registers keyboard events – use the ctrl key if you
have issues with the keyboard.
The keyIsPressed variable stores whether or not a key is currently being pressed.

**What does if / else do?**
Creates a true or false condition for the computer to execute.

**What happens if you remove the { } or ( )? Why?**
The program crashes.

**What happens if you change 255 to mouseX ? Why?**
It changes the colour of the draw shape based on the mouse location and the RGB co-ordinates.

**Remove the outline of the circle. Use Google and the P5.js reference to help
you.**

# Challenge

In your pairs, take the code in sketch c and adapt it into a simple paint
program. The user should be able

- click and drag to paint on the screen
- press keys on the keyboard to choose a colour
  - e.g. pressing ‘r’ changes the paint colour to red, pressing ‘g’ changes the
    paint colour to green.

Use this code as a starting point:

```js
if (keyIsPressed) {
  if (key == 'r') {
    // set paint colour to red
  }
  if (key == 'g') {
    // set paint colour to green
  }
  // add more keys/colours
}
```

**Document your process in this file.**

## Extension

- Change the shape of the brush (explore other shapes like squares or triangles)
  based on a key pressed
- Change the size of the brush based on a key pressed.
