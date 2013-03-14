## Description

debugger2 is a fork of [debugger] (https://github.com/cldwalker/debugger) for Ruby 2.0.

It uses only external C-APIs. Not of Ruby core sources.

(and debugger is a fork of ruby-debug(19) that works on 1.9.2 and 1.9.3 and installs easily for rvm/rbenv rubies :)

I want to merge original debugger if it has no problem. So debugger2 may be obsolete. Feel free to give us your comments.

## Install

First clone this repository:

```shell
git clone git@github.com:ko1/debugger2.git
```

Next, compile the extension:

```shell
rake compile
```

Build the gem package and install it:

```shell
gem build debugger2.gemspec
gem install debugger-1.0.0.gem
```

## Supported Rubies

Ruby 2.0.0 or later.

## Usage

Wherever you need a debugger, simply:

```ruby
require 'debugger'; debugger
```

To use with bundler, drop in your Gemfile:

    gem 'debugger2', :git => "git://github.com/ko1/debugger2.git"

### Configuration

At initialization time, debugger loads config files, executing their lines
as if they were actual commands a user has typed. config files are loaded
from two locations:

* ~/.rdebugrc (~/rdebug.ini for windows)
* $PWD/.rdebugrc ($PWD/rdebug.ini for windows)

Here's a common configuration (yeah, I should make this the default):

    set autolist
    set autoeval
    set autoreload

To see debugger's current settings, use the `set` command.

### Using Commands

For a list of commands:

    (rdb: 1) help

Most commands are described in rdebug's man page

    $ gem install gem-man
    $ man rdebug

### More documentation

I forked this project from <https://github.com/cldwalker/debugger>.
Maybe it can work same as `debugger'.
However, now don't support `post-motem' mode and `threading'.

Please give us your feedback.

## Reason for Fork

Ruby 2.0.0 has debugger support API. No need to install internal headers.

## Issues
Please report them [on github](http://github.com/ko1/debugger2/issues).

## Credits

All ruby's debugger programmers.

Quote from [original README.md] (https://github.com/cldwalker/debugger/blob/master/README.md).

* Thanks to the original authors: Kent Sibilev and Mark Moseley
* Thanks to astashov for bringing in a new and improved test suite and various bug fixes.
* Thanks to windwiny for porting to 2.0.0
* Contributors: ericpromislow, jnimety, adammck, hipe, FooBarWidget, aghull
* Fork started on awesome @relevance fridays!

## TODO

* Collect feedback.

