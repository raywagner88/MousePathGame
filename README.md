# MousePathGame

One last 'project' for practicing events, loops and functions before moving on to new material!

## General Overview

When the page loads, there should be lots randomly generated boxes on the page on a single color (red) and have one box be a different color (blue). The goal of the game is to navigate your cursor around all of the same red boxes and hover over the single blue box.

## Basic Technical Goals

- Generate a random number between 0 and `n - 1` to act as our "special box" index and save in variable for `specialBoxIndex`
- Will need to have a function called placeRandomBoxes() that creates `n` new divs, gives them a CSS class of `box`, generates two random numbers for their X and Y positioning and appends them to the page.
- In the loop of placing the random boxes, check to see if `i == specialBoxIndex`. If it is, add classes `box specialBox`. If not, just add `box`.
- Also in the loop, we will need to add event listeners to the box
  - if it is the special box, a `mouseover` event should be listened to and call a function `winGame()`.
  - If its a normal box, attach an event listener to the same event and call a function `loseGame()`.
- Create a function called `removeEventListeners`. In the function, grab all elements with the class of `box`, loop through them and remove both the `winGame` and `loseGame` event listeners from the elements.
- Call the `removeEventListeners` function inside of `winGame()` and `loseGame()` to make sure the game is unplayable when a result is reached.
- Both winning and losing should cause an alert to appear letting you know the result of the game.

## Extended Technical Goals
- Instead of `divs` use images.
- Replace the alerts with `div` modals. Make the divs part of your HTML but set them to `display: none` in your CSS. Then, when `winGame` or `loseGame` is called, you can grab the modal by an ID and set the `display` to block.
- Add buttons inside of these modals that, when clicked, reload the page using `location.reload()`.

## Advanced Technical Goals
- On page load, start a timer that updates the screen to let the user know how many seconds have gone by during the game.
- Save high scores in `localStorage` and display on screen.
  - When the game ends, check to see if completed time is better than the stored high score
    - If it is, update the saved value in storage
- Add 'Jeopardy' music that plays in the background
- Allow the users to select from different difficulties
  - Toggle a variable that will be used as the amount of boxes to inject into the page
    - I.E. easy = 100 boxes, medium = 250, hard = 500
