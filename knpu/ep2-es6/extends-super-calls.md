# Class Inheritance and super Calls

In PHP, a class can extend another class. So, can we do that in JavaScript? Totally!
And once again, you're going to *love* it.

To try this out, let's go back to the `play.js` file. Create a new class: `AGreatClass`,
because, it's going to be a great class. Give it a `constructor` with a `greatNumber`
arg and set that on a property.

Below, add one new method: `returnGreatThings`, which it will, because it's going
to return our `greatNumber`!

Finally, create a new constant, `aGreatObject`, set to `new AGreatClass(42)`. Let's
`console.log(aGreatObject.returnGreatThings())`.

There's no mystery about what this is going to return. Run the file! Yep, 42!

## Extending a Class

Now, let's create another class, `class AnotherGreatClass`, because we're on a roll.
But, I want this to be a *sub class* of `AGreatClass`. How? The same way we do it
in PHP: `extends AGreatClass`.

That is it. We're not overriding anything yet, but this should work. Change the variable
to be a `new AnotherGreatClass`, and then run the file! Success!

## Overriding a Method and Calling super

From here, pretty much all the rules of extending things in PHP work in JavaScript,
with just a *little* bit of a different syntax. For example, we can override `returnGreatThings`.
Let's return something else that's great: `adventure`! This completely overrides the
parent class method.

Okay, but what if we want to call the *parent* method. In PHP, we would say
`parent::returnGreatThings()`. Well, in JavaScript, the magic word is `super`:
`let greatNumber = super.returnGreatThings()`. Let's return an array of great things,
like `greatNumber` and `adventure`. This time, it prints both. Love it!

## Overriding the constructor

Can we override the `constructor` in the same way? Because really, I should be
able to pass the `greatNumber` and the great thing, `adventure`, into this class.

Override the `constructor` and give it just one argument: `greatWord`. Then, set
`this.greatWord = greatWord`. Before we try to print that below, what do you think
will happen when we run this? We're setting the `greatWord` property... but we're
not calling the parent constructor. Actually, try to run it!

Ah, we get an error in the `constructor`!

> this is not defined

Interesting! Inside `construct()`, there is no `this` variable! And PhpStorm is
trying to tell us why:

> Missed superclass's constructor invocation

Unlike PHP - where calling the parent constructor is usually a good idea, but ultimately
optional - in JavaScript, it's required. You must call the parent's constructor.

So let's give this two arguments: `greatNumber` and `greatWord`. To call the parent
constructor... it's  *not* what you might think: `super.constructor()`. You actually
treat `super` like a *function*: `super(greatNumber)`.

Below, let's print out `this.greatWord` and pass in `42` and `adventure`. Try
this out!

Yes! It works! Oh man, are you feeling like a JavaScript class pro or what? Now
let's talk about something kinda weird: destructuring!
