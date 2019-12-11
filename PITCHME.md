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

Let's start with looking at a team that writes really clever code

---
<span class="menu-title" style="display: none">Introduction 3</span>

### Premise:
A team is building a command line tool that has a Greeter class

---
<span class="menu-title" style="display: none">Introduction 4</span>

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
$stdout.puts "" << 104 << 101 << 108 << 108 << 111

=> hello
```

---
<span class="menu-title" style="display: none">Symbols 4</span>

```ruby
$stdout << ("" << 104 << 101 << 108 << 108 << 111)

=> hello
```

---
<span class="menu-title" style="display: none">Symbols 5</span>

```ruby
$> << ("" << 104 << 101 << 108 << 108 << 111)

=> hello
```

---
<span class="menu-title" style="display: none">Symbols 6</span>

```ruby
"@" =~ /$/

=> 1
```

---
<span class="menu-title" style="display: none">Symbols 7</span>

```ruby
"@@" =~ /$/

=> 2
```

---
<span class="menu-title" style="display: none">Symbols 8</span>

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

Impressive!

<br> 

But is it readable?

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

Phew! No more symbols!

<br>

But will anyone else understand this code?

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

Clever!

<br>

But will future self appreciate this?

---
<span class="menu-title" style="display: none">Readability Over Quick Fixes</span>

#### Consider the consequences
#### of quick bug fixes

---
<span class="menu-title" style="display: none">Wise Words</span>

“Indeed, the ratio of time spent reading versus writing is well over 10 to 1. We are constantly reading old code as part of the effort to write new code. ...[Therefore,] making it easy to read makes it easier to write.”

--  Robert C. Martin, Clean Code

---
<span class="menu-title" style="display: none">Promote Readability 1</span>

#### To promote readability:

* Embrace conventions and use existing patterns
* Implement new patterns with care
* Consider the consequences of quick bug fixes

---
<span class="menu-title" style="display: none">Promote Readability 2</span>

#### To promote readability:

* Keep things small - classes, methods, parameter lists
* Focus on descriptive, accurate naming
* Consider how easy it will be to delete your code    

---
<span class="menu-title" style="display: none">Conclusion</span>

### We need all of these people on our team!

The one keeping up with the latest blogs, the one pushing quick fixes, and the 
one with a deep understanding of the Ruby language all contribute to the team's 
success. They just need to adopt a team mentality!

---
<span class="menu-title" style="display: none">Resources</span>

### Additional Resources

* More Ruby tricks (and some quines)
    * http://confreaks.tv/videos/rubyconf2017-esoteric-obfuscated-artistic-programming-in-ruby
* More on code quality
    * Practical Object Oriented Programming in Ruby, Sandi Metz
    * Clean Code, Robert Martin

---