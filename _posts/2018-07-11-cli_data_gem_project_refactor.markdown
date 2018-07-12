---
layout: post
title:      "CLI Data Gem Project Refactor:  Building CLI Menus"
date:       2018-07-11 23:10:10 -0400
permalink:  cli_data_gem_project_refactor
---

Although I moved on with the remainder of the curriculum that follows the CLI Data Gem Project, I was asked to refactor the menu system that I created within my CLI controller class.  The correction that I was given was to eliminate the additional calls on methods that contained `while` loops.  

Basically, my redirect was to get the user from one menu or display to another without erroneously re-calling menu methods and triggers to do so.  Taken to scale, this would hypothetically be a real disaster of a command-line program because at no point did I implement `break` statements by which to end a loop and thereby step back to a previous menu. Instead, my program was susceptible to having multiple running loops in the call stack. 

So to reiterate, my objective going forward was to refactor the CLI controller class's series of methods to enable the user to step forward into a menu that persists in the terminal via a while loop and is then broken to navigate anywhere else.

In the process of refactoring the class, however, I found a better way to streamline and refine the menu systems to be far less complex for the user, and more intuitive than originally coded for a command-line interface built on page-like menus.

I want to share my improvement . It is pretty neat means of handling multiple menus in cli.  But first let me setup what was my intent. My original intent is to enable the quit option no matter where the user navigates in the program. I removed the option while refactoring to drive the user back to the main menu and at which point the user can quit.  With that said, Iet's say that you *do* want the user to have the quit option anywhere in the program.  In the code below is a main menu method and the other method is a kind child method to the former because the second is reached via the main menu.

Let's say this code is your CLI main menu method:
 
 
 ```
 def main_menu
 
  while @input != 'quit' do
	
   # some code
	 
   @input = gets.strip.downcase
	 
   # some logic code to trigger the #main_menu method
	 
	 # some logic code that triggers the 'break' statement when @input = 'quit'
	 
  end
 end
 ```

And this is the main menu (my data gem's actual main menu):

![](https://i.imgur.com/eR9p4bg.png)


Now lets navigate to a sub-menu by choosing option 16 and this code triggers the menu for the option:

```
def sub_menu

 while @input != 'quit' do
 
  # some code
	
	@input = gets.strip.downcase
	
	# some logic code that triggers the 'break' statement when @input = 'quit'
	
 end
end
```

This is the submenu:

*Top of the menu*

![](https://i.imgur.com/KdU0KKn.png)

*Bottom of the same menu due to 180 possible user selection options.*

![](https://i.imgur.com/4tJcXh3.png)

Notice that I stored the user input in an instance variable.  The genius of using this is in how its instance scope will allow both the `#sub_menu` and `#main_menu` method's loops to break and exit or end the program.

This is the convention I utilized to step into a menu and then back out of it. However, I've only shown how to end the program with 'quit'.  By choosing a different term to for any sub menu I can allow the user to return to the main menu from anywhere in the program, as opposed to simply quitting. (Note: I grant that this is a not a either/or dilemma. I could certain create option to quit from anywhere in the program as well as simply return to the main menu from anywhere else in the program too.  It was just my prerogative to do one over the other.)

So if the `#sub_menu` method were written as follows, it would enable the user to type in 'main', which breaks the sub menu's loop but will stop at the main menu.  Why? the `@input` instance variable current holds the string 'main', thereby preventing the `#main_menu'` from breaking or ending.

```
def sub_menu

 while @input != 'main' do
 
  # some code
	
	@input = gets.strip.downcase
	
	# some logic code that triggers the 'break' statement when @input = 'quit'
	
 end
end
```

In in the last image above the user is given the option to enter 'Main' which breaks its loop, and returns to the main menu.

This refactor was an exercise in building more efficient and cleaner CLI menus.




