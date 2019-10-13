---
title: "Rails 6 Method: #Array.extract!"
layout: post
date: 2019-09-29 12:49
image: /assets/images/markdown.jpg
headerImage: false
tag:
- coding
- ruby
- ruby_on_rails
- tech
star: true
category: blog
author: samanthacausey
description: An explanation with an example of Array.extract!, a methods new with Rails 6.
---

Calling the new Rails 6 method ```extract!``` (<a href="https://github.com/rails/rails/pull/33137">Pull request here</a>) on an array will remove and return the elements for which the given block returns true.

Because I recently remembered what a great book <i><a href="https://www.goodreads.com/book/show/375802.Ender_s_Game">Ender's Game</a></i> (and, due to my low expectations, surprisingly alright <a href="https://www.imdb.com/title/tt1731141/">movie</a>) is, take the following code block that extracts characters in the Wiggin family, modifying the original ```characters``` array.

```ruby
>> characters = ['Petra Arkanian', 'Ender Wiggin', 'Bean', 'Mazer Rackham', 'Valentine Wiggin', 'Peter Wiggin']

=> ["Petra Arkanian", "Ender Wiggin", "Bean", "Mazer Rackham", "Valentine Wiggin", "Peter Wiggin"]

>> characters.extract! { |character| character.include?('Wiggin') }

=> ["Ender Wiggin", "Valentine Wiggin", "Peter Wiggin"]
```

This new method is basically the opposite of ```reject!``` since ```reject!``` returns the array after the elements have been removed, and ```extract!``` will return the elements that were removed from the array. Here's the example using ```reject!```.

```ruby
>> characters = ['Petra Arkanian', 'Ender Wiggin', 'Bean', 'Mazer Rackham', 'Valentine Wiggin', 'Peter Wiggin']

=> ["Petra Arkanian", "Ender Wiggin", "Bean", "Mazer Rackham", "Valentine Wiggin", "Peter Wiggin"]

>> characters.reject! { |character| character.include?('Wiggin') }

=> ["Petra Arkanian", "Bean", "Mazer Rackham"]
```

Fun fact: There's also a <a href="https://github.com/rails/rails/blob/master/activesupport/lib/active_support/core_ext/hash/slice.rb#L41-L47">```#Hash.extract!``` method</a>.
