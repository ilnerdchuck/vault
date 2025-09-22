---
id: 1740496719-black-box-testing
aliases:
  - Black Box Testing
tags: []
title: Black Box Testing
---

When performing black box testing you care about only the input and output interface 
and not the implementation of the compontent under test => **INDIPENDENT FOM THE IMPLEMENTATION**
Pros:
    - Don't need the implementation to write the tests
    - Very easy and fast to write
Cons:
    - Can't cover all possible behaviours of the compontent under test 

For example to test a function `int foo(int a, int b)` we can generate some integer numbers 
and assert that the output is an `int` type.


# Refereces
[[1740496359-unit-testing|Unit Testing]]
[[1740496732-white-box-testing|White Box Testing]]
