---
layout: post
title:      "OO Ruby Final Projects: Music Library CLI"
date:       2018-06-05 19:36:23 +0000
permalink:  oo_ruby_final_projects_music_library_cli
---


I am one lab away from the CLI Data Gem Project. Although, I have gone over it to evaluate what I need to do to complete it.

Object-oriented Ruby has been one heck of challenge so far, and I've enjoyed every moment, including the parts where I was stumped.  I enjoyed the Music Library CLI project the most.  However, the CLI Data Gem Project appears to be the most fascinating and open!  By open, I mean that I like that I get to choose the content of my project, albeit with some training wheels still attached. But I digress... What the Music Library CLI project brought to bear regarding object relation is where I struggled the most. It was hard to quickly wrap my brain around the intricacies of how the objects were to be linked via methods.  Moving forward my takeaway is to draw diagrams with a flowchart of objects to get the big picture.  And since I am a big picture thinker, this is almost a must! I am a visual-kinesthetic learner. I must see and touch my solutions, or at least have some physical association with what I am learning.

On the more technical side of the house, these are the methods in the Music Library CLI project that gave me the most significant challenge:

**Song Class**
`Song.new_from_filename`:  Learned that I had to instantiate a new instance of Song.

**Artist Class**
`artist#add_song`: The key to getting this to pass was the `unless` conditional statement, which is the inverse of the `if` conditional.  It just proved to be a far more elegant and efficient means of defining the method.

**Music Library Controller Class**
All of the trigger methods took some careful reading of the test specs and greater thinking along the lines of iterating with an index--that is, Ruby's `each_with_index method`, to be more specific. It saved the day!  Also, I later realized that I'd be sorting objects, which reframed my entire plan of approach to elegantly and adequately coding specific list methods. It is important to remember that we are to take advantage of the object attributes to maintain well abstracted and efficient code throughout the entire project.  So I called on the list of objects stored in the `@@all` class variables so that I could sort them, then call on their respective attributes to define specific list methods.

Overall, everything that I have learned has challenged me to think broadly--far more than I thought I already could.  And the fact that I can learn to think more broadly than I ever have with coding has nurtured both a growing excitement and hunger to learn more.
