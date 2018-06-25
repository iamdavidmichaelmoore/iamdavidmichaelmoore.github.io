---
layout: post
title:      "CLI Data Gem Project: True Crime Documentary "Database""
date:       2018-06-23 18:55:10 -0400
permalink:  cli_data_gem_project_true_crime_documentary_database
---


At last, I am complete with my project.  It took exactly two weeks.

**Overview**

The name of my project is True Crime Documentary Database. It offers a list film and television documentary film titles in the True Crime genre. 

(Note: Although it indeed is not a database, its functions point in the direction of a database. The term "database" is used here loosely.)  

I used the Nokogiri gem to scrape the site crimedocumentary.com.  I created an application that scrapes the category names, the URLs, and the documentary attributes that exist within each URL path.  The program should deliver a menu of options: to browse the documentaries by category or to see a full listing of documentary titles.  

Selecting category delivers a list of documentaries displayed with their title, year, category, synopsis, and full synopsis URL.  Otherwise, if list all documentaries is chosen, then the user is taken to a submenu from which to select a title.  Similarly, the selection displays the documentary’s details.

**Building The Project**

Now, based on my initial review of the HTML I felt assured that I could achieve this project based on what I had learned in the previous labs leading up to my CLI data gem.  What I hadn’t given better attention to was the layout of the site and how it delivered the data.  The categories of a film are front and center, while the documentaries generate (no HTML to scrape) in many places, except inside of category link paths in the right sidebar.  Sadly, I hadn’t noticed this quirk until long after getting approval and having coded my scraper class. (With respect to object orientation, this presents some coding challenges. It would be hard to maintain the has a/has  many object relationship that I planned.)  In the scraper class is when I realized I might run into trouble when I’d have to connect these objects in the CLI controller class.  Sure enough, that difficulty arose. I worked hard to refactor the entire project from start to finish and ended up with a better product.

Something I encountered was that the number of links I decided to scrape tacked on at least 15 to 20 seconds of load time at the start of the program. Coincidentally, in one of my recent study groups, the instructor mentioned how it might sometimes be a better option to have the data load (scrape) upon selection by the user. I thought it was an excellent idea!  However, given how far I had come and that I was already in the middle of rebuilding my program from scratch (I created a branch and merged later), it would have proven difficult timewise.  So again, the layout and coding of the site presented a hurdle that made any new idea unfeasible.


Overall, I believe that I have met the requirements of the project by demonstrating that I have a good grasp of object orientation and working confidence in coding in Ruby.  

**Some Afterthoughts**

* Simple ideas are still complicated when it comes time to code them!
* What you think is simple may not be simple enough.
* Projects fan the flames of enduring appreciation for Google search! :)
* This project was, *hard*! However, it I love it! 
* Coding is fun. Learning to code is fun and uncannily cathartic. O_O

Bottom line: The CLI data gem was a challenging project, while also gratifying!

Access the repository [here](https://github.com/iamdavidmichaelmoore/true-crime-documentaries).

UPDATE:  24 June 2018 - This video walk-through demonstrates some changes/additions that were made since the publication of this post.  See my walk-through [here](https://youtu.be/1EGOcOhAYpM).




