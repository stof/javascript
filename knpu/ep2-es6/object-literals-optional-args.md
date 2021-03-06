# Object Literals & Optional Args

When it comes to functions and arrays, ES2015 has a couple of things you
are going to love! Well, some of this stuff might look weird at first... but then
you will love them!

## Object Keys... without the Key

Start in `_saveRepLog`. Right now, we're passing `$.ajax` some options: `url`, `method`
and `data`. Above that line, create a new `url` variable set to the URL. Then,
use that below.

Obviously, this will work *exactly* like before: nothing interesting yet. Well, in
ES2015, if your key and your value are the same, you can just leave off the key.

Yep, this means the same thing as before. So if you suddenly see an associative array
or object where one of its keys is missing... well, it *is* the key... and the value.

## Short Method Syntax

Next, you can do something similar with methods inside an object. The `loadRepLogs()`
method is just a `loadRepLogs` key assigned to a function. Simple, but too much work,
maybe? In ES2015, we can shorten this to `loadRepLogs()`.

So much cooler! Let's change it everywhere! Search for the word `function`, because
almost everything is about to change. Ultimately, the *only* function keywords that
will be left are for the self-executing function - which could be an arrow function -
and the two constructors. Nice!

## Optional Args

Ready for one more cool thing? This one is easy. Suppose we have a new method, not
`calculateTotalWeight()`, but `getTotalWeightString()`. Use the new shorthand syntax
and return `this.calculateTotalWeight()` and append "pounds" to it.

Perfect! Then above, in `updateTotalWeightLifted()`, instead of calling `calculateTotalWeight()`
and passing that to `.html()`, pass `getTotalWeightString()`.

Ok, nothing too crazy so far: when we refresh, at the bottom, yep, "pounds".

But now suppose that we want to set a *max* weight on that. What I mean is,
if we are over a certain weight - maybe 500 - instead of printing the actual total,
we want to print "500+"

Start by adding a new argument called `maxWeight`. Then say `let weight = this.calculateTotalWeight()`.
And if `weight > maxWeight`, add `weight = maxWeight + '+'`. At the bottom, return
`weight` and "pounds". Head up top to try this: when we call `getTotalWeightString`,
pass 500.

Refresh! It works! We see the 500+ at the bottom.

But what if I wanted to make this argument optional with a default value of 500?
You *could* do this before in JavaScript, but it was ugly. Now, thanks to our new
best friend ES2015, we can say `maxWeight = 500` - the same way we do in PHP.
Now, we can remove the argument and everything is still happy!

So, yay! Finally, JavaScript has optional function arguments! And a *second* yay,
because we are ready to learn perhaps the *biggest* change in ES2015: JavaScript *classes*.
