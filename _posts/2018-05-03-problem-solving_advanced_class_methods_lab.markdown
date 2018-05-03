---
layout: post
title:      "Problem-Solving: Advanced Class Methods Lab"
date:       2018-05-03 15:59:22 +0000
permalink:  problem-solving_advanced_class_methods_lab
---


This post is a live blog post--meaning that as I work through this lab, I am writing out my thoughts and actions for this post.

So, I am stumped, yet again.  And I honestly want to say that it is great.  Weird, right?  And, yes, it is weird!  But I am learning to absorb and redistribute the impacts of what it means to "fail up" as a computer programmer.  My current lesson is the Advanced Class Methods Lab, which for some reason the concepts seem to be flying over my head.  But as I have worked my way through the Learn.co curriculum I have relied on the practice of chunking larger problems into smaller problems or the counterintuitive route of taking a beat, as it were--be it either a 15-minute break to do something different or take a walk and returning with a fresh head on my shoulders to get at the problem.

I've stopped to write this blog post because where I am stuck is to create a class constructor that initializes a song and saves it to the ```@@all``` class variable. Finally, it should return the song instance that initialized and saved.

My code towards this solution is as follows:

```
def self.create
   song = self.new
   song.name = name
   song.save
end

def self.all
   @@all
end

def save
   self.class.all << self
end
```

But I am getting the following error:

```1) Song Class Methods .create instantiates and saves the song, and it returns the new song that was created
Failure/Error: expect(song).to be_a(Song) expected [#<Song:0x000000022d7c68 @name = "Song">] to be a kind of Song```
		 
I don't know what the problem is here.  And as usual, I have the sneaking feeling there is either an elementary concept I am overlooking as it pertains to Class Methods or I didn't read carefully.

 (10 minutes later)

 First, I re-read the specifications for the ```Song#create``` class constructor to realize that this line of code: ```song.name = name``` is not required because we are not initializing an instance of Song with a name at all, hence the subsequent class constructor in my class building called ```Song#new_by_name```.  So I removed the line above entirely and ran the learn command in the terminal once again.  I got back the same error. 
 
 Next, I commented out the last line: ```song.save``` and got the following error, and for which I was so grateful because it gave me a clue I needed to see the error of my ways. 
 
 ```1) Song Class Methods .create substantiates and saves the song, and it returns the new song that was created
 Failure/Error: expect (Song.all).to include(song) expected [] to include #<Song.0x000000141b378>```
 
 This error message clued me in that the save function is storing the song that I instantiated on the first line as expected.  Next, I referred back to the specifications to see that I am just not paying close enough attention to detail because the last instruction states that the method should **return** *the song instance that was initialized and saved*.  So I changed my code as follows and was able to move on to the next specification in the lab:

```
def self.create
   song = self.new
   song.save
   song
end
```
			
**The Takeaway**

In simple list form:

1. Read/Know and revisit your specifications carefully. (Implicit task: A good programmer has planned and written test cases. In this context, the specs and tests are written for me and leads to the next point...)
2. Give proper attention to detail.
