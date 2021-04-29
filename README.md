# Road-Incidents-Geospatial-Analysis-in-Calgary
The web app is hosted by PythonAnywhere and is available at https://micdean19.pythonanywhere.com/.

Note that due to the limitation of the free hosting tier of Python Anywhere, some of the images won't show due to being too large (i.e. traffic cameras images).
If you'd like to see those feel free to pull the repository and open the app with python/flask by running "flask run" in the directory.

## Introduction
The objective of the final project of ENGO 551: Advanced Geospatial Analysis was to apply the skills and knowledge gained over the semester to solve a geospatial problem.

My project consists of showing Road incidents in Calgary since 2016. According to Alberta Statistics, in 2018, there were 142,596 collisions with 246 of them being fatal. 
I thought it'd be interesting to model some of the different datasets and see if there's correlation between location of traffic cameras and the speed limits. 
The data was collected from open Data Calgary, the backend was made using Flask (python library) and the front end was generated using vanilla JavaScript (Leaflet, Leaflet draw and other external Libraries). 
There were 2 geospatial techniques applied using turf which are Euclidian Distance along a road and Finding Nearest neighbour (from the traffic camera cluster). 
The data was collected from Open Data Calgary.

## Technologies
Python 
HTML5/CSS3/Javascript(ES6)
Flask (Python Libgary)
Leaflet, Leaflet Draw.JS
Bootstrap 5
Turf.JS

## Layout of Website
The design of the website was made from a combination of bootstrap and some css styling. The UI itself consist of 2 pages, a landing page, and the map. The landing page contains an appealing visual to welcome the user, a navigation menu and an about me section. Furthermore, the navigation and footer are also present in the map page. 

For simplicity, the layout consists of:
1.	Welcome/Landing Page:
2.	Map page
![](/static/img/project.png)

## Backend API
The backend was developed in Python using the Library Flask.

They backend has 2 routes for the Home and Map pages, and 4 external API’s. The api simply loads in the data Open Data Calgary and returns a GeoJson object to the front end. The API can be accessed by the relative link of /api/DataofInterest. 

For example, there are currently 4 end points:
* /api/incidentdata
*	/api/cameradata
*	/api/speeddata
*	/api/speedcolor

The incident data and camera data are very simple request functions that grab data from opencalgary data using their API and sends a geojson object to the front end. This process can and should normally be used on the front side without a need for a back end.

Speed Data and Speed Color have a few processing steps. Open Calgary sends a list of polylines many with the same speed limit. The backend groups the polylines with the same speed limit and assign the same color to each speed limit. Thus, the front end is able to plot roads with the same speed limit in the same color. The endpoint speed color just returns a hex color code. 
![](/static/img/Picture2.png)

## Spatial Trajectory Processing
There were 2 spatial trajectory techniques used in this project. They are simple and are generated by Turf. They 2 functions include finding the Euclidian distance of a trajectory (displayed in the navigation bar once the user is done drawing their trajectory) and finding the nearest traffic light given any selected incidents

## Software Hierarchy 
The hierarchical structure On Github can be summarized by:
*Static contains the CSS, Javscript and images for the front end.
*Templates: Contains the html pages that is loaded into python/flask.
*Application.py is the main code for the backend.

## User Interactivity
The user can:
1.	Draw trajectory based on their preference.
2.	Calculate distance of their trajectory.
3.	Download their trajectory/route in a GeoJson Format, that is a universal format that can be loaded into most geospatial services or mapping systems. 
4.	They can investigate any regions based on their incidence, number of traffic cameras and speed limits, thus it allows the user to find what they need.
5.	By click the icon of an incident, the website will display the closest traffic camera which can be useful when finding the correlation between location of traffic incidents, the speed limits and the distance to the nearest traffic camera.

![](/static/img/Picture3.png)

## More Information
* [Project report Containing more technical description & Findings](https://uofc-my.sharepoint.com/:b:/g/personal/michael_ahkiow_ucalgary_ca/EWt1etYHy89JrnpR67Z6-aoB2-SoO0E-xMzGK7A5WREx5A?e=jplf8h)
* [Youtube Video with a complete walkthough]()


