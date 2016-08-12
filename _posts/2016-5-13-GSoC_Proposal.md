---
layout: post
title: Proposal
---
### Photo Language Translation (PLT) ###

## Systers Questions ##

**1. Are you a Syster [www.systers.org](http://www.systers.org)? Would you join if you are accepted? (Note: Systers is only open to women in computing; if you are male, you may not join, though you are welcome to join systers-dev, our development list and our Slack team channel.)**

Yes of course. It would be a matter of honor for me to be a part of Systers Community and I really like your approach to empower women in the tech field.

**2. How can we reach you (email, GTalk, etc.) if we have questions about your application?**

Email address: [rupinderwadali@gmail.com](mailto:email@domain.com)

IRC nickname: roop

Slack channel: rupinderjit

**3. What is your github username(s)?**

Github username: https://github.com/rupinderwadali(http:github.com)

## Project Specific Questions ##

**4. Which Systers GSoC project are you applying for (please submit a separate application for each project):**

Peace Corps Project (Photo Language Translation)

**4a. What do you plan to accomplish over this summer for this project? (Please tell us what project you want to work on, how you will approach that project portion, and what your milestones are.)**

**Brief Description:**

Photo Language Translation project is helpful for the Peace Corps Volunteers who are working  in different countries and sites which are developing local languages. The photos uploading, Chuukese and English translation are already done and the main requirements of the project are the offline usage of “application”, categorization of the article, add geolocation using OSM, refactoring code and removing the bugs of the existing code.

**Detailed Project Description:**

A lot of work has already been done. I will add the offline feature, categorization of article feature, improve the admin panel’s organization profile work (things are complex, refactoring it and hide the complexity of the work), the working flow of the project is difficult to understand. I will also work on the individual user panel to make it bugs free, I found some bugs like contact number has no validation, it has the option of add new member, site, categories but these options are not working either the user do not have rights or  , search bar did not perform any functionality etc. The detailed description of the work is explained as:

**1. Offline Usage of Web Pages**

This is the main feature that we will be achieving this year and having the higher priority that is level-1. The web pages of the application are accessed offline and when the device is connected to the internet it automatically updates the web pages that are shown offline. For implementing this feature we have three alternatives:

* Using HTML5 

Offline application is a list of URLs- HTML, CSS, JS, images or any kind of Resources.

*Manifest file* points to this list is the home page of the offline application. A web browser
that implements HTML5 offline application will download the resources and cache them
locally and automatically keep local copies up to date.

1. You need to point to the manifest file using a manifest attribute on <html> element.

*<html manifest = “/cache.manifest”>*

2. Cache manifest file: It has three distinct sections:

* *CACHE:* Resources get downloaded and cached locally.

* *NETWORK:* Resources in this section are never cached and are not available offline. 

* *FALLBACK:* Includes the resources and the fallback.

3. When browser notices manifest attribute in <html> element, it fires a checking event and these events are fired on the window.applicationCache object.

![_config.yml]({{ site.baseurl }}/images/cache.png)


* **jQuery Offline Plugin:**

The jQuery offline plugin provides an easy mechanism for retrieving data from a remote server, then caching it. If the user is online, the plugin will transparently request new content from the remote server, firing the callback again if the content has changed. jQuery offline uses the HTML5 localStorage API. jQuery offline is best used in conjunction with *Rack::Offline and jquery-tmpl.* 

* **Test:** To test the functionality of browser with localStorage and without localStorage, ruby is needed on the system.

![_config.yml]({{ site.baseurl }}/images/test.png)

* **SyncIt:**

Synclt is a library to enable us to easily add synchronization to our (offline/ live) web
App. This may be for allowing multiple users/ devices to work offline or because the app
has a live editing session with other users.
So have alternatives to choose one, which is best suitable for our application.

2. **Admin Panel**

Admin can do the task of approving the user request, assigning roles, add new members, articles, languages, country, site, categories and it’s performing all the tasks. Now the question arises what are problems and where we need the improvement? Following are some problems that need improvement and enhancement and the alternatives of the problems.

![_config.yml]({{ site.baseurl }}/images/admin.png) 


* **Categorization of the articles:** 

This is a new feature I wish to add to the application and this feature has priority level-2. Firstly the articles are shown in the manner of rows and columns. We can show the thumbnails of the article with some information like English text and language etc and shown in a dashboard of admin. We can categorize the articles according to category and language of the photo(article). I found two alternatives:

1. **Using the drop-down option:** 

We can categorize them by using the drop-down option. In this, first one option like the category of the photo will be selected after which some filtering on data is applied and it shows the relevant option to a category in the next dropdown. Say our next drop-down options are ‘language’ and choosing it shows only those articles that belong to that particular category and language.

2. **Using the search bar:** 

We can apply the same logic on the search bar to search the data as described in the first alternative but a search bar is used instead of using the drop-down.
And after filtering the data we left with the articles that are belongs to that particular category and language. Such as below:

![_config.yml]({{ site.baseurl }}/images/article.png) 


* **Organization Profile:** 

This feature has priority level-3. “My Organization” option contains only the name of the organization and country and sites options contains the information that basically belongs to the organization. Instead of showing the same detail in two different locations, we can use to display it at one place where it is highly preferable. For an instance, we have the information in “countries” option where the organization has the branches and it includes the information like name of the organization, manager and different sites of the countries. In the “sites” option we have the information about the sites that belongs to that particular country and it include information of country and different sites of the country.

![_config.yml]({{ site.baseurl }}/images/profile.png) 


![_config.yml]({{ site.baseurl }}/images/orgpro.png) 


For exploring this working of form have a look:


![_config.yml]({{ site.baseurl }}/images/listorg.png)


Here first we select the organization then it shows the countries that are belongs to the organization. Same wise when we select the country then it shows the sites of the country and when we select the site it shows the list of the volunteer and contributor.
 
* The role of the user is assigned by the admin. But this option is in the site option of the admin panel. It is not user-friendly. This is the main task of the admin and it resides in another option and one more thing, how would admin know that the user is volunteer or contributor. So, the alternative is that there should be a separate tab for the role of the user in the admin panel or they should assign the role when they are accepted as a member by the admin in “Member option” for simplifying the things. As below diagram shows the working of the Assigning role. When a user select the “Assign Role” tab, it shows two select option where we select the country name and site name. Then it shows the options to add volunteers and contributors and admin assign the role to the user.

![_config.yml]({{ site.baseurl }}/images/assign.png)


**3. Individual Users**

Currently, In individual user panel, user either does not have the permission to add new members, category and new sites or it does not work at all. Though the button to add member, category, site are available but clicking them redirects the page to profile page instead of performing the corresponding actions. I can either remove it or add functionality if a user has the permissions to do these activities. And the same categorization of article feature is applied to this part also. This feature has priority level-4.

**4. Access Management and generating logs:**

 The admin or the higher authority person can access the account of volunteer (or lower authority person). There will be a log file that will have the record of all entries. So that no one misuses their authority.

## MILESTONES:

## Community Bonding Time:

* Interact with community members
* More exploration of Ruby On Rails
* Knowing the code
* Solving issues(#107, #125 or more if have time)

## Detailed Timeline:

**Week 1 (23rd May)**

1. Busy due to exams on 23th may, 26 may, 27 may
2. Get comfortable with the code 

**Week 2 (30th May)**

1. Busy due to exams on 30th may and 31 may
2. Individual User module
* Making existing buttons work

**Week 3 (6th June)**

* Organisation’s Profile
* Fetch the fields of countries and its dependent sites
* When select the site it shows the list of volunteer

**Week 4 (13th June)**

1. Usage of Offline web pages
* Study various methods
* Discuss all the alternatives with mentor and choose one

**Week 5 (27th June)**

* Code cleanup for mid-term evaluation
* Documentation

**Mid-Term Evaluation**

**Week 6 (27th July)**

1. Implementing the offline usage of the application
* Implementing the selected alternative
* Testing and finding bugs, if any

**Week 7 (4th July)**

* Categorization of articles
* Filter the data according to the category and language
* Use search box for filtering

**Week 8, 9 (11th July)**

1. Managing access of Admin, volunteer and contributor
* Adding interface to access management
* Authentication based access to the interface
2. Generate the Log

**Week 10 (25th July)**

Changing Interface

1. Assigning roles
* Create a new tab for assign role to users and remove  the functionality from the Sites tab
* Add dependent dropdown 
* Show the contributors and volunteer form to add
2. Make interactive form

**Week 11 (1st August)**

* Time to make up for missed milestone(if any).
* Code cleanup

**Week 12 (8th August)**

* Testing and remove bugs
* Final deployment

**Week 13 (15 August)**

* Getting reviews from mentors and other community members
* User and Developer Documentation using recommended tools

**Final Evaluation** 

## Availability:

I will not be available on 23th may, 25th may, 26th may, 27th may, 30th may and 31th may due to exams.

## Peace Corps Web Projects

**5. Have you worked in web development? HTML, PhP, JS, or Perl? If so, please describe your experience or project. Whether it is a school assignment, personal project or other experience.**

Yes, I have an interest in web development and also have worked in web development. I am very well acquainted with HTML, PHP and JS and implement these in projects. I worked on the following projects using these platforms:

* I have done my training project in PHP and Wordpress that is "Be Organic" [https://github.com/Rupinderwadali/store](http://github.com/Rupinderwadali/store)

* I contributed in open source project that is "Certificate Generation System": [https://github.com/Rupinderwadali/Certificate](https://github.com/Rupinderwadali/Certificate). It's my first open source project that encourages me to again contribute to open source projects. So here I am participating in GSoC. 

* I also participated in Hackathon "Hack in Punjab". Here we made a simple web application that is "3WC (We Will We Can)” which is in PHP and is to help the needy person. In this application, we just click a photo and upload it where the help is needed or you felt that there is happening something wrong. I did this project in a team. It taught me working in a team with coordination, understanding, faith and much more.

* Currently I am working on "Friend Recommendation System". The front end of the project has been prepared.

**6. Some PCVs are located in remote areas and most mentors are scattered across the globe. Have you worked on projects with remote teams? If so, what tool did you use to collaborate?**

Yes, I have the experience to work on project with remote team. I am comfortable with this. As I used to meet my mentor online and we also work online during my training time. We use the following tools to collaborate:
Google+
Hexchat
General Development and Education Questions

**7. Why do you think you are a good candidate for these projects? Describe the skills you confidently bring to the project, and what you hope to learn from working on this project, and your interest in the Systers mission.**

* Because I love the concept of Open Source. I know my project very well and also understand the requirements of the community. So I think I am a well-equipped person to handle this project and develop a great product for the community. 

* This project is mature and need improvement more and also need refactoring of the code. My previous open source project needed finish up and refactoring, I performed very well. 

* Eager to learn the new things, grasping power is more and work calmly in any situation. Have the ability to work in a team and motivate the other team members to accomplish the goal.

**Systers Mission:**  As we have very less number of women in the technical study as compared to men, I want to be the part of the technical community and spread awareness about women in tech in our society. I will learn a lot being the part of this community and want to contribute more to this program and afterward. 

**8. We have various projects in Python, Ruby, Android, iOS and Ushahidi. Describe the largest project you have completed in any of the programming languages mentioned. If you haven't used any of the programming languages, describe the programming experience you have that will allow you to learn a programming language quickly and be successful on this project.**

I did not complete any large project in any programming languages mentioned above, but I will add one project to the list in my near future that is PLT app in Ruby and using the framework Rails. As I earlier said that I have done some project to implement what I learned. I will learn a programming language quickly as well as also implement it successfully. I have setup the project environment, find contact number validation bug in existing project and also work on #115 and #107 issues of the project.

**9. We use GitHub and LaunchPad for our projects. Do you have experience with any version control software?**

Yes, I have experience with the Github. My projects are also on Github. I think it is necessary for every programmer to have experience of version control software and specially when working in a team also. When we contribute to open source world, one should be aware of version controlling systems. I am comfortable with using Github.

**10. Describe any plans you have over the time period of GSOC (including the community bonding period) in addition to GSoC, such as classes, a summer job, vacation plans, master's thesis, etc.**

I am an undergraduate student at Guru Nanak Dev Engineering College, Ludhiana. During the summer, I will be wholly committed to GSoC. I will dedicate a minimum of 42 to 45 hours/week, can spend more if required. 

**11. Education:**

**a. What year are you in school?**

I am third-year student of B.Tech. in Information Technology at Guru Nanak Dev Engineering College, Ludhiana, India.
                                                
**b. What programming courses have you taken?**

Currently, Web Technologies is a programming course in our academics. As for basis, I did C, C++, Java, Database in our academic. Also enroll in various MOOCs that offering courses like Coursera, codecademy etc. to learn Web development.

* **What did you like about them? What did you not like?**

The programming courses provide us the basis and help us to start implementing them what we have learned till now and courses that we join except out academics help us to enhance the self-learning skill.
	
**c. What is your major?**

Information Technology.

* **Why have you chosen that?**

Actually, it’s an I.T. revolution. I.T. is everywhere, it is in every field. It holds a vital part in almost all the activities we do in our daily life. It has the power to change the way of our living and thinking and makes our live better. 
		  
**d. Have you done group projects (programming or otherwise)?**

Yes, I have done the group projects as described earlier. I also list up here:

1. I also participated in Hackathon "Hack in Punjab". Here we made a simple web application that is "3WC (We Will We Can)” which is in PHP and is to help the needy person. In this application, we just click a photo and upload it where the help is needed or you felt that there is happening something wrong. I did this project in a team. It taught me working in a team with coordination, understanding, faith and much more.

2. My class project that is assigned to me and my team members is "Friend Recommendation System". The front end of the project is prepared.
		
* **What was your primary contribution to/role in the group?**

I played the role of web developer and designer in both the projects. And also played the role of Ideator in “3WC” project.

**e. What made working in a group better than alone? What made it harder?**

While working in a team we empower and motivate each other and help each other and did the whole work in the modular form. The coordination between team member is an important aspect that sometimes makes it harder to work.

**12. Do you have work experience in programming? Tell us about it.**

Yes, I have work experience in programming. As I explained earlier the projects I have done. It’s really great to be a programmer. Programming makes our life so comfortable. I think a programmer should be lazy. As if he/she don’t want to do things repeatedly then he/she think about to that thing in an easy and automatic way. That’s what a programmer do.

**13. Do you have previous open source experience? Tell us what you have done.**

Yes, I have previous open source experience with the “Certificate Generation System”. I contributed to this project and refactored the code and made it runnable. Besides I solved some bugs in software like “Zlib extension”, “fetch data from CSV file” and “pdf conversion part” of the
software. 

**14. Tell us one interesting fact about yourself.**

Once if I have decided that I will do it then I never give up and keep on trying it again and again until it’s not complete. I have a hunger for knowledge and make it eagerness to learn things. Here I have the opportunity to work with great developers and in a wonderful community.







