# Test-driven Design

## Why not Test-driven Development?

It's the same thing, really. At CJ we call it
test-driven _design_ because we think the most important
benefit of test-driving your software development is the
impact it has on your design.

_Code that is easy to test usually exhibits good design_

By definition at CJ, good design means code is easy to
maintain.

There are plenty of other benefits of TDD: built-in automated
verification against regressions, fearless refactoring,
always-truthful documentaion, for example. But those don't
require test-driven development, only unit-tested code.
With test-driven you get it all.

## So What is Test-driven Design

When you test-drive your code, you promise to _never write
code unless a test requires it_. It sounds simple. It is
not. Becoming fully test-driven requires practice--a lot
of practice. And even when you are great at it, you will
find ways to improve.

## But It Takes So Much Time

To outsiders, test-driven design appears to impede productivity.
Unfortunately, those outsiders might be your boss or
your customers. But here's what they might not see: _you are
actually improving your overall productivity when you
test drive_.

Ask yourself: what proportion of your software development life
is writing new code versus modifying existing code? The fact
is, the vast majority of your work is adding new features and
fixing bugs in existing code. You might spend hundreds-of-times
more effort working on existing code than writing new code. So
what will make you more productive, delivering hard-to-maintain
code quickly or easy-to-maintain code a little more slowly?

## Decoupled Code

When you write code that is easy to test, you are automatically
reducing the coupling in your software. Coupling is the property
of software that forces you to change many things in response to
changing a single thing. With low coupling, your code is isolated
and resiliant to changes in other parts of the software.

## Red Green Refactor

At CJ, the most common way to test drive code is using the
red-green-refactor cycle. It goes like this:

1. Decide what you want to change, it should be a small thing, only
part of a feature
1. Write a test that will only pass if you successfully make the change.
You are now _red_
1. Write code that causes the test to pass. You must check all your
previous tests because you may have caused one or more of them to fail
with your change. Once all tests are passing, commit your code to
source control. You are now _green_
1. While you are green, survey your code and optionally decide changes you want
to make to improve code quality only and make them. You must not
change any behavior. How do you know if you changed behavior? One or
more of your tests will fail. Once all tests are passing, comit your
code. You just _refactored_
1. Repeat the cycle

It is super important to never refactor while you are red. If you see
something that is spelled wrongly but doesn't impact the current code
change, leave it alone. If you see you could make some code a little more
clear but it doesn't impact the current code change, leave it alone. Focus
only on going to green.

Once you are green (and commmitted to source control), make all the
improvements you want. Your tests will ensure you don't break anything.

Sometimes you want to improve your tests. That's ok, but only do it
while you are green. In that case, add your new tests, ensure they are
green and all your previous tests are still green, commit, then do another
refactor round that remove your old, deprecated tests.







