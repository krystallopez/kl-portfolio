# Project 3 - JediVerse

A high-level overview of the project purpose:

## :memo: Situation

The JediVerse is a frontend web application that I created during the Multiverse Frontend Module. The JediVerse is a complete encyclopedia of all the people, planets, films, species, and starships that make up the Star Wars Universe. 

## :pushpin: Task 

- There are multiple components that make up this application. The <code>components</code> folder houses all of the components that make up the individual pages of the application. 

- The <code>App.js</code> file is the main page that serves as the entry point and root component of the application. This is where I defined the main structure and layout for my UI. 

- I used Semantics UI for React to style all of the buttons and the navbar. I also created a wireframe to help me visualize how I wanted the application to look. 

<br>
<p align="center" >
<img src="jediverse_visuals/jediverse-wireframe.png" alt="wireframe"/>
</p>


## :computer: Action 

<li> I built the JediVerse by using React and linking the Star Wars API better known as SWAPI to my React application. I followed the documentation listed on the API website and followed the examples on to reach each endpoint. Once I linked the API to my React project, I was then able to build the components needed to bring the application to life.</li>
<br>
<p align="center" >
<img src="jediverse_visuals/swapi-data.png" alt="swapi-data"/>
</p>
<p align="center"><i>This is how the data looks when grabbed from the API directly, further down you will be able to see how I pulled specific key-values for each component.</i></p>
<br>

<li>Using a navbar component, I created a navbar using the Menu and Container components from Semantic React to set the navbar in a container and to give each endpoint link a name in the navbar as well. I used the Link component from the <code>react-router-dom</code> to add the endpoints for each component. On the UI, when the user clicks on each tab it will take them to the linked endpoint. </li>
<br>
<p align="center" >
<img src="jediverse_visuals/jv-navbar-ui.png" alt="jv-navbar-ui"/>
</p>
<br>
<p align="center" >
<img src="jediverse_visuals/jv-navbar-code.png" alt="jv-navbar code"/>
</p>

<br>

<li>In the <code>App.js</code> file, I established all of the state variables needed to fetch data from each of the endpoints. I created fetch calls for each endpoint. Each component is linked to the endpoint of the same name, so for example, the people endpoint is linked to the <code>People</code> component. The data from each endpoint is then passed as a prop to each component, under the name of <code>data</code>. Each instance of <code>data</code> holds the value of the different state variables that  were created for each component.</li>
<br>
<p align="center" >
<img src="jediverse_visuals/jv-fetch-planets.png" alt="jv-fetch-planets"/>
</p>
<br>
<p align="center"><i>In the function <code>fetchPlanets</code>, the variable <code>data</code> is set to be the response received when making the call to the API. Once the response is received, the state <code>setPlanets</code> changes to the value of <code>data.results</code>. The state is then updated and the results are fetched and rendered on the page.</i></p>

<p align="center" >
<img src="jediverse_visuals/jv-planets-rendered.png" alt="jv-planets-rendered"/>
</p>
<p align="center"><i>Once the state has been updated and the results have been fetched, the data is rendered on the page, as shown in the photo above.</i></p>

<li> Each state variable manages the state for each individual component. For example, the state variables <code>[people, setPeople]</code>, is used to store and manage the state for the <code>People</code> component. I used the same method for each component </li>
<br>
<p align="center" >
<img src="jediverse_visuals/jv-app.png" alt="jv-app"/>
</p>
<br>


<li> Each endpoint, contains between 30-80 objects, each displaying about 10 objects per page. In order to show the data for each page I used pagination to design a dynamic UI that allows the user to flip through each page by simply pressing "Next". Should the user want to go back to the previous page they can just click the "Previous" button. </li>

<br>
<p align="center" >
<img src="jediverse_visuals/jv-page-buttons.png" alt="jv-page-buttons">
</p>
<br>
<p align="center"><i>The circled area in the photo above, shows how the "Next" and "Previous" buttons look on the UI. </i></p>

<li>Upon initially fetching the data, the page is always set to 1. I also created the event handlers (<code>handleNextPage</code> & <code>handlePreviousPage</code>) needed to move through each page of data for each endpoint. The event handlers were then passed as props to all of the components. <code>next</code> and <code>previous</code>.
</li>

<br>
<p align="center" >
<img src="jediverse_visuals/jv-pagination.png" alt="jv-pagination"/>
</p>
<p align="center"><i>This is pagination. You can see that as you hit "Next" the page number increases by 1 taking you to the next page of data, then when you hit "Previous" the page number is reduced by 1, thus taking you to the previous page. In the <code>useEffect</code> function, the <code>page</code> prop is passed so that the page can be fetched and rerendered.</i></p>
<br>

<li> I followed the same data structure for each of the components, pulling only specific key values that I wanted to be visible to the user. I used the map function to map through each object so that they could easily be displayed in an array.</li>
<br>
<p align="center" >
<img src="jediverse_visuals/jv-people.png" alt="jv-people"/>
</p>

<p align="center"><i> As shown in the photo above, for the People component, on line 20, I styled each piece of data that was I mapping in a grid so that I could display the data in a way that was readable to the user. Each card has a header, a title, and a description, which includes the individual attributes that are present for the People component.</i></p>

<li>In order to display the information that is shown on each page, for each component I created the variables <code>totalPages</code> and <code>isLastPage</code>. Each data component follows this structure, the Navbar and Home components were built differently.</li>
<br>
<p align="center" >
<img src="jediverse_visuals/jv-page.png" alt="jv-page"/>
</p>
<br>

<li> For the look and feel of the UI, I used Semantics UI and Semantics CSS, to style the buttons as well as give the color scheme to the Navbar. I used CSS to add a background image and also used a cursor website that allowed me to set the cursor as R2-D2. I created a CSS file, <code>App.css</code> in order to add some styling to the UI.</li> 

<br>
<p align="center" >
<img src="jediverse_visuals/jv-app-css.png" alt="jv-app-css"/>
</p>
<br>

<li>Last but not least, I made my homepage very interactive. On the homepage, I added the movie poster for each Star Wars movie. In order to have each poster show up one after the other, I created and array called <code>posters</code>, that held 9 different objects with the key-value pairs of <code>image</code> and <code>video</code>. The key of <code>image</code> holds the link to movie poster as a value and the key <code>video</code> holds the link to the external video source as a value.</li>
<br>
<p align="center" >
<img src="jediverse_visuals/jv-home.png" alt="jv-home"/>
</p>
<p align="center"><i>Here you can see the <code>posters</code> array, an array of objects, which holds the keys <code>image</code> and <code>video</code> and their values.</i></p>
<br>
<p align="center" >
<img src="jediverse_visuals/jv-home-page.jpg" alt="jv-home-page"/>
</p>
<p align="center"><i>Here you can see how the movie posters and home page were designed. At the top, I included a gif and provided a brief description of what the user can see within my application. The navbar can be seen at the very top portion of the page and clearly maps out each tab to each API endpoint.</i></p>
<br>

<li> Next, I was given the task of making the posters clickable so that when the user hovers over the poster a message pops up that says "Click me!" and then takes the user to an external link. In order to complete this, I create two pieces of state <code>hoveredIndex</code> and <code>setHoveredIndex</code> this piece of state changes each time a user hovers over an image.</li>
<br>
<p align="center" >
<img src="jediverse_visuals/jv-home-state.png" alt="jv-home-state"/>
</p>

<p align="center"><i>Above, you can see the state used to track whether or not a user has hovered their cursor over one of the movie poster images</i></p>
<br>

<li>I used the map function to go through each index of the <code>posters</code> array and displayed each one in a grid column in the form of a card. Once this was established, I used the event handler, onMouse, and created logic that would display the "Click me!" message each time the cursor was over the poster image. I also created logic that when the user navigated over to the poster image and clicked on it, it would then take them to an external link, this link being the <code>poster.video</code> attribute. </li>

<br>
<p align="center" >
<img src="jediverse_visuals/jv-home-map-logic.png" alt="jv-home-map-logic"/>
</p>

<p align="center">There you have it! This is the <b><i>JediVerse</b></i>!

## :movie_camera: Result (Video Presentation + Project Repo) 

- [JediVerse Repository](https://github.com/jedi-verse-MV/jediverse-MV/tree/main)
- [JediVerse Project Board](https://github.com/orgs/jedi-verse-MV/projects/1)

<p align="center"><i>Click the thumbnail below to be redirected to the video!</i></p>

[![Watch the video](https://i.imgur.com/cHE8DU8.jpg)](https://www.youtube.com/watch?v=xO90thlEhC8)


## :floppy_disk: Technologies

Front End 
<ul>
<li>React</li>
<li>React Router</li>
<li>Semantics UI React</li>
<li>Semantics UI CSS</li>
</ul>

API 
 
- [Star Wars API](https://swapi.dev/)

## :book: Competencies


### JF 1.6

#### Can follow software designs and functional/technical specifications

With this project, I was able to design my own software and work out what technologies I wanted to use. Doing so allowed me to explore new frameworks and expanded my understanding of React and how CSS frameworks can vary. I held myself accountable by keeping track of my tasks using a GitHub project board. I utilized the project board to help me lay out each task and project tier so that I could effectively keep track of what tasks I had already completed. This allowed me to really visualize how I wanted my application to look.

<br>
<p align="center" >
<img src="Project Visuals/jediverse_app/jv-project-board.png" alt="home-page"/>
</p>

### JF 2.3

#### Can develop effective user interfaces

This project was a huge challenge for me. I have never built a React application from scratch before. I have also never really used an external API to build out an application. I researched different ways to make an effective React application and tried to place myself in the position of a user. In doing so, I was able to effectively create a very cool and interactive user interface. I used a navbar so that a user can easily navigate to the different endpoints and made the home page interactive so that users would want to come back and engage further with my application. I used various functions to create each component with custom logic in order to get the UI that I wanted. 


### JF 2.4

#### Can create simple software designs to effectively communicate understanding of the program

I primarily focused on making this application extremely user-friendly. I chose very simple styling so that as a user the application would be easy to navigate through. In my presentation I utilized developer tools in Google Chrome, to show how my application communicated with the API that I was using. Doing so allowed me to articulate the functionality within my application. 

### JF 2.6

#### Can translate wireframes into User Interfaces

I used a wireframe for this project to lay out how I want my front end to interact with the API. Using a wireframe allowed me to really think about what I wanted from this application and how I wanted it to look. I was able to break down and visualize how I wanted users to interact with my application. While my application is simplistic in its design, using a wireframe for the planning portion of the project was very useful. 


### JF 3.4 

#### Can create a logical and maintainable codebase

In taking on this project alone, it allowed me to practice more version control. When pushing up code to my repository, I tried to make each commit very detailed so that way if another engineer wanted to read through my commits they would be able to understand what was done in each commit. I would push up multiple commits a day as I was constantly updating and adding to my codebase as well. 


<br>
<p align="center" >
<img src="Project Visuals/jediverse_app/jv-version-control.png" alt="home-page"/>
</p>


### JF 5.5

#### Understands and can apply structured techniques to problem-solving, can debug code, and can understand the structure of programs to identify and resolve issues

When creating this application, there were a lot of obstacles that I faced, specifically when it came to debugging. In order to make sure that I was getting the desired information from each endpoint, I used console logs to verify that the data was in fact being retrieved in the browser. I also used Google Chrome developer tools, specifically Network to see how long it took for calls to be made to the API and whether or not those calls were successful. I reviewed different documentation in regard to React so that I could understand how to construct my components better as well. 

### JF 6.1

#### Knows how best to communicate using different communication methods and how to adapt appropriately to different audiences

For my presentation, prior to recording the presentation, rather, I took the time to think about how best to convey the information needed to get into the inner workings of my project. I took the time to break down complex explanations to something that a user can understand. I even used visual demonstrations, such as showing how I used developer tools to debug my work and see how long to it takes to get a response from the API. 
