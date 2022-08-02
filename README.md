{
 "cells": [
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "# Microsoft's Foray Into the Movie World\n",
    "Flatiron School Data Science: Project 1\n",
    "- **Author**: Zaid Shoorbajee\n",
    "- **Instructor**: Matt Carr\n",
    "- **Pace**: Flex, 20 weeks"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "![Microsoft Building](./images/msft-bldg-cropped.jpg)\n",
    "Image source: [Pixabay](https://pixabay.com/photos/building-cologne-facade-1011876/)"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "## Overview\n",
    "\n",
    "This project analyzes data about the ratings and popularity of movies to make recommendations to Microsoft, which intends to launch its own movie studio. As a newcomer to the scene, Microsoft has asked for recommendations on what types of movies perform well among audiences. I have available to me movie datasets from Box Office Mojo, IMDb, Rotten Tomatoes, The Movie Database, and The Numbers. I derive my conclusions mainly from the **IMDb datasets**, which contain information about movies from 2010 to 2019, including, genres, average user rating, and the number of users who voted on each movie. As a result of the analysis, I was able to distill 10 well-peforming genres for Microsoft to focus on, as well as make recommendations about how much of its budget it should focus on 1) comedies and 2) animated movies."
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "___"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "## Business Problem\n",
    "\n",
    "**Measuing success:** A first instict might be to narrow down the attributes of movies that have the highest return-on-investment at the box office. However, in the streaming age, that might not be the best measure of success. Popular movies are increasingly being [released directly to streaming services](https://variety.com/2022/film/box-office/disney-pixar-turning-red-disney-plus-subscribers-1235149836/), and the COVID-19 pandemic has dissuaded many people from going to the theaters anymore. A better measure of success would be the number of people that will actually watch the movie. Whether Microsoft plans to sell its movies to distributors like Netflix or spin up its own streaming service to host the films, it needs to determine what kinds of movies are going to attract the most viewers in numbers.\n",
    "\n",
    "I use the **number of votes a movie has received** on IMDb as an analogue for the number of viewers. The votes may be negative or positive, but we can infer that a vote means someone actually watched the film. Using this metric, I attempt to answer these questions:\n",
    "\n",
    "- Which 10 genres tend to perform best?\n",
    "- How much should Microsoft focus on making comedies? \n",
    "- How much should Microsoft focus on making animated movies?\n",
    "\n",
    "*As explained in more detail in the full Jupyter Notebook, I have also isolated the top 10% of movies (in terms of number of votes). There are a number of reasons for this, but it boils down to wanting to draw conclusions from a subset of the best-performing movies, as opposed to a cacophony of niche movies (which is the bulk of movies on IMDb).*\n",
    "___"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "![Person watching TV](./images/streaming-cropped.jpg)\n",
    "Image source: [Pixabay](https://pixabay.com/photos/tv-man-watching-room-office-3774381/)"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "## Data Understanding\n",
    "\n",
    "IMDb is one of the most popular websites for basic facts about movies and TV shows, as well as user reviews. It claims to have nearly [600,000 movies](https://www.imdb.com/pressroom/stats/) listed and is [ranked 75th](https://www.alexa.com/siteinfo/imdb.com) in in global internet engagement. \n",
    "\n",
    "The data I've been provided is housed in a SQL file, from which I primarily use two tables:\n",
    "- `movie_basics`: Contains information about each movie's name, release year, runtime, and genres.\n",
    "- `movie_ratings`: Contains a weighted average of all the individual user ratings and the number of votes a movie has received.\n",
    "\n",
    "More information [here](https://www.imdb.com/interfaces/).\n",
    "\n",
    "The two tables have a shared column `movie_id`, which is a unique identifier for each movie. I grouped the movies by genre to see each genre's average number of votes.\n",
    "\n",
    "---"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "## Measuring Success\n",
    "\n",
    "I use **number of votes** as an indicator of a movie's of success. In the streaming age, this is arguably a better indicator of a movie's popularity as opposed to return on investment at the box office.\n",
    "\n",
    "I also found that **number of votes and average rating are positively correlated.** Thus, in choosing number of votes as our measure of success, we are reassured that that it's generally associated with a higher movie rating.\n",
    "\n",
    "---"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "## Results: \n",
    "\n",
    "### The top 10 movie genres in terms of average number of votes on IMDb are:\n",
    "- Adventure\n",
    "- Fantasy\n",
    "- Sci-Fi\n",
    "- Animation\n",
    "- Mystery\n",
    "- Western\n",
    "- Action\n",
    "- Crime\n",
    "- Biography\n",
    "- Romance\n",
    "\n",
    "![Number of votes on movies by genre](./images/top_genres.png)\n",
    "\n",
    "---\n",
    "\n",
    "### Of the top 10% best-performing movies, 2,281 out of 7,304 — or 31.22% — are comedies.\n",
    "\n",
    "![Breakdown by comedy](./images/comedies.png)\n",
    "\n",
    "---\n",
    "\n",
    "### Of the top 10% best-performing movies, 287 out of 7,304, — or 3.93% — are animated.\n",
    "\n",
    "![Breakdown by animated](./images/animated.png)\n",
    "\n",
    "---"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "## Recommendations\n",
    "\n",
    "In this analysis I attemped to determine the most successful movie genres as well as what proportions of movies are comedies or animated. I arrived at three recommendations for what kinds of movies Microsoft should make:\n",
    "\n",
    "1. Microsoft should focus its efforts on movies with some combination of these genres:\n",
    "\n",
    "    - Adventure\n",
    "    - Fantasy\n",
    "    - Sci-Fi\n",
    "    - Animation\n",
    "    - Mystery\n",
    "    - Western\n",
    "    - Action\n",
    "    - Crime\n",
    "    - Biography\n",
    "    - Romance\n",
    "    \n",
    "    \n",
    "2. Microsoft should focus about a third of its efforts on comedy movies.\n",
    "\n",
    "3. Microsoft should focus about 4 percent of its efforts on animated movies.\n",
    "___"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "## Next Steps\n",
    "\n",
    "As I mentioned before, I came to these conclusions after dropping 90% of the data I had available to me. I justified this by saying that those were niche movies that barely a thousand or so people on the internet knew of, and that those weren’t the types of movies I’d want to analyze when making recommendations to a multi-billion dollar company like Microsoft.\n",
    "\n",
    "I could further explore this by **answering the same questions for the bottom 90%** as I did for the top 10%. Knowing the differences between the tiers might lead to other helpful insights.\n",
    "\n",
    "Having said that, **the division between the two tiers is arbitrary**; I could have looked at the top 5% or 25%. Another way to go about this would be to merge in a new dataset that told us which movie studio is behind each movie. I could then separate the data into movies made by established, big-budget studios and movies that are not. Looking at the differences among movies in those two tiers might give us different results and possibly lead to different recommendations."
   ]
  }
 ],
 "metadata": {
  "interpreter": {
   "hash": "9066515e2c74396c3dc22ac47132aa38294e007e809df6151bffa6da73189c66"
  },
  "kernelspec": {
   "display_name": "Python 3",
   "language": "python",
   "name": "python3"
  },
  "language_info": {
   "codemirror_mode": {
    "name": "ipython",
    "version": 3
   },
   "file_extension": ".py",
   "mimetype": "text/x-python",
   "name": "python",
   "nbconvert_exporter": "python",
   "pygments_lexer": "ipython3",
   "version": "3.8.5"
  }
 },
 "nbformat": 4,
 "nbformat_minor": 4
}
