# Radix

[Website](http://rubyworks.github.com/radix) /
[Report Issue](http://github.com/rubyworks/radix/issues) /
[Source Code](http://github.com/rubyworks/radix) /
[![Build Status](https://secure.travis-ci.org/rubyworks/radix.png)](http://travis-ci.org/rubyworks/radix) /
[![Gem Version](https://badge.fury.io/rb/radix.png)](http://badge.fury.io/rb/radix)

Radix is a very easy to use Ruby library for converting numbers to and from
any base. It supports both Integer, Float and Rational numbers, as well as 
representational string-notations that need not be in ASCII order.


## Features

* Convert to and from any base.
* Convert Integers, Floats and Rational numbers.
* Define custom encoding and character sets.
* Can be used to encode/decode bytecode strings.
* Very intuitive API.


## Usage

Base conversions with ASCII ordered notations are easy in Ruby.

    255.to_s(16)   #=> "FF"

    "FF".to_i(16)  #=> 255

But Ruby reaches it's limit at base 36.

    255.to_s(37)   #=> Error

Radix provides the means of converting to and from any base.

For example, a number in base 256 can be represented by the array [100, 10]
(ie. 100**256 + 10**1) and can be convert to base 10.

    [100,10].b(256).to_a(10)  #=> [2,5,6,1,0]

Or, to get a string representation for any base up to 62.

    [100,10].b(256).to_s(10)  #=> "25610"

A string representation of a number can be converted too, again,
up to base 62.

    "10".b(62).to_s(10)  #=> "62"

To use a custom character set, use an array of characters as the base
rather than an integer. For example we can convert a base 10 number
to another base 10 number using a different encoding.

    base = [:Q, :W, :E, :R, :T, :Y, :U, :I, :O, :U]

    "10".b(10).to_a(base)  #=> [:W, :Q]

To learn more have a look at the [QED Demo](http://rubydoc.info/gems/radix/file/DEMO.md).


## Installing

To install with RubyGems simply open a console and type:

    $ gem install radix

Radix follows [Ruby Setup](http://rubyworks.github.com/setup) package standard
so it can also be installed in an FHS compliant manner using setup.rb.


## Copyrights

Copyright (c) 2009 Rubyworks

This program is distributable in accordance with the *BSD-2-Clause* license.

See LICENSE.txt for details.

