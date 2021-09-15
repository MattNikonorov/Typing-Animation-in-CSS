# Create A Typewriter Effect for Your Website in Pure CSS

#### In this article, you'll learn how to make your website's text dynamic and more engaging using typewriter animations in pure CSS!

What I've found is that adding typewriter effects to chunks of your text makes your website's visitors more engaged and interested in reading further.
The typewriter effect can be used for many purposes such as making engaging landing pages, call to action elements, personal websites or code demonstrations

************

## Let's create the typewriter effect!

The typewriter animation is easy to make and all you will need to have in order to make sense of this tutorial and this animation is basic knowledge of CSS and CSS animations.

Here's the way the typewriter effect is going to work:
* The "typing" animation is going to reveal our text element by changing it's width from 0 to 16%, step by step, using the CSS "step()" function.
* The "blink" animation is going to create the cursor that will "type out" our text element.

Before making the animation, let's create the webpage, along with the div that will contain the "typed-out" class, this class is the one that we want to display the typewriter effect:
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


### Styling the element that we want to display the typewriter effect

Now that we have the layout of the webpage, let's style the "typed-out" class by giving it these properties:
```
    .typed-out{
        overflow: hidden;
        border-right: .15em solid orange;
        font-size: 25px;
        width: 0;
    }
```
Note that in order for the typewriter effect to work, we've added
* An **"overflow: hidden;"** and a **"width: 0;"** property to make sure the text content isn't revealed until the typewriter animation has started.
* A **"border-right: .15em solid orange;"** property to create the typewriter cursor.

### Making the typing animation
The typing animation is going to create the effect of the text inside the div containing the "typed-out" class being typed out letter by letter:
```
    @keyframes typing {
      from { width: 0 }
      to { width: 16% }
    }
```
As you can see, all it does is change an element's width from 0 to 16%.
You will need to adjust the target width of this animation based on the length of your text element, but I'll get to that in a bit.

Now if you include this animation in your "typed-out" class and set it's animation direction to "forwards" to make sure the text element won't go
back to "width: 0" after the animation has finished:
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
You're text element will simply be revealed in one smooth step, from left to right:

https://codepen.io/matveynikon/pen/OJggJGG 

#### Adding steps to the typing animation to achieve a typewriter effect

This is obviously not what a typewriter effect looks like.
To make this animation reveal our text element in steps, the way a typewriter would, we have to split the "typing" animation included by the "typed-out" class into steps in order for it to look like it's being typed-out:
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
    @keyframes blink {
      from { border-color: transparent }
      to { border-color: orange; }
    }
```
This will change the border color of the "typed-out" element's border, which is used as a cursor for the typewriter effect, from transparent to orange.
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
          blink .8s infinite;
    }
```
https://codepen.io/matveynikon/pen/wveeBgB

You can make the cursor thinner or thicker by adjusting it's `border-right: .15em solid orange;` property, or you can make the cursor a different color, border-radius, frequency of the cursor blinking effect, there's a lot of possibilities!
https://codepen.io/matveynikon/pen/MWovWdw

You can experiment with these properties inside the codepen and see what you can do!

### Combining everything

Now that you know how to make the typewriter animation in pure CSS and how the typing animation works, it's time for me to demonstrate some practical and relevant use cases of the typewriter effect.

**Personal portfolios**

https://codepen.io/matveynikon/pen/dyRoqmr

Typewriter effects make your web-resume/personal website stand out, and make it more engaging.

*************

**API landing pages**

https://codepen.io/matveynikon/pen/powWNYa

It's likely that at some point in your development journey, you came across an API provider landing page and saw a code-block like that, demonstrating the implementation of their API. I personally find this a really practical and relevant implementation of the typewriter effect, and find that it looks more attractive and inviting than a static chunk of code.

*************

**SaaS/product landing pages**

https://codepen.io/matveynikon/pen/qBjPRWe

I found that typewriter effects inside SaaS or Product landing pages are more inviting and engaging to visitors looking to use their products or services.
As someone who spent a lot of time developing Web Services and Web Apps, I can say from experience that typing effects are a definite win when it comes to building a unique and engaging landing page. The typed out "Get started today" at the end is a call to action that also implements the typewriter effect, and unlike most static call to action elements, it is only displayed after the visitor's attention is focused on the previous typed out elements pointing out the different use cases and implementations of "RandomSaaS".
************

## Conclusion
That's it for this tutorial!

I hope that at this point you know how to make, style, and implement the typewriter effect to make your webpages more engaging to visitors, as well as to show-off
your web design skills ;)
