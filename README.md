## Rocket League Player Statistics Data Visualization
Visit my GitHub hosted visualization: [https://dennisjunior111.github.io/dataviz-RocketLeagueStats/](https://dennisjunior111.github.io/dataviz-RocketLeagueStats/)

Feel free to visit my original vis, where I conduct my initial testing on, built with block builder://bl.ocks.org/dennisjunior111/92bf6064cd1d5810be1bd17f67deb95b](http://bl.ocks.org/dennisjunior111/92bf6064cd1d5810be1bd17f67deb95b)

# General Overview
## What is Rocket League?
This visualization describes [Rocket League](https://www.rocketleague.com/) statistics generated by top players in the first three seasons of Rocket League's League Play (qualifiers to participate in each years Rocket League Champtionship Series). Rocket League is a vehicular soccer video game developed and published by Psonix. Similar to physical sports (soccer, football, basketball, etc.), Rocket League has a very large following and is one of the larger eSports available. As such, statistics of players and games are important in understanding how the game, and how it is played, changes over time and between players. 

# The Data
## Data Source
The original compiled data can be found at [Parallel.GG] (rl.parallel.gg), a site to browse Rocket League Championship Series Statistics. I selected a subset of the data hosted here, specifically statistics of the first three seasons of Rocket League's League Play. This data was choosen as it had the largest available public playerbase, and data was consistent over the years. 

## Data Pre-Processing
The raw data found on Parallel.GG first needed to be processed in order to create a vis with it. Data first needed to be merged from multiple web pages into csv format. The website has no download feature, and thus manual web scraping was done. In addition, team data was difficult to extract directly from the web pages. Team logos/urls were posted instead of the actual team names. Since there were not too many individual teams, I updated the team names manually. The processed CSV version of the data can be found on my Github.

# The Vis
## Interactions
My vis serves as an interactive scatter plot where a user can mix-and-match various numerical and categorical player attributes. It demonstrates usage of a new library called d3-component and Redux to create the scatter plot with various menus. The default scatter plot describes an individuals win percentage to their miscellaneous score per game (score which is aquired through objectives such as scoring, assiting, clearing the ball, saving the ball, etc.). The user may select the continuous statistics as either the x-axis or y-axis. One can also select a nominal attribute to color the corresponding circles. One may hover over a specific individual point to view exact statistics for that player.

## Prototypes
The very first prototype created was a non-interactive one. It began by displaying only Win Percentage on the X-axis and the Mischelanous Score per Game on the Y-axis. Color of points depicted the season the data was from, while the radius reflected the Total Games Played. The scatterplot provided insight, but lacked the abilitiy to answer multiple questions on the fly. 

![](https://github.com/dennisjunior111/dataviz-RocketLeagueStats/blob/master/image/first-prototype-scatterplot.png?raw=true "Initial Scatterplot Prototype")

I wanted to create a vis that would allow the user to compare correlations between certain player statistics. One may ask who are the best players? This would be easy, and require little interactivity, if the term 'best' was well defined for all individuals. 'Best' for some may be indicated by goals made, while others may see their misc. score or defends to put them on the top. What if 'best' is indicated by multiple statistics? Other questions a user may have could include 'how does my favorite player stack up against others,' or 'which players have unique playstyles?' With these questions in mind, I sketched my interactive vis.

![](https://github.com/dennisjunior111/dataviz-RocketLeagueStats/blob/master/image/first-sketch-scatterplot.jpg "Interactive Vis Sketch")

As you can see, I have not implemted all of my sketched vis. Specifically, my table selection and individual player filtering was cut. This was do to complexity and difficulties learning D3.js. Over time, I hope to create and link my table of players to provide the user the ability to remove or highlight specific individuals throughout the scatterplot who may or may not be close to one another statistically.

## Sources and Inspirations

This project is a fork from a template project, with my own code specifically for Rocket League Statistics visualization.

The template project that uses Webpack and D3. Designed as a starting point for interactive data visualization projects that require JavaScript code to be organized across many files (as ES6 modules).

The starter code here is from [Stylized Scatter Plot with Color Legend](https://bl.ocks.org/curran/ecb09f2605c7fbbadf0eeb75da5f0a6b).


## How to Run Locally
This project uses NPM and Webpack. To get started, clone the repository and install dependencies like this:

```
cd dataviz-RockLeagueViz
npm install
```

You'll need to build the JavaScript bundle using WebPack, using this command:

```
npm run build
```

To see the page run, you'll need to serve the site using a local HTTP server.

```
npm install -g http-server
http-server
```

Now the site should be available at localhost:8080.

For automatic refreshing during development, you can start the Webpack Dev Server like this:

```
npm run serve
```
