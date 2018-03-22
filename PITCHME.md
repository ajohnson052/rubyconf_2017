<span class="menu-title" style="display: none">Title</span>

# Don't Write Clever Code

---
<span class="menu-title" style="display: none">Introduction</span>

Shout outs to
<br><br>

#### Esoteric, Obfuscated, Artistic
#### Programming in Ruby

<span class="aside">by Yusuke Endoh</span>

<br>
#### Types and Ruby Programming Language

<span class="aside">by Soutaro Matsumoto</span>

---
<span class="menu-title" style="display: none">Symbols 1</span>

```
puts "hello"

=> hello
```

---
<span class="menu-title" style="display: none">Symbols 2</span>

```
puts "" << 104 << 101 << 108 << 108 << 111

=> hello
```

---
<span class="menu-title" style="display: none">Symbols 3</span>

`$> == $stdout`

---
<span class="menu-title" style="display: none">Symbols 4</span>

```
$> << ("" << 104 << 101 << 108 << 108 << 111)

=> hello
```

---
<span class="menu-title" style="display: none">Symbols 5</span>

```
"@" =~ /$/

=> 1
```

---
<span class="menu-title" style="display: none">Symbols 6</span>

```
"@@" =~ /$/

=> 2
```

---
<span class="menu-title" style="display: none">Symbols 7</span>

```
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

#### Choose well-known methods
#### over cool Ruby tricks

---
<span class="menu-title" style="display: none">No Symbols 1</span>

```
puts "hello"

=> hello
```

---
<span class="menu-title" style="display: none">No Symbols 2</span>

`inspect`

<br>
Returns a string containing a human-readable representation of obj

---
<span class="menu-title" style="display: none">No Symbols 3</span>

```
inspect

=> "main"
```

---
<span class="menu-title" style="display: none">No Symbols 4</span>

```
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

```
for x in inspect do end

=> NoMethodError: undefined method 'each' for "main":String
```

---
<span class="menu-title" style="display: none">No Symbols 6</span>

```
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
<span class="menu-title" style="display: none">Hello, Goodbye 1</span>

```
puts "hello"

=> hello
```

---
<span class="menu-title" style="display: none">Hello, Goodbye 2</span>


```
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

```
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

### To promote readability:

<br>
* Choose well-known methods over cool Ruby tricks
* Implement new patterns with care
* Consider the consequences of quick bug fixes

---
<span class="menu-title" style="display: none">Quine Time?</span>

#### Quine Time?

<br><br>
```
eval s=%q(
  s="eval s=%q(#{s})"
  puts s
)
```
