<span class="menu-title" style="display: none">Title</span>

# Clever Code

---
<span class="menu-title" style="display: none">Introduction 1</span>

Shout outs:
<br>

### Yusuke Endoh
Esoteric, Obfuscated, Artistic Programming in Ruby

<br>

### Soutaro Matsumoto
Types and Ruby Programming Language

---
<span class="menu-title" style="display: none">Introduction 2</span>

### Premise:
A team is building a greeter that will print "hello" to the command line

---
<span class="menu-title" style="display: none">Introduction 3</span>

```ruby
puts "hello"

=> hello
```

---
<span class="menu-title" style="display: none">Persona 1</span>

### Persona 1:

* has a deep understanding of Ruby
* sees many possibilities in such a flexible language
* comfortable with complex operators
* recently realized that the Greeter could be written using only symbols 

---
<span class="menu-title" style="display: none">Symbols 1</span>

```ruby
puts "hello"

=> hello
```

---
<span class="menu-title" style="display: none">Symbols 2</span>

```ruby
puts "" << 104 << 101 << 108 << 108 << 111

=> hello
```

---
<span class="menu-title" style="display: none">Symbols 3</span>

```ruby
$> == $stdout
```

---
<span class="menu-title" style="display: none">Symbols 4</span>

```ruby
$> << ("" << 104 << 101 << 108 << 108 << 111)

=> hello
```

---
<span class="menu-title" style="display: none">Symbols 5</span>

```ruby
"@" =~ /$/

=> 1
```

---
<span class="menu-title" style="display: none">Symbols 6</span>

```ruby
"@@" =~ /$/

=> 2
```

---
<span class="menu-title" style="display: none">Symbols 7</span>

```ruby
_ = ("@" =~ /$/)
__ = ("@@" =~ /$/)
$> << ("" << ((__*__+_)*__)**__+__+__ <<
                ((__*__+_)*__)**__+_ <<
                ((__*__+_)*__)**__+__*__*__ <<
                ((__*__+_)*__)**__+__*__*__ <<
                ((__*__+_)*__)**__+__*__*__+__+_)

=> hello
```

---
<span class="menu-title" style="display: none">Readable?</span>

Before you get too pleased with yourself... Are you scaring away other developers?

---
<span class="menu-title" style="display: none">Readability Over Tricks</span>

#### Embrace convention and
#### use existing patterns

---
<span class="menu-title" style="display: none">Persona 2</span>

### Persona 2:

* keeps up with the programming blogs
* knows about popular patterns and trends
* annoyed with another coworker's insistence on using symbols 
* heard on a podcast that Rubyists should avoid using symbols

---
<span class="menu-title" style="display: none">No Symbols 1</span>

```ruby
puts "hello"

=> hello
```

---
<span class="menu-title" style="display: none">No Symbols 2</span>

```ruby
inspect
```

<br>
Returns a string containing a human-readable representation of obj

---
<span class="menu-title" style="display: none">No Symbols 3</span>

```ruby
inspect

=> "main"
```

---
<span class="menu-title" style="display: none">No Symbols 4</span>

```ruby
puts inspect.clear
            .concat(104)
            .concat(101)
            .concat(108)
            .concat(108)
            .concat(111)

=> hello
```

---
<span class="menu-title" style="display: none">No Symbols 5</span>

```ruby
for x in inspect do end

=> NoMethodError: undefined method 'each' for "main":String
```

---
<span class="menu-title" style="display: none">No Symbols 6</span>

```ruby
class String
  def each
    clear
    concat 104
    concat 101
    concat 108
    concat 108
    puts concat 111
  end
end

for x in inspect do end

=> hello
```

---
<span class="menu-title" style="display: none">Readable?</span>

Before you jump on that bandwagon... What will be understood by the team?

---
<span class="menu-title" style="display: none">Readability Over Trends</span>

#### Implement new patterns
#### with care

---
<span class="menu-title" style="display: none">Persona 3</span>

### Persona 3:

* proactive about production monitoring
* takes pride in making speedy hot fixes
* tired of the debates about design patterns and coding style 
* noticed the Greeter never says "goodbye"

---
<span class="menu-title" style="display: none">Hello, Goodbye 1</span>

```ruby
puts "hello"

=> hello
```

---
<span class="menu-title" style="display: none">Hello, Goodbye 2</span>


```ruby
class Greeter
  def speak
    puts 'hello'
  end
end

greeter = Greeter.new
greeter.speak
=> hello
greeter.speak
=> hello
```

---
<span class="menu-title" style="display: none">Hello, Goodbye 3</span>

```ruby
class Greeter
  def speak
    puts 'hello'
    def speak
      puts 'goodbye'
    end
  end
end

greeter = Greeter.new
greeter.speak
=> hello
greeter.speak
=> goodbye
```

---
<span class="menu-title" style="display: none">Readable?</span>

Cool, you fixed that pretty fast... But your coworkers are in for some surprises

---
<span class="menu-title" style="display: none">Readability Over Quick Fixes</span>

#### Consider the consequences
#### of quick bug fixes

---
<span class="menu-title" style="display: none">Wise Words</span>

“Indeed, the ratio of time spent reading versus writing is well over 10 to 1. We are constantly reading old code as part of the effort to write new code. ...[Therefore,] making it easy to read makes it easier to write.”

--  Robert C. Martin, Clean Code

---
<span class="menu-title" style="display: none">Summary</span>

#### To promote readability:

* Embrace conventions and use existing patterns
* Implement new patterns with care
* Consider the consequences of quick bug fixes

---
<span class="menu-title" style="display: none">Deletable?</span>

#### To promote readability:

Consider how easy it will be to delete your code    

---
<span class="menu-title" style="display: none">Conclusion</span>

### We need all of these people on our team!

The one keeping up with the latest blogs, the one pushing quick fixes, and the 
one with a deep understanding of the Ruby language all contribute to the team's 
success. They just need to adopt a team mentality!

---
