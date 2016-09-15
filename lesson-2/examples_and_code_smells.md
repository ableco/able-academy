# Examples and code smells

Code clarity can take on many different forms. From variable naming, to method structure, to how classes and objects interact with each other.

### Function-level clarity

Compare the following examples:

#### Example 1a:
```ruby
def get_next_size(i)
  return i > 0 ? i << 2 : ~(i << 2) + 1
end
```

#### Example 1b:
```ruby
def get_next_size(current_size)
  if (current_size < 0)
    current_size *= -1
  end
  
  current_size * SIZE_MULTIPLIER
end
```

How quickly can a reader understand what the first example was doing? What about the second example?

Which code would you rather debug? If these were taken from two different files with 20 methods each, which would be easier to refactor and maintain?

To illustrate this further, we can expand this to multiple class methods:

#### Example 2a:
```ruby
def a(i)
  i << 2
end

def b(i)
  ~i
end

def c(i)
  i > 0
end

def d(i)
  c(i) ? a(i) : b(a(i)) +1
end
```

#### Example 2b:

```ruby
def invert(value)
  value * -1
end

def increase_size(value)
  value * SIZE_MULTIPLIER
end

def is_positive?(value)
  value > 0
end

def get_next_size(current_size)
  positive_current_size = if is_positive?(current_size)
    current_size
  else
    invert(current_size)
  end
  
  increase_size(positive_current_size)
end
```

As an application grows and becomes more complex over time, the way the code is written can deeply affect if it becomes more readable, or if it becomes increasingly hard to debug and maintain.

Note the `+ 1` that has to happen in example 2a if the original value is inverted. It isn't immediately clear that the invert function (`~i`) is a _bitwise operation_ that inverts the value of each bit in an integer. If `i == 8` then `~i == -7`. This is a detail that is not immediately apparent to the reader and, in many cases, will go unnoticed, leaving the door open for bugs to be introduced.

Conversely, the descriptively named `invert` method in example 2b makes it obvious what the intended outcome for that method is, and its contents can easily be verified by the reader.

