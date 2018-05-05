+++
title = "Script to Create Exercise Files"
date = 2018-04-27T22:45:26+10:00
description = "A small script I have been using to create individual files for exercise."
weight = 30
draft = false
bref = "A small script I have been using to create individual files for exercise."
toc = false
comments = true
+++


### How to use
Copy the script  to a directory you would like to have file with exercise files, adjust the variable at the top to the number of exercises, then run the script.

I use Atom as my text editor and I can do this all in the editor, by copying the file to a new directory, editing the number of exercises, then running the script with the 'code runner' package for Atom ( CRTL + X ).

### The script
```ruby
#!/usr/bin/env ruby

exercises = 10
(1..exercises).each do |n|
  filename = "ex_#{n}.rb"
  File.open(filename, "w") { |file| file.write("# #{filename}\n# ") }
end
```
