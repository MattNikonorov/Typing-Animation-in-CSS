# Create A Typewriter Effect for Your Website in Pure CSS

#### In this article, you'll learn how to make your website's text dynamic and more engaging using typewriter animations in pure CSS!

***********
##### First of all, why typewriter animations?

Answer: **It makes your website more engaging to visitors.**
For example, here's a snapshot of a personal portfolio template I made recently:
![Typing animation in action](https://github.com/MattNikonorov/Typing-Animation-in-CSS/blob/main/typewriter.gif)

As you can see, I've added the typewriter effect to this website instead of plain text.
What I've found is that adding typewriter effects to chunks of your text makes your website's visitors more engaged and interested in reading further.

************

## Let's make the typewriter animation!

The typewriter animation is easy to make and all you will need to have in order to make sense of this tutorial and this animation is basic knowledge of CSS and CSS animations.

Here's the way the typewriter animation is going to work:
* The "typing" animation is going to reveal our text element by changing it's width from 0 to 40%, step by step, using the CSS step() function.
* The "blink" animation is going to create the cursor.

Before making the animation, let's create the webpage and div element which we want to have the typewriter effect:
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
* An **"overflow: hidden;"** property to make sure the text content isn't revealed until the typewriter animation has started.
* A **"border-right: .15em solid orange;"** property to create the typewriter cursor.
* An **"animation"** property which will later be contained with the typewriter animation, as well as the typewriter cursor animation.

### Adding steps to the animation to add a typewriter effect
Here I will be introducing the reader to the CSS "steps()" function, how to use it and how to add the right amount of steps to your typewriter animation based on the length of your text element, and how The longer the text the more steps are needed and vice-versa. 
I will also share an easy way to calculate the amount of steps needed for the typewriter animation based on the length of the text.
![Long text animation](https://github.com/MattNikonorov/Typing-Animation-in-CSS/blob/main/long-text.gif)

![Short text animation](https://github.com/MattNikonorov/Typing-Animation-in-CSS/blob/main/short-text.gif)


### Making the typewriter cursor animation
Here I will be explaining and demonstraiting how to make the typewriter cursor animation, as well as how to style it.
This is going to be essential for creating the typewriter effect and give the text the feeling of being typed.
![Blink caret animation](https://github.com/MattNikonorov/Typing-Animation-in-CSS/blob/main/blink-caret.gif)

### Combining everything
Here I will be demonstrating the end result and the full code of the typewriter animation, along with full code of some practical applications of the typewriter effect like: demonstrating code, SaaS landing pages and personal portfolios.
![Short text animation](https://github.com/MattNikonorov/Typing-Animation-in-CSS/blob/main/short-text.gif)
https://codepen.io/matveynikon/pen/RwgGRab
