---
layout: post
title:      "The Case of the Sinatra Playlister"
date:       2018-09-19 12:46:28 -0400
permalink:  the_case_of_the_sinatra_playlister
---


This was the most challenging and grueling lab to date! But first an anecdote.

As of today I have completed Sinatra Playlister Lab. No lie. It took me roughly a month and a half to finish it.  Let me explain that I was once a full-time student with no daytime work obligations. Every single day was mine to devote to Learn.co.  Then I went back to work by the time I was mid-way through the Sinatra curriculum on Learn.co.   Working roughly 8 am to 4 pm workdays on top of family and social obligations with school left me with two-hour periods per night at best during the week and weekends to make headway through the curriculum.

Why share the anecdote? I want other students to get a sense of realness from me, at least.  It can serve as at least one example or barometer for a working part-time student...at the risk of sounding like I'm complaining. Not sorry.  This is real life folks!

At any rate, it is a wonderful relief to have struggled, striven, and thrown my computer at a wall to get this far.  …Okay. I didn’t throw my computer or anything.  But the Office Space computer smash GIF went through my mind on many late nights.  One word: catharsis. You have to have a sense of humor as a coder. Laugh at yourself, the situation, and don't take things too seriously, lest you get in your own way.

In seriousness, here are some tips for getting through this lab without fear of a spasmodic episode of violence against your tech. (lol)

* Follow the test specs in order!

* You will have to create a module for two common methods; one an instance method and the other a class method.

* Enable sessions in the `application_controller.rb` file, as it is a parent class to the `artist`, `genres`, and `songs` controllers.

* Place the `use Rack::Flash` code directly within the `SongController` class.

* The flash message will go in your `post` and `patch` routes of your `Songs` controller.

* The test specs have keywords that refer to the Capybara for things it will look for in your HTML forms, such as `fill_in` and `click_on`.

* Give careful attention to the test spec lines of code that begin with `expect(page)`, as they are clues to passing several test specs.

* In your `new.erb` and `edit.erb` `Song` forms, ensure that you begin your iterator with a direct call to the `Genre` class as opposed to store `Genre.all` as an instance variable within the `Songs` controller.  Doing the latter will produce a confusing error message that won't clue you into the former solution!

	`<% Genre.all.each do |genre| %>`
    	--code--
    `<% end %>`
    

* Make sure to add the correct values for the `name` and `id` attributes of each input HTML tag in your `edit.erb` and `new.erb` forms within the `Songs` view. 


* IMPORTANT! When you create your `edit.erb` form in the `Songs` view make sure to add the `Artist` attribute with its erb value from the database.  Otherwise, several remaining spec tests will not pass

All of these bullet points were major delays towards completion!  Maybe I didn’t remember past lessons well.  Maybe I had other things on my mind. Who knows what? But I’m sharing them for any other student that wants to avoid the frustrations I ran into.

Just paying it forward! :)

Happy coding!

Originally posted on [iamdavidmoore.com](https://iamdavidmichaelmoore.com).


