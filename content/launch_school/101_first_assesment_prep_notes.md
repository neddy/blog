+++
title = "101 First Assesment Preparation Notes"
date = 2018-05-05T14:00:00+10:00
description = "Note for preparing for first assesment at Launch School"
weight = 50
draft = false
bref = "Note for preparing for first assesment at Launch School"
toc = true
comments = false
+++

### Specific Topics of Interest
Be able to explain clearly the following topics:

* local variable scope, especially how local variables interact with method invocations with blocks and method definitions
* how passing an object into a method definition can or cannot permanently change the object
* working with collections (Array, Hash, String), and popular collection methods (each, map, select, etc). Review the two lessons on these topics thoroughly.
* [variables as pointers](https://launchschool.com/books/ruby/read/more_stuff#variables_as_pointers)
* [puts vs return](https://launchschool.com/books/ruby/read/methods#putsvsreturnthesequel)
* false vs nil and the idea of "truthiness"
* method definition and method invocation
* implicit return value of method invocations and blocks


### How to Answer the Assessment Questions

The questions in this assessment will typically be testing your knowledge and understanding on more than one level.

* On one level the question is testing your ability to parse code and to describe it with precision, or testing your knowledge of some specific syntactical aspect or language-specific feature of the Ruby programming language.
* On another level, the question is checking your understanding of some deeper, underlying principle; this might be some more fundamental aspect of the Ruby language, or a non-language-specific concept that applies to programming more generally.

When answering the questions, you should:

* Explain your reasoning with reference to specific lines in the program. You can use line numbers to refer to specific lines of code where necessary.
* Answer with extreme precision. For example, say "method definition" or "method invocation" as opposed to just "method" (see the section on 'Precision of Language' below for more on this).
* Highlight any specific syntactical conventions or technical observations where relevant.
* Identify the key fundamental concept or concepts being demonstrated in the question.

##### Example

Examine the code example below. The last line outputs the String 'Hi' rather than the String 'Hello'. Explain what is happening here and identify the underlying principle that this demonstrates.
```ruby
greeting = 'Hello'

loop do
  greeting = 'Hi'
  break
end

puts greeting
```

### My answer before looking at suggested answer:

Within this code, on the first line, the string 'Hello' is assigned to the variable 'greeting'. Next, a loop block is run, inside the block, the string 'Hi' is assigned to the variable 'greeting'. Next, the loop is broken with 'break'. Finally the method 'puts' is called on the variable 'greeting' which which now contains the string 'Hi', which is output to the screen. The variable 'greeting' contains the string 'Hi' because is was assigned this value within the loop. If a variable is defined outside a block it may be accessed from within a block, and it's vaule modified.

### LS answers and explanations 

Compare the following possible answers to this question:

A) greeting is set to 'Hello' on line 1. greeting is set to 'Hi' on line 4. Line 8 outputs greeting, which is 'Hi'.

B) The local variable greeting is assigned to the String 'Hello' on line 1. Within the loop, greeting is then reassigned to the String Hi on line 4. The puts method is called on line 8 with the variable greeting passed to it as an argument; since greeting is now assigned to 'Hi', this is what is output.

C) The local variable greeting is assigned to the String 'Hello' on line 1. The do..end alongside the loop method invocation on lines 3 to 6 defines a block, within which greeting is reassigned to the String Hi on line 4. The puts method is called on line 8 with the variable greeting passed to it as an argument; since greeting is now assigned to 'Hi', this is what is output.

D) The local variable greeting is assigned to the String 'Hello' on line 1. The do..end alongside the loop method invocation on lines 3 to 6 defines a block, within which greeting is reassigned to the String Hi on line 4. The puts method is called on line 8 with the variable greeting passed to it as an argument; since greeting is now assigned to 'Hi', this is what is output. This example demonstrates local variable scoping rules in Ruby; specifically the fact that a local variable initialized outside of a block is accessible inside the block.

While none of these answers is technically incorrect, they all answer the question with varying degrees of detail and precision.

* Answer 'A' describes what is happening in the code example, but does so in a fairly basic way with imprecise language. This wouldn't be a sufficient response to receive full points for any of the questions in the assessment.

* Answer 'B' again describes what is happening, but with much greater precision of language. This would score higher than Answer 'A', but generally wouldn't be sufficient to receive full points for the majority of questions; most questions in the assessment are looking for something more, such as a specific piece of syntactical knowledge and perhaps identification of some fundamental concept.

* Answer 'C', as well as precisely describing the example, identifies an important Ruby syntactical convention that is relevant to the example: the fact that the method invocation combined with do..end defines a block in Ruby. For some assessment questions this might be sufficient to receive full points, but many questions will expect you to demonstrate some deeper understanding of the fundamental concept that this illustrates.

* Answer 'D' goes a step further than 'C' by explaining why this is important and the underlying principle that it demonstrates; i.e. the fact that method invocations with blocks in Ruby have particular scoping rules which affect whether or not the local variable can be referenced or reassigned. Based on the way that this particular question is phrased, answer 'D' would be the only answer of the four to receive full points in an actual assessment.


### Example Question from Discussion Post, and My Answer

Describe the following code:
```ruby
def fix(value)
  value << 'xyz'
  value = value.upcase
  value.concat('!')
end
s = 'hello'
t = fix(s)
```

A method 'fix', is defined on the first line, with a parameter of 'value'. The variable 's' is assigned a value of 'hello' on line 6, then the method 'fix' is then called with 's' passed to the method and assigned to the variable 'value', with the return value of the method assigned to the variable 't'. Within the method 'fix', on line 2, the string 'xyz' is appended to the variable 'value', this mutates the object referenced by the variable 'value', which the variable 's' also references, therefore both the variable 'value' within the method, and the variable 's' outside the method now contain the string 'helloxyz'. Next, on line 3, the variable 'value' is assigned a new value of it's previous value in upercase as a result of calling the method upcase on the variable 'value'. 'value' now contains a new string object 'HELLOXYZ', this does not mutate 's', which is left unchaged. Finally on line 4, the string '!' is appened to the string object referenced by the variable 'value', this is done by calling the concat method on 'value' with the string '!' passed to the method. This mutates the variable 'value' to 'HELLOXYZ!', which is the final expression in the method 'fix', and is therefore implicitly return by the 'fix' method and assigned to the variable 't'. The final value for the variables is: 's' = 'helloxyz', 't' = 'HELLOXYZ!' 

This method demonstarates how some operations inside a method can mutate the caller, but do not always do so. This method also demonstrates how a medthod with implicitly return the last expression of hte method.


### Precision of Language

Most of the questions will require that you explain the code using words. It's important to be able to explain why something happens using precise vocabulary and be able to pinpoint the exact causal mechanism at work. In other words, be precise and don't be vague.

For example, let's take the following piece of code.

```ruby
def a_method
  puts "hello world"
end
```

If asked to describe the method, you might be tempted to say "the results of the method is hello world". This isn't wrong, but for a programmer, it's extremely imprecise and doesn't help us understand the method. If you had written that as an answer, you'd score a 5/10 on the question (50% is not a passing score).

The more precise answer would be "the method outputs the string hello world, and returns nil". In programming, we are always concerned with the output and the return value and mutations to objects. We need to speak in those terms, and not use vague words like "results".

When writing answers to the test questions, make sure to be as precise as possible, and use the proper vocabulary. Doing this will help you debug and understand more complex code later in your journey. If your definitions are not precise, you will not be able to lean on them to decompose complicated code. Also, you will likely not be able to pass this assessment.


### Some Specific Definitions

As well as requiring a general precision of language in your answers, for the purposes of the assessment there are a few areas where we would like you to refer to certain things in a very clear and fairly specific way; these are outlined below.

##### Truthiness
In the assessment we want you to be very clear about the distinction between truthy and the boolean true (and similarly the distinction between falsey and the boolean false).

In Ruby, every value apart from false and nil, evaluates to true in a boolean context. We can therefore say that in Ruby, every value apart from false and nil is truthy; we can also say that false and nil are falsey. This is not the same as saying every value apart from false and nil is true, or is equal to true. These may seem like subtle distinctions but they are important ones.

Example:

```ruby
a = "Hello"

if a
  puts "Hello is truthy"
else
  puts "Hello is falsey"
end
```

* `a` is `true` and so 'Hello is truthy' is output" would be incorrect
* `a` is equal to `true` and so 'Hello is truthy' is output" would be incorrect
* `a` evaluates to `true` in the condtional statement and so 'Hello is truthy' is output" would be correct
* `a` is truthy and so 'Hello is truthy' is output" would be correct

##### To sum up:
*Use "evaluates to true" or "is truthy" when discussing an expression that evaluates to true in a boolean context
*Do not use "is true" or "is equal to true" unless specifically discussing the boolean true

##### Method Definition and Method Invocation
When discussing methods, particularly in terms of how blocks and methods interact with local variables, we want you to explain this in terms of method definition and method invocation. You can review [this assignment](https://launchschool.com/lessons/a0f3cd44/assignments/9e9e907c) for an outline of the mental model to use.

##### Integer, Fixnum and Bignum
As of Ruby 2.4.0, Ruby has unified Fixnum and Bignum into Integer; Fixnum and Bignum are now deprecated. For the purposes of the assessment we want you to refer to Integer when identifying a Ruby object that represents a whole number. [This assignment](https://launchschool.com/lessons/c82cd406/assignments/1788c3a1) provides some additional context.

##### Variable References and Object Mutability Articles
We wrote a series of blog posts that thoroughly cover variable references and object mutability:

* [Variable References and Mutability of Ruby Objects](https://launchschool.com/blog/references-and-mutability-in-ruby)
* [Mutating and Non-Mutating Methods in Ruby](https://launchschool.com/blog/mutating-and-non-mutating-methods)
* [Object Passing in Ruby - Pass by Reference or Pass by Value](https://launchschool.com/blog/object-passing-in-ruby)

Spend some time reviewing these articles to ensure that you have a good understanding of these topics.

### Assessment Prep Videos
We did a Beginning Ruby series that will serve as great review for this test. Specifically, the sessions that are relevant to this assessment are:

* [Part 1](https://launchschool.com/blog/live-session-beginning-ruby)
* [Part 2](https://launchschool.com/blog/live-session-beginning-ruby-part-2)
* [Part 3](https://launchschool.com/blog/live-session-beginning-ruby-part-3)


### Notes To Organise

When you say "the method local variable value is mutated ..", I'd change that to "Inside, the method fix, the string object pointed to by the local variable value is mutated ...`. The point is that we don't mutate variables, but the objects those variables point to.
