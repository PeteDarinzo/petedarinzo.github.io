---
name: Weatherly
image: /assets/Weatherly.PNG
layout: default
description: An app that lets you optimize your movie watching time.
---
<a href="https://fast-authority.surge.sh/">
  <img src="/assets/weatherly-logo.PNG" alt="weatherly-logo"  />
</a>

###  An app that lets you optimize your movie watching time.

**GitHub Repo:** [https://github.com/PeteDarinzo/Weatherly-Frontend](https://github.com/PeteDarinzo/Weatherly-Frontend)  
**Live:** [https://fast-authority.surge.sh/](https://fast-authority.surge.sh/)  


---


# **Background**

Rainy days and early winter sunsets on the road made movies a necessity to pass downtime. Thankfully, a good friend lent me some DVDs from his collection before I left, and I picked up more from thrift stores as the journey progressed. As a result, I saw some new films, classic ones, and ones that I wouldn't normally consider. I knew film appreciation was a hobby I'd like to continue after settling back into domestic life, so for my second capstone project, I began to think of ways to pair it with my web development skills. 

# **Goal**

 My initial idea was simple, make an app for users to search for and save movies. The question was how to go beyond basic CRUD, and make it unique, something people would really like to use. The answer was an API mashup! I had already selected a movie API, and I knew there were several terrific, free weather APIs. With that in mind, my goal became to create an app that would give a users a place to keep their "to-watch list", while also analyzing upcoming weather, comparing it with a user's ideal watching conditions, and then providing a personalized forecast.

<br>

<img src="/assets/weatherly-landing-page.PNG" alt="weatherly-logo" class="demo-img" />

<br>

# **Technologies**

Here are the technologies at a glance:
- Express
- Node
- JavaScript
- React
- Redux
- PostgreSQL
- Material-UI (MUI)

**Backend:** Being my second big project, Weatherly was a chance to implement my new knowledge of Node.js and Express backends. Flask is a good first time framework, but I enjoyed being able to use JavaScript for the front and backends.

**Frontend:** I also knew I could kick the user interface up a notch with a React I based front end. React and React-Router made the front end a breeze, I scarcely had any of the styling trouble that I encountered on my first capstone.

**MUI:** After using Bootstrap for my first project, and being dissatisfied with reactstrap, I decided to give MUI a try. The learning curve was steep ("why the heck are there 'typographies' everywhere?!"), but once I got a grasp on it, I was cooking with gas. MUI is straightforward to use, and the components look great as-is, but are also easy to customize. There were also parts of the user interface that I'm not sure how I'd even begin to implement without MUI, in particular the double slider for selecting a user's temperature preference. It's a library I'm very glad to have in my toolkit.

**Redux:** This was my first big project using Redux, and believe me: it was a life saver. The Redux unit was optional in Springboard, and looking back I'm very glad I chose to learn it. The major benefit is reducing prop drilling by storing user info, a list of movies, and the forecast, making all of them easily accessible to all components. The second big benefit was how it perfectly pairs with MUI's "snackbar" component, basically flashed message. I followed an excellent tutorial on how to implement the snackbar component with Redux, and it added a lot to the app.

**Data:** Fortunately, I chose two excellent, well documented APIs: the [Open Movie Database](https://www.omdbapi.com/), and [Open Weather Map](https://openweathermap.org/). The Open Weather Map was particularly useful. Not only did it provide weather data, but also performed geocoding on a user's location by converting a postal code and country into latitude and longitude, which it needs to return the forecast data.

**Database:** User data, movies, and a join table linking the two are implemented using PostgreSQL. Database interaction was handled using the node-postgres package. 

# **Features**

After completion, the app functions fully as intended. Upon login, users are presented with a dashboard giving the three day forecast, and a list of their most recently saved movies. A quaint weather quote is also presented.

Users may navigate to the search page to find new movies, or the movies page to see what they have saved on their to-watch list. 

The forecast page gives a one week forecast, with a bargraph for each day corresponding to how well the weather matches the user's watch preferences. 

The profile dashboard gives the user the option to change their geographical location, or to update their weather preferences. A user can choose between imperial or metric units of measurement, select the temperature range and weather conditions in which they would prefer to watch movies.

User authentication is implemented with JSON web tokens (JWT). Upon signup or login, a JWT is generated for the user, and stored in the front end for future requests. Middleware is used to verify the presence of a JWT on a request when a user must be logged in, or that the JWT matches the logged in user, for user specific routes. 

# **Screenshots**

### _Movie search page_

<img src="/assets/weatherly-search-demo.PNG" alt="weatherly-logo" class="demo-img" />

<br>

### _User profile_

<img src="/assets/weatherly-profile-demo.PNG" alt="weatherly-logo" class="demo-img" />

<br>

### _Forecast page_

<img src="/assets/weatherly-forecast-demo.PNG" alt="weatherly-forecast-demo" class="demo-img" />

<br>

# **Going Forward**

There are a couple of features that would really take the app to the next level.  

Currently, all of a user's saved movies are grouped together in one list. I would like to implement a search function, and group by genre. This would make it much easier for users with a long "to-watch" list to find a particular movie they have saved.

Also regarding movies, I initially had plans for users to mark a movie "watched" once they had seen it, and possibly record their notes or a brief review. This would go very well with a "friends" feature, where user's can see what their friends are watching, and compare reviews of movies.

The preferences page works as intended, but could be made more nuanced. Instead of simply selecting the condition that makes for a good movie watching day, users could be presented with a slider that represents their adversity to certain weather. For example, the rain slider could represent if a user won't go out even in a drizzle, or if it would take a monsoon to keep them indoors. 

# **Lessons Learned**

The implementation of this app went well, owing to the fact that I took the time to really sketch out of the React interface and nail down the technical details of where my data would come from.  

The biggest lesson I learned is to just keep moving, get the project working, then go back and add more features if time is available. My mentor would often remind me that once the app is complete, there will always be time to go back and extend the functionality. The first priority is to build something that satisfies the project requirements, and I can live with at the end of the day.

