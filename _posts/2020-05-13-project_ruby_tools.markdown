---
layout: post
title:      "Project Ruby Tools"
date:       2020-05-13 20:43:02 -0400
permalink:  project_ruby_tools
---



My name is Franklyn….
And this….
is a story about….
a man….
a project …..
and a goal……..

WARNING: I’ve only been at this for three weeks, so concepts and technical terms are still bit shaky at best

RUBY
NOKOGIRI

Scraper

What is to scrape?

What is the act of scraping?

**Scraping**

Scraping is used to take certain elements or data that you want from a website. This is a very useful tool!! because>//….why???!!!
You can take that data and display in your app
Instead of going to a website filled with graphics and javaScript…you can just go to a ruby made app that takes the nitty gritty of a website. It trims off the fat for you. It uses a gem called Nokogiri to do so. A gem is a ruby tool that does different functions for you in the background. Nokogiri goes in a website quickly in and quickly out. Just like what it means in Japanese.
This a very useful tool for a couple of reasons. Lets say you are in an area with bad internet connection and you need to see information on a site for research that you are doing. Sometimes these websites can’t load up or take forever because of a lot background activity you can’t see. Activity happening in the server side, javascript, not client side, HTML.
I had some trouble with grasping the logic behind the Nokogiri and scraping at first.
Nokogiri and Scraping
When I first started using the scraper tool I was pretty confident in using it. I believed that I understood how it works just for the fact that I have had made websites previously. I was quickly humbled to understand there is much more than that. Every step I took to better understand how Nokogiri works it was like it was being used on me. Taking away the fat of the unnecessary and leaving the lean protein packed meat.
The way that the scraper tool works is as follows:
I had to look at the site and see what did I want to in the site.
I had to also see how the site was laid out. Then I had to inspect the website to see what class names where common, and how the site was setup. Did it have common class names, class names describing the actual item it contains? This was a problem I saw in many websites. Maybe not a problem for the developer, just for me. I understood that when it comes to scraping it is best to pick a website that has common <div> class names and even better for the information to be in a common <div> to just iterate through the information.
It took me a bit to find a website that I wanted to scrape.
I finally found one that looked clean, and had what I needed to get my app started.
I was excited!!
But like something quick.
My excitement ceased.
I was getting data but not what I wanted or how I wanted it.
I wanted to make sure the information I scrape is what I want and then I can choose how I wanted it presented.
I scrounged and scrounged through the div’s to uncover that the div’s I wanted had different class names, and inside those div’s those div’s had different class names. I know `divception`!
In retrospect I could have been able to get the data how I wanted but didn’t find it efficient at the time to scrape that site. Time was not on my side.

I found a new site that made more sense for me to scrape.:
www.ruby-tools.com
I really like how the information is relayed to the user. Very clean and organized.

This time though, I learned my lesson.
I looked at the website and inspected it, with the inspector tool. You can do so by right clicking on a website, click inspect or pressing F12 on the keyboard. This opens a side panel with the website’s document or skeleton. Here you can see different names in tags, <>. You might see a <h1> or a <h2> even and a <h3>. There are a pretty finite number of tags that are used when writing websites with HTML. The one that was most important for me was the <div>. Most websites house the body of information inside of a <div> inside of the <body>.


Housing the data inside the <div> makes making changes to the sites style much easier. It makes everything more streamline and one can easily adjust the layout of the site this way.
When I inspected this website I saw how clean everything was. It was like magic every time I opened a div tag and saw how uniform the information was. Every web-page was like that. Eureka! This was it.
I started scraping the site and got what I wanted and more!….
I just want to iterate that when you scrape you then want to iterate over a div where all the information you want is housed.

For me i wanted the popular categories, so I used div that contained the whole cards of popular categories. I had originally use a class name that was common throughout all the <div>’s on the site. Thankfully my cohort lead was able to point it out.

At this point I had felt good about scraping at the first level. Felt like smooth sailing from here
I was not done scraping just yet. I had to scrape on a second level. Because of how the first layer was scraped,I was able to get a link for each of the popular categories. I could then take the website for each category I scraped, use those links to scrape again and get the information I want from each site.

My issue was I was only getting the last element from the second site through the scrape and a description. I didn’t have time to figure out exactly how or why this was happening. All I understood was that I need to change either how I iterate through the scrape or what class name I was using for the scrape.
For the time being I used what I could get to get the app to work.
I think my app is mighty fine, definitely not perfect.

With this project I was able to better grasp what iterator methods do like, each and map.
You know the saying what happens in Vegas stays in Vegas. The each method is kind of like that. Each takes an array and puts out that same data, what ever changes it went through does not get stored.
Map takes the data and alters its output to whatever you put it through.

Sounds like a rough time but it’s not too bad. Depending on what you want to do to your data this can be a good thing. I had used these two throughout my app to get the data I needed and make the app function how I want it to.
Overall had a lot of fun doing this. 10/10 would recommend to any one who wants to be curious about computer science, could be loads of headaches and fun.

This is great resource about NOKOGIRI:
https://nokogiri.org/tutorials/installing_nokogiri.html
