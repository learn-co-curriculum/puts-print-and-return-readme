---
tags: readme
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
# Hello!Hello!Hello!

3.times { puts "Hello!" }
# Hello!
# Hello!
# Hello!
```

By default, Ruby doesn't display any output. The methods `puts` and `print` are a great ways to explicity tell the program to display specific information. Without these printing methods, Ruby will read the line, but not print anything out.

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

You may notice that the `puts` and `print` methods, when run in IRB, print values on the screen and then display a line like this: `=> nil`. This is because puts and print may print the value you want, but instead of returning that value, they return `nil`.

Every method in Ruby returns a value by default, even custom ones. This returned value will be the value of the last statement. For example, let's look at this method called `restaurant`:
```ruby
def restaurant
  restaurant_name = "Guy's American Kitchen & Bar"
  cuisine = "american"
  motto = "Welcome to Flavor Town!"
end
```
The return value of the `restaurant` method is "Welcome to Flavor Town!" because that was the last statement evaluated.

Say you're the best chef in the world, Guy Fieri. To make a method that just prints your name and returns `nil`, you could write:
```ruby
def print_name
  puts "Guy Fieri"
end
```

To write a method that returns your name but doesn't print anything, you could write
```ruby
def return_name
  "Guy Fieri"
end
```

To both print and return your name, you could write:
```ruby
def print_and_return_name
  puts "Guy Fieri"
  "Guy Fieri"
end
```
If you accidentally switched the order of the lines inside the method:
```ruby
def broken_print_and_return_name
  "Guy Fieri"
  puts "Guy Fieri"
end
```
the method would instead print "Guy Fieri" and return `nil`. This is becuase the last line that was evaluated was `puts ...` and the return value of a `puts`, as seen in the [table above](#returning-values) is always `nil`. 
