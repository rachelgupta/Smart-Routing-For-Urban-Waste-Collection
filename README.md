![image](https://github.com/rachelgupta/Smart-Routing-For-Urban-Waste-Collection/assets/83275253/f0483926-7e38-4a54-b5e0-e84925106edc)# Smart-Routing-For-Urban-Waste-Collection

## 1. Problem
Municipal solid waste (MSW) is considered as one of the primary factors that contribute greatly to the rising of climate change and global warming affecting sustainable development in many different ways. It is indeed necessary to investigate an efficient computerized method for the optimization of MSW collection that minimizes the environmental and other factors according to a given waste collection scenario.

These wastes are collected by the garbage trucks and the problem with garbage trucks is that they need to go on a same route everyday even though there might be a chance that the dumpbin of some area might not be full enough. This cost trucks unnecessary diesel which they would have saved if they went to the same place after maybe a week or if they know when that bin would be filled. Also, as trucks follow a same route everyday, there is a possibility that they are unable to cover all the places in a day thus the places which might actually need cleaning is not been cleaned which in turn increases global warming.

## 2. Literature Review
a. [A Literature Review on Solid Waste Management: Characteristics, Techniques, Environmental Impacts and Health Effects in Aligarh City”, Uttar Pradesh, India](https://www.researchgate.net/publication/336972243_A_Literature_Review_on_Solid_Waste_Management_Characteristics_Techniques_Environmental_Impacts_and_Health_Effects_in_Aligarh_City_Uttar_Pradesh_India)
<br>b. [Review on Solid Waste Management Practice in India: A State of Art](http://www.hpccc.gov.in/PDF/Solid_Waste/Review%20of%20SWM.pdf)
<br>c. [Evolution of Ant Colony Optimization Algorithm – A Brief Literature Review](https://arxiv.org/abs/1908.08007)

## 3. Research Gap/Solution
A research gap, as the name suggests is a question or a problem that has not been answered by any of the existing studies or research within the field. The researches tried to solve the problem of smart routing by just devising an algorithm which takes only the position of different bins as an input and finds the optimal path through them. 

This algorithm calculates the closet bin from the starting path. Once you reach that bin, it again finds the closet bin from there. This continues. The energy saved in this method is not that high but its still better than the present system. 

The method provided by us is different form the present researchers solution. Our method calculates not only the closet bin but also finds the most optimal bin from the start. The most optimal bin meaning the bin which requires to be empty out as soon as possible as it either contains wet waste or the bin is completely full. 

This is done by adding a component on each dust bin. This machine calculates the type of waste and the amount it is filled with. The entire data is then sent to server and from there the best path is calculated through ant-colony optimization algorithm technique which as the name suggests is a pheromone-based algorithm. As one ant follows other through the pheromone released by the first one, this algorithm works in the same way. Thus, this is the research gap, as the algorithm used by the present researchers is a python script-based algorithm as ant colony algorithm is a NP hard problem and is not easily solvable. Also, we have an extra component that measures the quantity and type of waste which is not proposed by them.

## 4. Data and Time Periods

### a. Data Explaination
Our system has segregated trash bins that are fitted with sensors to measure the depth of the trash (two bins, one for recyclable waste and the other for nonrecyclable waste, each with a depth sensor) and the other sensor to measure the temperature and humidity of trash. The sensors, connected to an Arduino, which sends the data to a central server. The server keeps track of the trash levels, and over a number of weeks, categorizes the bins according to the following parameters:
<br>. How quickly the bin is filled.
<br>. What are the levels of waste (both recyclable and non-recyclable)?
<br>. What is the kind of waste (domestic, industrial, etc.), assigning them different priorities.

### b. Data Used
The following parameters are used for categorization:
1. ***Amount of garbage:*** Garbage is safe to be collected when it can work for 2 more days (to account for delays or public holidays)
2. ***Type of garbage:*** Waste generated can be of many different types, which may require different treatment. For example, dry waste is safer to keep in an enclosed location when compared to wet waste, thus, wet
waste requires more frequent cleaning (regardless of the fill level).
3. ***Garbage Fill Rate:*** Just like the type of waste generated, the amount of waste generated in a day also varies widely and knowing the areas which create more trash per day can help a lot in long-term route planning and for equal division of garbage. As cities increase in size, and routes change, knowing the fill rates can help in breaking up routes.
4. ***Area population:*** As the system is aimed towards Municipalities, they already have a database of population. As populations fluctuate, that data can also be used to facilitate long term planning of waste management resources.
5. ***Traffic/Weather conditions:*** During routing, the traffic and weather conditions of the city will also be taken into account. Increased traffic may mean delays and thus, routes may need to change.

### c. Time Periods
Data from garbage bins would be collected on a daily basis. This data would be sent to the servers.
Time Periods:
<br>. **Initial data collection period:** 2-4 weeks
<br>. **Initial rollout:** 2-4 weeks
<br>. **Final rollout:** 2-4 weeks

## 5. Methodology
### a. Overview
In our proposal, garbage bins will be fitted with sensors which send the data to the central server. That server categorises the bins, determines which bins to collect and gives the data to the routing algorithm which creates the optimal route. That route is then given to the truck drivers. The figure below gives a diagrammatical representation of the complete system.

![1 1](https://github.com/rachelgupta/Smart-Routing-For-Urban-Waste-Collection/assets/83275253/51fe4fb7-ee34-421f-8323-29adbe919e92)

### b. Hardware
The hardware system was implemented using the Arduino platform, which is a low-cost, open-source microcontroller hardware platform. The components used were:
1. ***Arduino Uno Board:*** The Arduino Uno is one of the first USB-based Arduino boards. Being an open-source microcontroller and a general purpose board, the Arduino Uno is one of the most popular microcontrollers
for a vast number of applications.
2. ***Ultrasonic Sensor:*** This is a sound-based sensor which can be used to determine the level of trash in the container.
3. ***DHT11 Temperature and Humidity Sensor:*** It is a low-cost temperature and humidity sensor which will be used to determine the kind of waste in the trash can. As wet waste leads to higher temperatures and humidity in enclosed places. This can be used to determine if waste is wet or dry
4. ***Piezo Buzzer:*** Used to alert when the garbage truck is approaching or the can is full.
5. ***ESP8266-01 Wi-Fi Module:*** The ESP8266 is a very user-friendly and low-cost device to provide internet connectivity to your projects. The module can work both as an Access point and as a station. It will be used to send data to the server. The hardware system will be fitted in every garbage bin.

![1 2](https://github.com/rachelgupta/Smart-Routing-For-Urban-Waste-Collection/assets/83275253/cd1198b0-0dcd-4e33-acfb-35f0d8db76b2)

### c. Software
The Arduino was programmed using the arduino c++ programming language. The server was created using the flask library in python. The hardware units in every garbage bin send the humidity and fill level data to the server using the wifi chip. The server then stores the data in a database. The data in the database is used to categorize the bins. These categories are used to determine which bin should be collected on the next round of garbage collection. The bins to be collected are then given to the routing algorithm which generates the optimal route for the garbage trucks to follow. That route can then be used to instruct the drivers, which bin to collect.

![1 5](https://github.com/rachelgupta/Smart-Routing-For-Urban-Waste-Collection/assets/83275253/29719ab8-280f-4493-8a50-80ccde068d5d)

### d. Routing Algorithm
Salesman Problem, is *NP-hard*. This means, it cannot be completely solved efficiently. Thus, approximate solutions are used. Ant-colony optimization is currently the best solution for finding the approximate optimal solution for garbage collection. It models the problem based on the behaviour of real life ants.

## 6. Result
Upon result analysis and data analysis we are able to find that an optimal route has been charted on basis of the data points given. The waste disposal system has been highly inefficient and a cause of concern
for our cities. As our cities continue to grow in size and area the waste disposal will proportionally increase thereby having a waste disposal system driven by modern data analytics and machine learning technology is absolutely essential. Over here using the Arduino sensors what we have done is locate the data points for potential waste pickup and after that we have charted an optimal route using ant colonisation optimisation method.

![1 3](https://github.com/rachelgupta/Smart-Routing-For-Urban-Waste-Collection/assets/83275253/c0da0306-7f12-4151-9408-6c1b21e53fdc)

This optimal route charting helps in an efficient garbage retrieval where an optimal route and efficient route has been prepared by the algorithm at the end. This helps in saving time , money ,fuel and other transportation costs for the company and most importantly it will increase the efficiency of garbage retrieval by 30%.

We expect to see the following benefits from the implementation of the system.
1. **Low Cost:** As not every trash bin will be filled everyday, the daily routes of garbage collection trucks will be shortened, resulting in lower cost for the municipal corporations.
2. **Lower Environmental Impact:** Shorter routes result in lower CO2 emissions, which is better for the environment.
3. **Lower Traffic:** Although garbage collection does not usually happen during rush hours, a lower number of trucks on the road is better for congested city traffic.
4. **Efficiency:** The overall process of garbage collection and recycling becomes more streamlined and efficient.

