# Do Or Do Not

## Step 1
This program will create a https://magic-8ball.com/ style program for the Micro:bit.
Start out by getting rid of the **on start** and **forever** blocks - we'll only be using
the A button to start with.

Try out your program in the simulator as you go through the tutorial.


## Step 2
Drag in an **on button A pressed** block from the **Input** section.

Put **show icon**, **pause**, and then **clear screen** inside it.

This program will start out with only **yes** or **no** icons, so choose the tick
symbol from the icon, and change the pause to **500ms**.

```blocks
input.onButtonPressed(Button.A, function () {
    basic.showIcon(IconNames.Yes)
    basic.pause(500)
    basic.clearScreen()
})
```

## Step 3
That program only ever says **yes**, so the next step is to extend it to
choose between yes and no.

Drag in an **if-else** block from the **Logic** section, put a **show icon**
into the **if** part, and another into the **else** part, making one a tick
and the other a cross.

Put the **pause** and **clear screen** blocks *after* the end of the **if**
block. Try out the code.

```blocks
input.onButtonPressed(Button.A, function () {
    if (true) {
        basic.showIcon(IconNames.Yes)
    } else {
        basic.showIcon(IconNames.No)
    }
    basic.pause(500)
    basic.clearScreen()
})
```

## Step 4
Notice how the previous step only ever showed whatever you had in the **if**
part and not the **else** part? The choice is not a choice, it's always true!

Drag an **=** comparison block from the **Logic** section to replace the *true*,
and a **pick random** block from the **Math** section into the left side of that,
so that the block says *if **pick random 1 to 2** = **1***

```blocks
input.onButtonPressed(Button.A, function () {
    if (randint(1, 2) == 1) {
        basic.showIcon(IconNames.Yes)
    } else {
        basic.showIcon(IconNames.No)
    }
    basic.pause(500)
    basic.clearScreen()
})
```

## Step 5
This works fine for only two options, but the original Magic 8 Ball had 20!
We need to create a variable to store our random number, and then use that variable
in the **if** block, adding **else-if** sections to test more numbers.

**set** the variable at the top of the button press section to the random
number, and use the **+** button at the bottom of your **if** block to add
more options. **It's fine to have an empty *else* at the bottom.**

```blocks
input.onButtonPressed(Button.A, function () {
    let choice = randint(1,2)
    if (choice == 1) {
        basic.showIcon(IconNames.Yes)
    } else if (choice == 2) {
        basic.showIcon(IconNames.No)
    }
    basic.pause(500)
    basic.clearScreen()
})
```

## Step 6
Check your code to make sure it still works the same way!

## Step 7
Now add more options to your program. Remember that you need to change
the **pick random** number and the number of **else if** options as you add
more answers.

You can also show text instead of icons. Just replace the **show icon** block
with the **show text** block from the **Basic** section.

```blocks
input.onButtonPressed(Button.A, function () {
    let choice = randint(1,2)
    if (choice == 1) {
        basic.showString("Yes!")
    } else if (choice == 2) {
        basic.showString("No!")
    }
    basic.pause(500)
    basic.clearScreen()
})
```

## Step 8
You're done!

Try it out in the simulator, and then download it to a Micro:bit and make
sure it works on the real thing.

Check out the extension problems in OneNote if you have time.

