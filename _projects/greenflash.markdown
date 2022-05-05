---
name: Green Flash
image: /assets/GreenFlash.PNG
layout: default
description: A road trip assistant for RVers and vanlifers.
---

<!-- # Green Flash   -->
<a href="https://green-flash.herokuapp.com/">
<img src="/assets/GreenFlash-logo.PNG" alt="green-flash"  />
</a>

### A road trip assistant for RVers and vanlifers.

**GitHub Repo:** [https://github.com/PeteDarinzo/Green-Flash](https://github.com/PeteDarinzo/Green-Flash/)  
**Live:** [https://green-flash.herokuapp.com/](https://green-flash.herokuapp.com/)  

---


# **Background**

Life on the road is different from that in a fixed residence. Some days are laid back, some are packed with adventure. Some days, you don't know where you'll be sleeping until the sun starts to set. Or you'll wait until you're hungry to start thinking about where to eat. Also, your home (on wheels) requires just as much maintenance, perhaps more, as your daily driver back home.

# **Goal**

I created Green Flash to be a nomad's road trip assistant to find local services, document daily life, and keep a record of maintenance done to the vehicle. To find local restaurants, campsites, or anything else they need, isers simply input their location and what they seek. They are then given a list of results straight from Yelp. For more information, the user can navigate to the Yelp page itself, or save the business for later reference. Creating journal and maintenance logs is simple - just give a title, then input the location, date, and mileage. An image is worth a thousand words, user's can add one to the post as well. The result is an electronic journal of the trip, looking back on past posts give users a welcome reminder of where they were on a certain day, or when they're due for an oil change.

<br>

<img src="/assets/green-flash-home-demo.PNG" alt="green-flash" class="demo-img" />

<br>


# **Technologies**

Here is the tech stack at a glance:
- Python
- Flask
- WTForms
- SQLAlchemy
- Jinja
- JavaScript
- jQuery
- CSS
- Bootstrap
- PostgreSQL
- AWS Simple Storage Service (S3)

**Backend:** Flask was used to make a simple yet robust backend. It also supports some useful libraries, WTForms for form rendering and validation, and SQLAlchemy, for creating and interacting with database tables.

**Frontend:** The frontend was constructed from JavaScript and jQuery, HTML, CSS, and Bootstrap. The Jinja templating language (included with Flask) was used extensively for populating HTML templates with data. Javacript was used to process the forms, and send search queries to the backend, and populate the search page with results. Styling was accomplished with CSS and the Bootstrap library. Images were stored by uploading to AWS S3, see [lessons learned](#lessons-learned) for more information about that.

**Data:** The [Yelp API](https://www.yelp.com/developers/documentation/v3/get_started) is well documented and easy to use. A GET request to the business search endpoint yields all the results which are then displayed to the user.

**Database:** PostgreSQL was used for the database. Tables consist of user data, logs entries, maintenance records, locations, and places. A location is a geographical point, usually a city. The purpose of a locations table is to have one table of locations accessible to all users. A place is a business returned by the Yelp API, and contains only that business' Yelp id. Since Yelp forbids the storing of business data for over twenty four hours, the id must be saved in order to retreive a user's saved places upon login.

# **Features**

All features of the app work as intended. The log and maintenance post functionality feature full CRUD, as does their user profile, where a user can write a short bio about themselves, change their password, and delete their account.

Image upload is supported for each log or maintenance post, and users may also upload an image as their profile picture.

 Authentication is handled via the Flask global object, in which a user's token is stored upon signup or login. Routes that require a user be logged in use middleware to check for the user's token on the global object. Routes are protected to ensure that a user can't perform and CRUD function on another user's saved content.

# **Screenshots**

### _Services search page_

<img src="/assets/green-flash-demo.PNG" alt="green-flash" class="demo-img" />

<br>

### _Log creation page_

<img src="/assets/green-flash-post-demo.PNG" alt="green-flash" class="demo-img" />

<br>

### _User profile page_

<img src="/assets/green-flash-profile-demo.PNG" alt="green-flash" class="demo-img" />

<br>

# **Going Forward**

After completion, the app functions fully as intended. I have personally used it to keep track of maintenance on my campervan, and also as a personal journal. 

At this time a user may only see his or her posts, but I think a version with "friends" and an option to make posts optional to connected travelers would be a fun upgrade. 

# **Lessons Learned**

Fortunately, the created of my first capstone project went quite smooth. The biggest challenges I faced were styling, and implementation of the image upload. 

The first challenge was appearance. I went back and forth between a few layouts and color schemes, but finally settled on the three column "dashboard" for log and maintenance entries, which Bootstrap made relatively easy. The tricky parts came later, e.g. keeping the background image fixed while scrolling on a lengthy post, and preventing the space taken up by the navbar from displacing content below. The lesson learned: spend a little more time considering styling upfront, and don't leave the little details to the end.

The second challenge was image upload. When I began the project, I gave no thought to how users would be able to upload an image. I found out the hard way that Heroku does not support file upload, and I'd have to find another way. Luckily, Heroku does recommend an alternate method, [uploading static assets and files to AWS S3](https://devcenter.heroku.com/articles/s3). I had never worked with AWS previously, but with the help of a few tutorials the learning curve was not too steep. The lesson here is the importance of defining all technical capabilites to the greatest extent possible, not assuming that everything will work out.

# **Misc**

What is a [green flash](https://en.wikipedia.org/wiki/Green_flash)? Simply put, it's an atmospheric phenomenon in which a setting or rising sun gives off green light. I've never seen one myself, but learned of it from a friend who saw on during a sunset on the West coast of Florida. The name is intended to invoke the feeling of adventure on road trips, and I'm always hopeful that I'll one day see one.