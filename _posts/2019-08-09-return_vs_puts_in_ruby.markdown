---
layout: post
title:      "Return vs. Puts in Ruby"
date:       2019-08-09 11:35:29 -0400
permalink:  return_vs_puts_in_ruby
---


When you’re first learning to code in ruby, one of the first methods you might learn is puts. Puts is great to show beginners because it lets you really see what your code is doing.

```
def hello
puts “Hello Madeline!”
end
```

This will print the words “Hello Madeline!” to the console. Pretty mind blowing stuff when you’re first learning. However, the downside of learning about puts first is that beginners often then want to use puts for every method they write from that point on. And that can be a bad thing because…

**Puts isn’t actually that useful.**

I know, I know, but it made your name show up on the computer! Isn’t that useful enough?
The reason puts might not be as useful as you think is because of return values. A return value is the information your method is actually sending out. And the return value of puts is nil, nothing, nada. 

I like to think of returning something vs putsing something as real money vs a photo of money. With cash (or lets be realistic, probably a credit card) I can do actual stuff. I can input my card to the ATM to see what my balance is, withdraw funds, and shop online.
With a photo of money, I can just show my instagram followers how cool I am. 


![Photo of cat with hundred dollar bills](https://i.imgur.com/kgTkpYpb.png)

Puts is the photo of money, return is the real thing.

I don’t mean to disparage puts. Sometimes there’s good reason to show what you have instead of returning it. Maybe you want to greet the user. In that case you could type: puts “Hello there!”. Thats definitely helpful, but there’s not a ton else you can do with it. 

```
def puts_balance(amount)
puts “I have #{amount} dollars!”
end
```

This method will tell users how much money we have. And that’s about it.
Instead, let’s try returning amount.

Returning something in ruby is actually super easy. The return value of a method is just whatever is on the last line of our method. So here:

```
def better_of_ted
“Ted"
end
```

the return value is Ted

But here:

```
def better_of_ted
“Ted”
“Phil”
end
```

the return value is Phil because “Phil” is the last line of our method.
Sometimes you might see the return keyword used to explicitly return things in ruby:

```
def better_of_ted
return “Lem”
“Ted”
“Phil”
end
```

This will return Lem. Using the explicit return keyword breaks us out of whatever code we’re running and returns that line. Explicitly returning can cause a lot of unintended consequences and is best avoided. 

So to recap, the return value of this:

```
def better_of_ted
“Veronica”
end
```

is Veronica

but the return value of this

```
def better_of_ted
puts “Veronica”
end
```

is nil

If we want to rewrite our balance method to return the amount, we could do something like this:

```
def return_balance(amount)
amount
end
```

With this method we can actually use our money.

```
def buy_cats(amount)
cost_of_cat = 100
return_balance(amount) - cost_of_cat #this subtracts the price of a cat from our balance
end 
```

Wise purchase.


And if we want to be really fancy, we can use return and puts together

```
def puts_and_return_balance(amount)
puts amount
amount
end
```

The return value of this method is still amount because amount is the last line, but the amount is also outputted to the console. 

Return values allow us to actually use our code in meaningful ways. If you’re confused whether a test is looking for puts or return, here’s an example of a test that is looking for puts:

`expect($stdout).to receive(:puts).with(“Oh hi Mark!”)`

And here’s a test expecting a return value:

`expect(buy_cats(200).to eq(100)`

Now that you have return values in your tool belt, you'll be able to do so many more cool things with your code! Happy coding!
