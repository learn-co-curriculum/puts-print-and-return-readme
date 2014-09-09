---
tags: readme, WIP
language: ruby
resources: 0
track: web development
topic: ruby
unit: hello world
lesson: print, puts, and return
---

# Print, Puts, and Return

## Puts and Print

The puts (short for "put string") and print commands are both used to display the results of evaluating Ruby code. The primary difference between them is that `puts` adds a newline after executing, and `print` does not.

```ruby
3.times { print "Hello!" }
# => Hello!Hello!Hello!

3.times { puts "Hello!" }
# => Hello!
# => Hello!
# => Hello!
```

## Returning Values

Everything in Ruby has a return value. For instance:


|Code                   | Return Value   |
|-----------------------|----------------|
| `"Hello world"`       | `"Hello world"`|
| `6 + 3`               | `9`            |
| `president = "Obama"` | `Obama`        |
| `total = 6 + 3`       | `9`            |
| `puts "hello world"`  | `nil`          |
|`print "hello world`   | `nil`          |

### PUTS
Let's say I wanted to really quickly in IRB get my name printed to the screen. I would enter `puts "Victoria"`. 

So we learned earlier that `puts` is just a ruby method that is designed to output words on the screen. It's really useful for debugging especially if you're confused about what value a variable is at a given point in time. 

But in IRB, directly below my name printed, I see ` => nil`. What the heck is that? The `puts` method simply prints the string on the screen, it doesn't return the value of my string. It returns nil. It means that you wouldn't want to `puts "Victoria"` as the return value of a custom method. The end value you would get would be nil! That end value would replace all the hard work you did to get a certain value. It's like erasing everything.

###Let's run this from a ruby file!
`.rb` is a file extension that let's us know we're about to open a ruby file. The computer doesn't need the file extension to know what kind of file we're talking about. It's more for human use, so we don't get confused about it.


To run a ruby file, we need to make sure we exit out of IRB by typing `exit`. We want to see the ♥ that indicates the terminal prompt. We also want to make sure we're in the correct directory. Remember `pwd` will tell you your current location. You want to make sure you're in the `say-my-name` directory. 

The computer has to know exactly what file to run and where it is. To run a ruby file, in terminal you type `ruby file_name.rb`. You won't actually type "file_name.rb" but replace that with the name of the file you're trying to run, which in this case is `my_name.rb`

In terminal, you'll enter `ruby my_name.rb`. This basically tells the computer, activate the ruby interpreter and execute this file. If you're not in the correct directory when you run this command, you'll see this error `ruby: No such file or directory -- my_name.rb (LoadError)`


###RSPEC Again:
Go ahead and open the file named `my_name_spec.rb` located in the spec directory. 

Line 3 of this file indicates that we're describing the code in the file `my_name.rb`. Notice our spec file is `my_name_spec.rb`. The naming conventions is part of how rspec knows what tests to match with what code.

Lines 6-10 describe the first exercise. Line 6 tells us that our code that we will write in `my_name.rb` a method called `my_name`. Line 12 tells us that part two of this lab will need a method called `my_name_with_puts`. The tests will fail if you don't have methods named `my_name` and `my_name_with_puts`. To run the tests, just type `rspec` into terminal. You will need to be in the `say_my_name` directory for this command to work. If you've written your methods correctly, all the tests will pass!

###Returning v. Puts-ing
So how come when `my_name.rb` only has "victoria", and I run this part of the file I don't see my name printed? Input and output operations in ruby are really important. Input is any data that is read by the program. In the case of what we just played with, returning your name, that is our input. By default, ruby doesn't display any output. There are a lot of behind-the-scenes things that programs do, and we don't want our users to see all of those things. `puts` is a great way to explicity tell the program to display that specific information. Without `puts`, Ruby will read the line, but not print anything out.
