# Project Proposal

Question/need:

* What is the framing question of your analysis, or the purpose of the model/system you plan to build?

  Can I use linear regression model to predict IMDb score of movies and tv shows?

* Who benefits from exploring this question or building this model/system?

  potential investor, marketing company, producers

Data Description:

* What dataset(s) do you plan to use, and how will you obtain the data?

  The data sources I'm planning on using are IMDb.com, BoxOfficeMojo.com and possibly rottentomatoes.com and metacritic.com. I'll use BeautifulSoup and Selenium as my main tool to web scrap those data.

* What is an individual sample/unit of analysis in this project? What characteristics/features do you expect to work with?

  A sampe/unit would be an individual movie. I'm expecting to have at least 1000 datapoints and at least 10 features, including year released, MPAA(Motion picture rating), runtime, genre, IMDb review, Metascore, number of reviews, Distributer, Director, Movie Budget, Domestic Grosses, International Grosses, Worldwide Grosses, etc. 

* If modeling, what will you predict as your target?

  Since we're doing linear regression modeling, my target is IMDb review score of a movie.

Tools:

* How do you intend to meet the tools requirement of this project?

  I plan on follow along the course learning webscraping methods and applying them on the project as well as looking up extra resources/tutorial if the learning curve is greater than expected. 

* Are you planning in advance to need or use additional tools beyond those required?

  Not in the mean time. I want to get familiar with the required tools and methods before exploring other options. If I have extra time, I'll attempt to learn additional tools. 

MVP Goal:

* What would a minimum viable product look like for this project?

  A linear regression model that can predict a movie's IMDb score and identify the features that have higher correlations with the target. 
