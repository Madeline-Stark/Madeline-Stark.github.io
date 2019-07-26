---
layout: post
title:      "What Even Is An Argument Anyway??"
date:       2019-07-22 22:08:45 -0400
permalink:  what_even_is_an_argument_anyway
---


TLDR: How to use arguments in Ruby

When I first started learning to code, I came up with this great system for passing my tests. If the test was passing my method two numbers like this:
		
```
sum(2, 3)
```

And they wanted my method to return the sum:

```
expect($stdout).to receive(:puts).with(5) 
#this just means we’re expecting the method to puts 5
```

All I had to do was write a method like this

```
def sum(first_number, second_number)
    puts 5
end
```

Magic! It worked perfectly and I never had to bother with those pesky arguments the test passed in. 
This victory lasted for about two seconds until I saw the next test called sum like this:

```
sum(3, 3)
```

And it expected the output to equal 6.

I smacked my palm to my forehead and accepted my fate. I was going to have to learn what an argument was. This doesn’t have to be the end of the world though. Arguments allow our code to be reusable. Without them, our methods are pretty impractical.

I like to think of a  method like a vending machine. My output will be different depending on what I input as my argument. If I put in D7, I’ll get a pack of delicious Gardetto’s Original Snack Mix, but if my finger slips and I put D8, I’m stuck with Fig Newtons and out 50 cents. A vending machine that gave us the same item, no matter what we input, would be pretty useless. We could punch in any combo of numbers and still be stuck with something disgustingly healthy, like a crumbly, good for nothing Nature’s Valley Bar.
		
This is that vending machine in code form:

   ```
def lame_vending_machine(snack)
     "You chose a Nature’s Valley Bar.”
end
```

This method will output a Nature’s Valley Bar no matter what we input. Noooo!!

THERE’S GOT TO BE A BETTER WAY!

Instead, we want to make our code reusable so that we can give our method different input and get a different result.
```
def super_fancy_vending_machine(snack)
  "You chose #{snack}”
end 
```
This method will take an input of snack and interpolate it into a string to return the user’s choice. 

Look at the different return values of these methods when we call them with the same argument:

   ```
lame_vending_machine(“hot cheetos”)
        => "You chose a Nature’s Valley Bar. ” #this is the return value
```
  
	
Have fun getting those crumbs out of your new carpeting.
		
vs.

```
super_fancy_vending_machine(“hot cheetos”)
    =>"You chose hot cheetos.”
```
   
Much better!

An argument is just whatever information we pass in when we call the method.

Here the argument is a string:

`my_string_method(“boop!”)`

But I can also pass in a number:
            
`my_number_method(42)`

Or even an array:

`my_array_method(["Wubba", "Lubba", "dub", "dub"])`


One word that you might also hear about in regards to arguments is *parameter*. A parameter is just the variable name we’re using to access whatever the test passes in.
		
```
def favorite_song(song)
  puts song
end
```

Here the parameter is song. When we reference song inside of our method, we’re really saying, “Hey! Give me that thing you passed into the method when you called it!” Try to pick a variable name that’s descriptive of what you will pass in, but ultimately it can be anything. However, if you name all your parameters “stuff" and "thing", you’re going to have a bad time. 

Another issue to be wary of with arguments, is some of the common errors you might see. 

```
ArgumentError:
         wrong number of arguments (given 1, expected 0)
```

This means that we are calling the method with in an argument.

```
cart([“apples”, “oranges”])
```

But we haven’t defined our method to accept an argument.

   ```
def cart
  puts "cart"
end
```
				
And this error is the opposite:

```
 ArgumentError:
            wrong number of arguments (given 0, expected 1)
```

This means that we defined our method to expect an argument.

```
def cart(shopping_cart)
  puts shopping_cart
end
```

But we’re calling it without one:

` cart`
	 
If you’re programming using Test Driven Development, it’s helpful to check how the test is calling a method before you define it. That will help you avoid errors like these.

Hopefully now you have a better understanding of how you can use arguments. They might seem confusing now, but they will make your life a lot easier in the long run. Unless of course you only want to create methods that output the same thing forever and ever until the end of time. In that case, you do you.
