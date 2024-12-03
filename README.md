# Green-Route-Architects

VoltMate
Table of Contents:
1. Overview
2. Product Spec
3. Wireframes
4. Schema

Overview
Description
VoltMate is an app designed to simplify electric vehicle (EV) charging. It allows users to locate nearby charging stations, check real-time availability and pricing, and plan optimized routes for their EV trips. VoltMate aims to make EV ownership more convenient and efficient by providing a comprehensive tool for all charging needs.

App Evaluation
1. Category: Navigation/Utility
2. Mobile: Mobile-first with potential for web support in future updates.
3. Story: VoltMate tells the story of a seamless EV charging experience, eliminating range anxiety and enhancing user convenience.
4. Market: EV owners, fleet managers, and environmentally conscious individuals.
5. Habit: Primarily occasional use, with increased frequency for frequent EV drivers or during trips.
6. Scope: Focused on EV charging needs but scalable to include additional EV-related tools (e.g., rewards programs, battery health monitoring).


Product Spec
1. User Stories (Required and Optional)
Required Must-Have Stories

User can create a new account.
User can log in.
User can view nearby charging stations on a map.
User can search for charging stations with filters (e.g., cost, speed).
User can view details of a charging station (availability, pricing, reviews).
User can plan an optimized route with charging stops.
User can save favorite charging stations.
User receives notifications for station availability or battery alerts.
Optional Nice-to-Have Stories

User can leave reviews and ratings for a charging station.
User can read reviews and tips from other users.
User can track charging history (costs, locations visited).
User can earn rewards or badges for sustainable driving.
User can view traffic data integrated into route planning.
User can share routes or station info with friends.


2. Screen Archetypes
Login Screen

User can log in.
Registration Screen

User can create a new account.
Map Screen

User can view nearby charging stations on a map.
User can search for charging stations with filters.
Station Details Screen

User can view details of a charging station (availability, pricing, reviews).
User can save a station as a favorite.
Route Planning Screen

User can input a start and end location.
User can view a route with optimized charging stops.
Profile Screen

User can view and edit account information.
User can access saved stations and route history.
User can view notifications and preferences.


3. Navigation
Tab Navigation (Tab to Screen):

Map (Main screen for station search and location).
Route Planning (Screen for trip optimization).
Profile (Screen for user settings and history).
Flow Navigation (Screen to Screen):

Login Screen
=> Map Screen
Registration Screen
=> Map Screen
Map Screen
=> Station Details Screen
=> Route Planning Screen
Station Details Screen
=> Map Screen
Route Planning Screen
=> Map Screen
Profile Screen
=> Map Screen

Wireframes
![ezgif com-animated-gif-maker](https://github.com/user-attachments/assets/d787804b-1daf-4243-badf-ded85185d9aa)



Schema
Models

User Model

Property	Type	Description
id	Integer	Unique identifier for each user
username	String	User's name or nickname
email	String	User's email address
preferences	JSON	User's saved preferences

Station Model

Property	Type	Description
id	Integer	Unique identifier for each station
name	String	Station name
location	JSON	Latitude and longitude of the station
pricing	Float	Cost per kWh
availability	Boolean	Current availability status
reviews	JSON	User-submitted reviews

Route Model

Property	Type	Description
id	Integer	Unique identifier for each route
user_id	Integer	Reference to the user
start_location	JSON	Starting latitude and longitude
end_location	JSON	Destination latitude and longitude
stops	JSON	List of charging stops along the way


Networking
List of network requests by screen:

Map Screen:

[GET] /stations - Fetch nearby charging stations.
[POST] /search - Search for stations by filters.
Station Details Screen:

[GET] /stations/{id} - Fetch details for a specific station.
[POST] /stations/{id}/reviews - Submit a review for a station.
Route Planning Screen:

[POST] /routes - Generate an optimized route with charging stops.
Profile Screen:

[GET] /users/{id} - Fetch user information and saved stations.
[PUT] /users/{id} - Update user preferences.
