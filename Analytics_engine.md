# Analytics engine - Hobbe 

## Objective
Developing an analytics engine that allow the creators of the app Hobbe solving four types of questions and  taking relaible decisions. 
  1. Design and develop the data data flow from the app to the analytics engine.
  2. Deploy the analytics engine on the web.


## Data
The data used in this project came from real time interactions of users with the app that were stored in firestore database and
from external sources that were stored on a github repository. In the case of the first one the structure of the database is as follows.

![image](https://user-images.githubusercontent.com/47225250/124957195-d1302e80-dfe6-11eb-9c4e-2faa2753e3de.png)
In the branch users it was stored the information of the users and their interactions with the app. The structure of the subbranch can be seen down below. 
![image](https://user-images.githubusercontent.com/47225250/124957667-51ef2a80-dfe7-11eb-9856-827d3c20db12.png)

## Development 
The diagram down below show the data flow. First the data is stored in firestore, then it goes to big query where it will be modified from  key base format to tabular format and 
finally the data feeds a dashboard deployed on google Data Studio
![image](https://user-images.githubusercontent.com/47225250/124957740-68958180-dfe7-11eb-812a-1ccbdfdefd3b.png)

The dashboard answers the next questions:

Type 1 - Telemetry 

When do the app have experienced the most crashes?
In which version the users have experienced the most crashes?
In which devices the users have experienced the most crashes?
In which operating systems the users have experienced the most crashes?
Which components of the app have produced the most crashes?
What is the distribution of Android OS and Apple OS versions using our application?
What is the distribution in regards to the type of request the users do?
What is the number of successful requests to the back-end services?


Type 2

Which are the activities on trending?
What is the trending category?
Which are the most economic activities?
Do we have activities attended to a certain times?
Which are the trending locations?
Which is the trending individual activity?
Which category of activities produce the most profit?
Do individual categories are attended the more than the group ones?
Which places are recommended for the users?
Which activities can I recommend based on the weather?
Which company the users prefer the most?
Which group activity is on trending now?


Type 3 

Which are the views the user interacts the most with?
Which events are more relevant in which cities?
Which content users like the most?
What is the content that the users request the most?
Which are the fluxes the user consult the most?


Type 4 

What is the distribution by gender of our users?
¿Which places produce the most profit?
In which view it will be more profitable to put advertisements?
Which are the most required hours
Which is the company that produce the most profit?
Which kind of activities generate the most profit?
Which activities produce the most profit?
Which category of activities produce the most profit?
Do individual categories produce more profit than the group ones?
Do users prefer activities in group or alone?


Type 5

Does the user tend to open the app at certain time of the day?
Which view of the app consumes the most memory?
Which type of error event consumes the most memory?
In which views the user spends the most time and therefore are more suitable to include advertisement?

## Results

The result of this project was a dashboard deployed on DataStudio 
- A PDF file  with the state of it at dic 2020 can be see in the next [link](https://drive.google.com/file/d/1dJem-gl9GDrOHRpfaHwkwaNlIUAAK4vO/view?usp=sharing). 
- Here is the link to google data studio [link](https://datastudio.google.com/u/0/reporting/dfb1841d-c2d1-4b82-af88-804cbdcaee86/page/1xZU)

