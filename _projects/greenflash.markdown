---
name: Green Flash
image: /assets/GreenFlash.PNG
layout: default
description: A road trip assistant for RVers and vanlifers.
---

# Green Flash  
### A road trip assistant for RVers and vanlifers.

**GitHub Repo:** [https://github.com/PeteDarinzo/Green-Flash](https://github.com/PeteDarinzo/Green-Flash/)  
**Live:** [https://green-flash.herokuapp.com/](https://green-flash.herokuapp.com/)  

---

# Background

Life on the road is different from that in a fixed residence. Some days are laid back, some are packed with adventure. Some days, you won't know where you'll be sleeping until the sun starts to set. Or you'll wait until you're hungry to start thinking about where to eat. Also, your home (on wheels) requires just as much maintenance, perhaps more, as your daily driver back home.

<p align="center">
  <img src="/assets/GreenFlash.PNG" alt="green-flash" width="500" />
</p>

# Goal

I created Green Flash to be a road trip assistant for nomads to find local services, document daily life, and keep a record of maintenance done to the vehicle. Users simply add their location and the type of service they seek, are given results straight from Yelp. For more information, the user can navigate to the Yelp page itself, or save the business for later reference. Creating journal and maintenance logs are simple - just give a title, then input the location, date, and mileage. An image is worth a thousand words, user's can add one to the post as well. Looking back on past post's give user's a welcome reminder of where they were on a certain day, or when they're due for an oil change.

<p align="center">
  <img src="/assets/Log.PNG" alt="green-flash" />
</p>

# Technologies

Here is the tech stack at a glance:
- Python
- Flask
- WTForms
- PostgreSQL
- SQLAlchemy
- JavaScript
- CSS
- Bootstrap
- AWS Simple Storage Service (S3)

Flask was the first backend framework that I learned, and made a good foundation for the app. It also supports some useful libraries, WTForms form rendering and validation, and SQLAlchemy, used to create and interact with the database tables. Javacript was used to process the forms, and send search queries to the backend, and populate the search page with results. Styling was accomplished with CSS and the Bootstrap library. Images were stored by uploading to AWS S3.

# Features

All features of the app work as intended. The log and maintenance post functionality are full CRUD. On the profile page, a user can edit a short bio about themselves, change their password, or even delete their account.

Images can be uploaded for each log or maintenance post, and the user may also upload an image as their profile avatar.

In regards to authentication, the app uses the global object to store a user's token up signup or login. Routes that require a user be logged in use middleware that checks for the user's token on the global object. Routes are protected to ensure that a user can't perform and CRUD function on another user's posts.

# Next steps

After completion, the app functions fully as intended. I have personally used it to keep track of maintenance on my campervan, and also a personal journal. 

At this time a user may only see his or her posts, but I think a version with "friends" and an option to make posts optional to connected travelers would be fun.

# Lessons Learned

Fortunately, the implementation went quite smooth. The biggest challenges I faced were styling, and implementation of the image upload. 

The first challenge was how to make the website look. I went back and forth between a few layouts and color schemes, but finally settled on the three column "dashboard", which Bootstrap made relatively easy. 

When I began the project, I gave no thought to how users would be able to upload an image. I found out the hard way that Heroku does not support file upload, and I'd have to find another way. Luckily, Heroku does recommend an alternate method: upload to AWS S3. I had never worked with AWS previously, but with the help of a few tutorials the learning curve was not too steep. The lesson here is the importance of defining all technical capabilites to the greatest extent possible, not assuming that everything will work out.

# Misc

What is a [green flash](https://en.wikipedia.org/wiki/Green_flash)? Simply put, it's an atmospheric phenomenon in which a setting or rising sun gives off green light. I've never seen one myself, but learned of it from a friend who saw on during a sunset on the West coast of Florida. The name is intended to invoke the feeling of adventure on road trips, and I'm always hopeful that I'll one day see one.