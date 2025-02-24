---
layout: post
title:  "Talking About AI"
date:   2025-02-23 17:54:42 -06:00
categories: ai
---

# Talking About AI

This is going to be a casual post, not really one that follows much structure, just thinking about
AI as a tool to assist with my job.

I'm familiar with Co-pilot, my current job provides it to its employees to help with coding. I
think it's been at least a year since we started, and I have some thoughts.

1. it makes you faster, not better
2. it makes you lazy
3. hallucinations
4. it's only capable of solving today's problems. it can't think ahead for you
5. I worry it could stall people's careers

I'll expand on each of these points, and maybe I'm wrong, maybe I just haven't used the right tool
the right way, and all these concerns are actually invalid. I can only speak from my own experience
though, so that's all this is. For reference I've also played around a bit with Codeium on my
personal projects, and I think the same holds true for it as much as Co-pilot.

## 1. It makes you faster, not better

I feel like this statement should have so many asterisks on it that maybe it's not even fair to say
as a blanket statement, but I'll try my best to explain my thoughts here.

So what do I mean by "better"? I'm talking about the developer's ability to produce code that works
and is understandable. In pretty simple scenarios, AI is capable of performing the task adequately
and the developer doesn't need to worry about it too much. But in some cases, the AI picks one of
these, seemingly at random, and goes with it. So either you'll get code you can read, but when you
try to run it, it breaks. Or you could get something that works, but maybe it's hard to figure out
why. Both of these are a problem, the former for obvious reasons, the latter because if you have
code you can't explain, then it's not properly maintainable. Even asking an AI to explain it could
be a problem because see point 3.

It also doesn't make a developer "better" in the sense that unless they go out of their way to
understand their AI generated code, they're not learning anything except how to rely on AI to solve
their problems for them, but I'll talk more about that in point 5.

## 2. It makes you lazy

There is a growing number of developers who are losing the ability to code without an AI companion.
"Well we have AI coding companions now" you say, "the cat's out of the bag, I don't see the issue."
This could be hard to argue against sometimes, but I see this as a great loss, similar to how kids
aren't being taught cursive in schools anymore. My own handwriting leaves a lot to be desired in
terms of legibility. "It's fine, I just type everything anyway, it doesn't really matter." It's
just lazy, and in some ways I feel like we're sacrificing pieces of our humanity, and for what
gain? I don't even really know the answer to that question. But I digress.

Developers are losing the ability to code. They forget syntax, keywords, the order of arguments for
basic functions. You don't need AI to forget these things, but it's like a muscle; use it or lose
it. If you want to "superpower" your devs with AI, just think about the things you're asking them
to leave behind.

I guess one thing to think about that might convince people is outages. Could be a power outage,
internet outage, the datacenter running the AI is down, doesn't really matter, just imagine a
scenario where for whatever reason your developers are unable to use an AI coding companion. Do you
still want them to be able to produce quality code? And to take it a potential step further, how
much faith do you have in your normally AI-powered, but now AI-less, developers?

Another thing I often notice is that even if the code an AI would write would run, it's often not
performant. Unnecessary complete enumerations of collections multiple times, for example. Failing
to consider how collections might grow over time. But I guess that's more of a point 4 thing.

## 3. Hallucinations

I don't even really feel like I need to elaborate on this one much, I think anybody who's tried to
use AI has come across their hallucinations. This is what we call it when AI just starts
confidently making things up and trying to pass it off as reality.

An example from my career is when I was trying to solve an encoding issue and ChatGPT was confident
that the incoming text was simply URL encoded multiple times. It wasn't.

Another example was when it suggested I wrap Serilog's ConsoleSink in a decorator to solve a
problem. I don't know if Serilog has a ConsoleSink internally or not, I never went to check, but I
can confidently say that there wasn't one that was available for me to wrap the way ChatGPT
suggested.

More directly related to Co-pilot, it often assumes I'm using Moq for unit tests, or some Assertion
library, but at work we use NSubstitute and XUnit. Other than that I actually like using these
tools for unit testing, the one thing you have to be careful of is that it's actually testing what
you think it's testing.

## 4. It can't think ahead for you

I think that about covers it. It won't consider how collections might grow, or if the code needs to
be maintainable. It'll just write something that it thinks will solve the issue today, and as long
as nothing else changes, it'll be fine. Although even that being said, it doesn't usually seem to
think about optimizing things by using Dictionaries or HashSets or anything like that. (I've been
on a bit of a crusade with those, trying to make sure we don't needlessly enumerate entire
collections more than once if we can avoid it. It's fun)

## 5. I worry it could stall people's careers

Kind of as a consequence of everything else listed here, I think this is a legitimate concern. If
a developer is nothing without an AI coding companion, then they're nothing. I would hesitate to
call such a person a "developer". That may seem harsh, but it's our ability to recognize a problem,
break it down, come up with a solution, and code that solution that makes us developers. I thought
the same thing in the era of "just copy-paste from StackOverflow". If that's all you're doing, you
aren't putting in the work. For the longest time I refused to use code I didn't understand, and
while that was probably stubborn and maybe stalled my professional development a little in the
early years, I think my drive to ensure I only used code I understood proved beneficial in the long
run. But I expect the same of other developers. Not that they need to be as stubborn as me, but
they should be able to explain the code they're trying to push.

Even outside of AI code companions, things like asking ChatGPT to diagnose your problems is kind of
an issue too. The encoding incident I mentioned before, I would've expected a developer to know
that the string in question was not URL encoded multiple times. Even if you can't eyeball that,
which I'll give a pass because encoding is difficult to deal with sometimes, just try URL decoding
the string a couple times yourself to see what happens. If it doesn't fix the issue, then you just
found one case where ChatGPT failed to help you. What do you do now?

Tied up in all this is people's ability to review code. If you don't know how to write code to
begin with, how are you going to review other people's code? Can you spot the bug in a PR before it
even gets run? If somebody submits a PR to you, do you just give it a glance to say you looked at
it before rubber stamping and allowing it through? "AI code reviews exist" I haven't tried those
yet, and I'm curious about them. That could be a missing piece here, because one shortcoming of AI
coding companions is that they don't teach, they just do. AI code reviews could be beneficial, but
I'll reserve judgement for when I've given it a shot, but it can avoid hallucinations and give
meaningful feedback, then I don't see the harm. I just also imagine there will be some times when
I want to ignore it because that just seems to be the theme here. It's pretty good some of the
time, but when it's wrong, boy is it wrong.

I guess this is all to say that AI might be raising a generation of code monkeys that never really
know what they're doing, they just know how to ask for what they want. Maybe that's enough for some
positions, but it's taking the craft out of the work, and again, sacrificing a bit of humanity for
a bit of code.

## Other thoughts I started writing and didn't fit in one of the five categories

I started writing this next paragraph in section 1, but it seemed to take on a life of its own. I'm
leaving it in though.

So first off, let's talk about the word "better", because that can mean different things to
different people. When _I_ think about "better" I'm talking about the developer and their skills.
To use a common example, if a developer was tasked with creating a FizzBuzz program, they could
just prompt their AI assistant to write it for them. It would probably even write an implementation
that satisfies the requirements properly, FizzBuzz is pretty standard, and not overly complicated.
There's a simple twist in it, but I'm getting distracted. Most of us who have been around a while
will probably glance at the code to see if it did anything tricky or just the basic approach, just
out of curiosity. But somebody who has no knowledge of coding at all could prompt for a FizzBuzz
program and get a working solution too. "But Alex" you say, "isn't that the idea? Anybody can code
now!" Well, reader, you're kind of right. Anybody _can_ code. And I'm not even against that.
Anybody _should_ be able to code. The part that worries me is that we're just going to get more and
more "code" being done by people who don't really know what they're doing, they're just using AI
to get what they want right now. If we ditch the FizzBuzz example, and imagine some non-technical
person trying to add a feature to an app without bothering a developer, they might end up tacking
on some code that technically _works_, but you can't really replace a flesh and blood developer who
actually has an understanding of the system with some LLM that just has enough context to know what
it has to do to complete the task it was given.

## It's not all bad though

All of this being said, AI tools can be great. I still haven't turned off Co-pilot at work, I just
ignore many of its suggestions when I don't like it. I actually love it for unit tests, as it can
hammer out tests really quickly, especially after you give it one as an example. Sometimes it gets
stuck in the weeds writing ever more specific tests for the same function, but it's easy enough to
start pointing it at another one. Whether or not the tests actually test the thing they state they
are is another thing, and if the test fails it could be a legitimate case of your code not quite
running the way you think it was and the test was right, but there's a non-zero chance that the
test written by the AI was faulty.

It can also take over for some tedious things like writing getters/setters, validation, error
messages.

I'm sure there's a number of other little things that it's perfectly adequate for. I just don't
think I want to trust it when it comes to writing anything meaningful.
