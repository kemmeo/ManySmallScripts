# Many Small Scripts

  

#### A collection of small Javascript snippets that I use for Canvas & Math.

  

<img  src="https://i.imgur.com/OXoWcya.png"  style="display:block;margin:0 auto;">

#

### Importing Scripts

Add the following to your JS file, to import all MSS functions:
```js
import {*} from "https://raw.githubusercontent.com/kemmeo/ManySmallScripts/master/mss.js"
```

You can also import specific functions like this:
```js
import {lerp,clamp}; from "https://raw.githubusercontent.com/kemmeo/ManySmallScripts/master/mss.js";
```
*This will import the lerp and clamp functions.*

>NOTE
- To import MSS Scripts you must add `type="module"` to your html script tag.
- Chrome won't let you import from local files, so test local modules with firefox.

#

### Clamp()

Prevent a variable from going beyond a min and max value.

  

```js

// clamp num between min & max

function  clamp(num,min,max){

return  Math.max(min,Math.min(num,max));

}

```

  

##### Example

  

```js

// prevents object's x position from going outside of canvas

object.x=clamp(object.x,0,ctx.canvas.width);

```

  #

### iRandom()

  

Generates a random integer between a max & a min value. Originally by [Coding Math.](https://www.youtube.com/user/codingmath)

  

```js

function  iRandom(min,max){

return  Math.floor(min+Math.random()*(max-min+1));

}

```

  

##### Example

  

```js

// sets object's x position to a random whole number

object.x=iRandom(0,ctx.canvas.width);

```

  #

### Lerp()

  

Linearly interpolates between 2 numbers.

  

```js

// move "origin" towards "goal" at "rate"

function  lerp(origin,goal,rate) {

return  origin+=(goal-origin)*rate;

}

```

  

##### Example

  

```js

/* move object's x position towards the center of the canvas

While making sure it cannot go outside the canvas*/

  

object.x=clamp(lerp(object.x,ctx.canvas.width/2,0.8),0,ctx.canvas.width);

```

  #

### Gap()

  

Gets the distance between 2 objects, based on their x & y positions

  

```js

// requires that the 2 objects have x & y properties specified

return  Math.hypot(a.x-b.x,a.y-b.y);

```

  

##### Example

  

```js

// checks if enemy & player objects are colliding

if(gap(enemy,player)<=(enemy.radius+player.radius)){

console.log("collision detected");

}

```

  #

### Within()

  
  

Checks if a number is between a min & max value

  

```js

// returns a boolean

function  within(value,min,max){

if(value>=min&&value<=max){return  true;}

else{return  false;}

}

```

  

##### Example

  

```js

let  num=5;

if(within(num,1,10)){

console.log("number is within 1 & 10");

}

```

  #

### Smoothing()

  

Rounds lines and values to make your canvas look overall more crisp

  

```js

// mock antialiasing

function  smoothing(){

c.translate(.5,.5);

c.lineWidth=.5;

}

```

  

##### Example

  

```js

// define and call this function before you draw anything

Smoothing();

```

  #
  

And that's all for now!