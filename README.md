# Create A Typewriter Effect for Your Website in Pure CSS

#### In this article, you'll learn how to make your website's text dynamic and more engaging using typewriter animations in pure CSS!

***********
##### First of all, why typewriter animations?

Answer: **It makes your website more engaging to visitors.**
For example, here's a snapshot of a personal portfolio template I made recently:

As you can see, I've added the typewriter effect to this website instead of plain text.
What I've found is that adding typewriter effects to chunks of your text makes your website's visitors more engaged and interested in reading further.

************

## Let's make the typewriter animation!

The typewriter animation is easy to make and all you will need to have in order to make sense of this tutorial and this animation is basic knowledge of CSS and CSS animations.

Here's the way the typewriter effect is going to work:
* The "typing" animation is going to reveal our text element by changing it's width from 0 to 40%, step by step, using the CSS "step()" function.
* The "blink" animation is going to create the cursor that will "type out" our text element.

Before making the animation, let's create the webpage along with div "typed-out" which we want to have the typewriter effect:
```
<!doctype html>
<html>
  <head>
    <meta charset="UTF-8">
    <title>Matt's portfolio</title>
  <style>
    body{
      background: navajowhite;
      height: 100%;
      background-size: cover;
      font-family: 'Trebuchet MS', sans-serif; 
    }
  </style>
  </head>
  <body>
      <h1>I'm Matt, I'm a</h1>
      <div class="typed-out">Web Developer</div>
  </body>
</html>
```


### Styling the text element which we want to have the typewriter effect

Now that we have the layout of the webpage, let's style the "typed-out" class by first giving it these properties:
```
    .typed-out{
        overflow: hidden;
        border-right: .15em solid orange;
        font-size: 25px;
        width: 0;
    }
```
Note that in order for the typewriter effect to work, we've added
* An **"overflow: hidden;"** and a **width: 0;** property to make sure the text content isn't revealed until the typewriter animation has started.
* A **"border-right: .15em solid orange;"** property to create the typewriter cursor.

### Making the typewriter animation
The typewriter animation is simply:
```
    @keyframes typing {
      from { width: 0 }
      to { width: 16% }
    }
```
As you can see, all it does is change an element's width from 0 to 16%.
Now if you include this animation in your "typed-out" class:
```
    .typed-out{
        overflow: hidden;
        border-right: .15em solid orange;
        white-space: nowrap;
        font-size: 25px;
        width: 0;
        animation: 
          typing 1s forwards,
    }
```
You're text element will simply be revealed in one smooth step:
https://codepen.io/matveynikon/pen/OJggJGG 

#### Adding steps to the animation to add a typewriter effect
This is obviously not what a typewriter effect looks like.
To make this animation reveal our text element in steps, the way a typewriter would, we have to split the "typing" animation included by the "typed-out" class into steps in order for it to look like a typewriter effect:
```
    .typed-out{
        overflow: hidden;
        border-right: .15em solid orange;
        white-space: nowrap;
        font-size: 25px;
        width: 0;
        animation: 
          typing 1s steps(20, end) forwards;
    }
```
As you can see, we've split the "typing" animation into 20 steps using the CSS "steps()" function, neat right!

Now that's more like it:
https://codepen.io/matveynikon/pen/oNwwgNd

Depending on the length of the text element, you will need to adjust the steps, duration, and target width of the "typing" animation accordingly.
For example, if we change the text from "web developer" to a longer string of text like "a web developer making unique web apps and designs", change the target width property of the "typing" animation to 58%, and the duration of the "typing" animation to 2.5s instead 1s, you'll see that the typewriter effect also works with longer pieces of text:
https://codepen.io/matveynikon/pen/GREvKMZ

Intuitevely, to adjust for shorter strings of text, we will need to decrease the steps, duration, and target width of the "typing" animation:
https://codepen.io/matveynikon/pen/mdwMdmB

### Making and styling the typewriter cursor animation
As you might have noticed, the orange cursor did not blink the way it would on a typewriter.
To fix this, create the "blink" animation:
```
    @keyframes blinking {
      from { border-color: transparent }
      to { border-color: orange; }
    }
```
This will change the border color of the "typed-out" element's border, which in our case serves the purpose of being a cursor.
Include this animation in the "typed-out" class and set it's animation direction property to infinite to make the cursor disappear and reappear every .8s forever.
```
    .typed-out{
        overflow: hidden;
        border-right: .15em solid orange;
        white-space: nowrap;
        font-size: 25px;
        width: 0;
        animation: 
          typing 1s steps(20, end) forwards,
          blinking .8s infinite;
    }
```
https://codepen.io/matveynikon/pen/wveeBgB

### Combining everything
Here I will be demonstrating the end result and the full code of the typewriter animation, along with full code of some practical applications of the typewriter effect like: demonstrating code, SaaS landing pages and personal portfolios.
https://codepen.io/matveynikon/pen/RwgGRab
