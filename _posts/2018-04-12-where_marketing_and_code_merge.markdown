---
layout: post
title:      "Where Marketing and Code Merge"
date:       2018-04-12 06:24:57 +0000
permalink:  where_marketing_and_code_merge
---


For my final project, for the Flatiron School, I decided to develop a tool that I would have liked to use at my former job. The concept came from a consitent need at my previous workplace to come up with  'never-been-done' before ideas for a great variaty of clients. Getting a group of smart, creative people in one room to ideate and brainstorm has always brought it's disadvatnages, primarely, the precious time that has been spent on yet another meeting.

Introducing 'Pitch or Ditch'.

This is a brainstorming tool designed to be used by teams who are faced with ideation challenges. As an example, this tool can be used by sponsorship marketing groups that have a need to develop new integrated media campaigns. Pitch or Ditch allows team members to submit their ideas based on pre-determined categories. Each team member has access to the Idea List and can vote on his/her favorite...so to determine whether an idea should be pitched, or ditched. The goal of this tool is to allow for remote collaborative brainstorming and filtering of the best ideas, all-the-while saving precious time.

Now a little on how it is built.

Pitch or Ditch is built utilizing a Rails API backend with a PostgreSQL database and a React frontend that uses a Redux store and React-Bootstrap for styling. 

Backend.
The backend includes some seed data that needs to be populated upon creating and migrating the database. Aditionally, the backend incorporates nested routes for categories/:id/ideas that serves up the ideas in a descending order of votes in the index action. One of the reasons I chose to creat nested routes in addition to namespacing is to have access to more end-points that I can use on the frontend to fetch nessesary data.   

Frontend.
My main container components on the frontend are the IdeasPage and IdeaForm. These are the components that are connected to my Redux store and know about the app's state. Both components have multiple children that have access to the ideas data that is fetched from the backend, however, these are strictly presentational and are not connected to the Redux store. The app takes advantage of the React router and displays the SPA with access to a navigation bar that is available via the NavBar component. The frontend is stylized with react-bootstrap, which is rather easy to navigate. The only requirement is to import visual elements from the react-bootstrap library and include a reference to the CSS stylesheet in the html.

Next Steps.
There are many additinional features that I would like to add to this app. The main one would be to create user accounts, specifically team accounts and create a leaderboard to incentivize members to submit more ideas. I would also like to include some type of countdown to indicate an ideation-timeline.


