---
name: Weatherly
image: /assets/Weatherly.PNG
layout: default
description: An app that lets you optimize your time for movie watching.
---

  <img src="/assets/weatherly-logo.PNG" alt="weatherly-logo"  />
###  An app that lets you optimize your time for movie watching.

**GitHub Repo:** [https://github.com/PeteDarinzo/Weatherly-Frontend](https://github.com/PeteDarinzo/Weatherly-Frontend)  
**Live:** [https://fast-authority.surge.sh/](https://fast-authority.surge.sh/)  


---

# Background

Rainy days and early winter sunsets on the road made movies a necessity to pass downtime. Thankfully, a good friend lent me some DVDs from his collection before I left, and I picked up more as I went from thrift stores. As a result, I saw some new and classic films, and ones that I wouldn't normally consider. I knew it was a hobby I'd like to continue after settling back into domestic life, so I began to think of ways to pair it with my web development skills. 

<p align="center">
  <img src="/assets/Weatherly.PNG" alt="green-flash" style="width: 100%" />
</p>

# Goal 

 My initial idea was simple, make an app for users to search for and save movies. The question was how to go beyond basic CRUD, and make it unique. The answer was an API mashup! I knew there were several terrific, free weather APIs. I had already selected a movie API. Therefore, my goal was to create an app that would analyze the forecast, compare it with a user's preferences, then provide a forecast that rates the compatibility of each day.

# Technologies

Here are the technologies at a glance:
- Express
- Node
- JavaScript
- React
- Redux
- PostgreSQL
- MUI

Being my second big project, Weatherly was a chance to implement my new knowledge of Node.js and Express backends. I also knew I could kick the user interface up a notch with a React and MUI based front end. React made the UI heavy app possible by breaking things down such that I had components for a movie cards, movie detail, and the user profile dashboard. 

There were two engaging parts of the build: using two APIs, and learning a whole new style library, material user interface (MUI).

Fortunately, I chose two excellent, well documented APIs: the [Open Movie Database](https://www.omdbapi.com/), and [Open Weather Map](https://openweathermap.org/).

After using Bootstrap for my first project, and being dissatisfied with reactstrap, I decided to give MUI a try. The learning curve was steep ("why the heck are there 'typographies' everywhere?!"), but once I got a grasp on it, I was cooking with gas.

User data, movies, and a join table linking the two are implemented using PostgreSQL.

User authentication is implemented with JSON web tokens (JWT). User password are stored using Bcrypt. Upon signup or login, a JWT is generated for the user, and stored in the front end for future requests. Middleware is used to verify the presence of a JWT on a request when a user must be logged in, or that the JWT matches the logged in user, for user specific routes.

# Features

After completion, the app functions fully as intended. Upon login, users are presented with a dashboard giving the three day forecast, and a list of their most recently saved movies. A quaint weather quote is also presented. Users may navigate to the search page to find new movies, or the movies page to see what they have saved. The forecast page gives a one week forecast, with a bargraph for each day corresponding to how well the weather matches the user's watch preferences. The profile dashboard gives the user the option to change their geographical location, or to update their weather preferences. 

<!-- <p align="center">
  <img src="/assets/weatherly-profile.PNG" alt="green-flash" style="width: 100%" />
  <img src="/assets/weatherly-search.PNG" alt="green-flash" style="width: 100%" />
  <img src="/assets/weatherly-forecast.PNG" alt="green-flash" style="width: 100%" />
</p> -->

# Going Forward

There are a couple features that would really take the app to the next level. Currently, all of a user's saved movies are grouped together in one list. I would like to implement a search function, and group by genre. 

The preferences page works as intended, but could be made more nuanced. Instead of simply selecting the condition that makes for a good movie watching day, users could be presented with a slider that represents their adversity to certain weather. For example, the rain slider could represent if a user won't go out even in a drizzle, or if it would take a monsoon to keep them indoors. 

# Lessons Learned

The implementation of this app went well, owing to the fact that I took the time to really sketch out of the React interface, and nail down the technical details of where my data would come from. The biggest lesson I learned is to just keep moving, get it working, then go back and add more features if time is available. My mentor gently reminded me that once the app is complete, there will always be time to go back and extend the functionality, but the first priority is to build something that satisfies the requirements, and I can live with at the end of the day.

