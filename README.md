# Airport Performance Analysis - Power BI Dashboard
![download](https://github.com/user-attachments/assets/72b2a7ed-eee4-426f-8c39-7b46eddb844f)

## 1. Problem Overview
Flight delays, cancellations, and diversions are major concerns in the airline industry, affecting customer satisfaction, operational efficiency, and revenue. This Power BI dashboard analyzes airport performance based on flight data to identify key trends and problem areas.
<hr>

## 2. Project Overview
This project involves importing, transforming, modeling, and visualizing flight performance data using Power BI. The dashboard consists of multiple pages focusing on various aspects of flight operations, including delays, cancellations, and airline performance metrics.
<hr>


## 3. Database Description
![Screenshot (131)](https://github.com/user-attachments/assets/c6c35124-4997-42eb-9955-a4033bfee759)

The dataset includes information on:
- **Flight schedules which includes** :
  
    **ID** –Id of the flight.

    **Year** – The year in which the flight took place.

    **Month** – The month of the flight (1 = January, 12 = December).

    **DayofMonth** – The day of the month when the flight occurred.

    **DayOfWeek** – The day of the week (1 = Monday, 7 = Sunday).

   **DepTime** – The actual departure time of the flight (in HHMM format, e.g., 1530 means 3:30 PM).

    **CRSDepTime** – The scheduled departure time according to the Computerized Reservation System (CRS), also in HHMM format.

    **ArrTime** – The actual arrival time of the flight (in HHMM format).

    **CRSArrTime** – The scheduled arrival time according to CRS.

   **UniqueCarrier** – The airline code or identifier for the carrier operating the flight.

    **FlightNum** – The flight number assigned by the airline.

    **TailNum** – The aircraft’s tail number (a unique identifier for the plane).

    **ActualElapsedTime** – The total actual time (in minutes) from departure to arrival.

    **CRSElapsedTime** – The scheduled elapsed time (in minutes) from departure to arrival.

    **AirTime** – The actual time (in minutes) the aircraft spent in the air.

    **ArrDelay** – The difference (in minutes) between the actual and scheduled arrival times (positive values indicate a delay).

    **DepDelay** – The difference (in minutes) between the actual and scheduled departure times (positive values indicate a delay).

    **Origin** – The origin airport code (e.g., LAX for Los Angeles International Airport).

    **Dest** – The destination airport code.

    **Distance** – The flight distance between the origin and destination (in miles).

    **TaxiIn** – The time (in minutes) the aircraft spent taxiing after landing.

    **TaxiOut** – The time (in minutes) the aircraft spent taxiing before takeoff.

    **Cancelled** – Indicates whether the flight was canceled (1 = Yes, 0 = No).

    **CancellationCode** – The reason for flight cancellation:

    "A" = Carrier (airline) cancellation
    "B" = Weather-related cancellation
    "C" = National Air System (NAS) delay
    "D" = Security-related cancellation
    Diverted – Indicates whether the flight was diverted (1 = Yes, 0 = No).

    **CarrierDelay** – The delay (in minutes) due to the airline (e.g., maintenance, crew issues).

    **WeatherDelay** – The delay (in minutes) due to weather conditions.

    **NASDelay** – The delay (in minutes) caused by National Airspace System (e.g., air traffic control, capacity constraints).

    **SecurityDelay** – The delay (in minutes) due to security-related issues.

    **LateAircraftDelay** – The delay (in minutes) caused by a previous flight arriving late and affecting the aircraft’s schedule.
<hr>


## 4. Tools and Technologies Used
- **Power BI**: For data visualization and reporting
- **DAX (Data Analysis Expressions)**: For creating calculated measures
- **Power Query**: For data transformation and cleansing
<hr>


## 5. Data Model
![Screenshot (132)](https://github.com/user-attachments/assets/483381fe-fc08-4a8f-b633-a7190bc97bff)

The data model consists of:
- **Fact Tables**:
  - FlightDetails (contains flight data, delays, and cancellations)
- **Dimension Tables**:
  - Airlines (airline details)
    ![Screenshot (135)](https://github.com/user-attachments/assets/b1043526-79d6-4ee5-846e-5db75ce391a2)

  - Airports (airport information)
    ![Screenshot (133)](https://github.com/user-attachments/assets/4f1d05ce-1037-429b-949e-56d538a1ddc7)
  - Time dimension
    ![Screenshot (137)](https://github.com/user-attachments/assets/1dc2db36-5dcf-4208-80ff-0271914293bc)

  - Date dimention
![Screenshot (136)](https://github.com/user-attachments/assets/8abf1cd1-e4c2-4b98-bfd8-d20c4c42c5ab)

    
  - Cancellation dimension
    ![Screenshot (134)](https://github.com/user-attachments/assets/a83e945e-cc39-4cf9-a129-961f573103a7)


Relationships are established between fact and dimension tables to enable cross-analysis.
<hr>


## 6. Analysis Process/Methodology
1. **Data Preparation & Cleaning**
   - Importing the dataset into Power BI
   - Removing duplicates and handling missing values by replacing it with zeros in delay reasons columns and adding extra column called UnknownReasonDelay 
   - Creating relationships between tables
    ![Screenshot (138)](https://github.com/user-attachments/assets/6b276064-92e7-4b32-87bf-f7b1d6d96dc8)

     
2. **Data Modeling**
   - Developing calculated columns and measures using DAX
   - Creating hierarchies and groupings
3. **Visualization Development**
   - Building interactive dashboards with charts, tables, and KPIs
   - Implementing drill-through features for deeper insights
<hr>


## 7. Key Visualizations & Insights
### **Page 1: Overview**
![Screenshot (116)](https://github.com/user-attachments/assets/4aaea0d7-09c6-4b53-9759-387b1a68f8fe)

- **Cards**:
  - Number of Flights
  - Total Distance
  - Number of Airplanes
  - Number of States
  - Number of Airlines
  - Ratio of Late Flights
- **Line Chart**: Number of flights per month (shows seasonal patterns)
- **Bar Chart**: Flights per day of the week (indicates operational consistency)
- **Insights**:<br>
 - **High Total Flights, Distance, and Planes**: The raw numbers (193,675 flights, 1,482,565,872 total distance, 5,367 airplanes) highlight the massive scale of the airline's operations.<br>
 - **High Ratio of Late Flights**: 88.98% late flights is a major cause for concern. This requires immediate investigation and action to improve on-time performance.<br>
 - **Relatively Consistent Flight Distribution**: The bar chart shows a fairly even distribution of flights across the days of the week. This suggests a consistent operational schedule across all days.<br>
 - **Declining Flight Numbers**: The most prominent insight is the consistent decline in the number of flights from June through November. This suggests a potential seasonal pattern with lower demand for    flights in the later months. Alternatively, it could point to other factors like economic downturn, This would make sense with the 2008 global financial crisis

### **Page 2: Airlines**
![Screenshot (115)](https://github.com/user-attachments/assets/c55ac10a-f374-4072-98d0-ad68be65bd1d)

- **Cards**:
  - Number of Early Flights
  - Number of On-Time Flights
  - Number of Late Flights
- **Bar Charts**:
  - Flights by carrier name (compares airline market share)
  - Diverted and canceled flights per carrier
  - Average arrival and departure delays per carrier
- **Insights**:<br>
 - **178K (Number of Early Flights)**: A substantial number of flights departing ahead of schedule. While seemingly positive, this can cause issues with connecting flights and potentially indicate operational inefficiencies.<br>
- **1,723,415 (Number of Late Flights)**: This is a huge red flag. The sheer volume of late flights points to systemic problems. This will negatively impact customer satisfaction, increase costs (compensation, rebooking), and damage the airline's reputation<br>
- **27,040 (Number of On-Time Flights)**: While a significant number in itself, it pales in comparison to the number of late flights. This reinforces the urgency to address the delay issue.
Southwest Airlines Leads: Southwest has the highest number of flights. This isn't surprising given their large operational scale.<br>
- **Distribution Across Carriers**: The chart allows for easy comparison of flight volume across different airlines. This helps understand market share and relative size.
Southwest Again Stands Out: Southwest also has the highest number of diverted and cancelled flights, likely due to their high flight volume.<br>


### **Page 3: Airline Drill-Through**
![Screenshot (139)](https://github.com/user-attachments/assets/c17256c1-9549-4e11-87ab-08b021a09962)

- **Cards**:
  - Number of Flights
  - Number of Airplanes
  - Average Flight Duration
- **Line Chart**: Arrival and departure delay trends by month
- **Bar Chart**: Average arrival delay per aircraft

### **Page 4: Delay Reasons**
![Screenshot (118)](https://github.com/user-attachments/assets/f29611cc-2f38-4194-967b-3b6932fcd674)

- **Cards**:
  - Average Carrier Delay
  - Average Late Aircraft Delay
  - Average NAS Delay
  - Average Security Delay
  - Average Unknown Reason Delay
  - Average Weather Delay
- **Table**: Number of delayed flights per reason, broken down by airport, region, and carrier
- **Donut Chart**: Ratio of each delay reason
- **Insights**:<br>
 - **Number of Flights and AvgActual ElapsedTime by airport**: By comparing bar heights (number of flights) and the line position (average elapsed time), you can identify airports with a high volume of flights and longer flight times. This could indicate potential bottlenecks or airspace congestion at those airports.<br>
 - **AvgTaxiIn and AvgTaxiOut by airport**:Long taxi times can contribute to delays and fuel inefficiency.
  Identifying airports with high taxi times can lead to investigations into runway congestion, gate availability, or ground traffic management issues.<br>
### **Page 5-7: Airline-Tooltips**
![Screenshot (122)](https://github.com/user-attachments/assets/4b79d342-6185-4c3b-8096-28b16f45a303)
![Screenshot (124)](https://github.com/user-attachments/assets/c8bcdc45-e460-440a-96f3-04a8a2357ca6)
![Screenshot (123)](https://github.com/user-attachments/assets/0797d9a5-97be-4fbf-acb5-b32c66418aa1)

- **Bar Charts**:
  - Early flights ratio per airline
  - On-time flights ratio per airline
  - Late flights ratio per airline


### **Page 8: Airports**
![Screenshot (117)](https://github.com/user-attachments/assets/5ec08adb-0ff3-4d30-a1fb-cdc77b16b702)

- **Cards**:
  - Number of Early Flights
  - Number of Late Flights
  - Number of On-Time Flights
- **Line & Stacked Column Chart**: Number of flights and average elapsed time by airport
- **Column Charts**:
  - Average taxi-in and taxi-out times per airport
  - Average arrival and departure delays per airport
- **Insights**:
  - Identifies airports with the highest delays and congestion issues
  - Long taxi times suggest inefficiencies in ground operations

### **Page 9: Airport Drill-Through**
![Screenshot (126)](https://github.com/user-attachments/assets/fbcf3660-fd2d-42d2-8907-128fd8dffd6a)

- **Cards**:
  - Airport Name
  - Region Name
  - Number of Flights
  - IATA Code
- **Charts**:
  - Flights and departure delay trends by month
  - Arrival and departure delays by month
  - Flights by hour


### **Page 10-12: Airport Performance Tooltips**
![Screenshot (119)](https://github.com/user-attachments/assets/0c576134-7c98-4d1e-a945-d1efec2d5653)
![Screenshot (121)](https://github.com/user-attachments/assets/80215b41-81d9-4630-abc4-77f035078d05)
![Screenshot (120)](https://github.com/user-attachments/assets/f303c7d1-5cdf-4f57-afcb-dcf06da34d8b)

- **Bar Charts**:
  - Early flights per airport
  - On-time flights per airport
  - Late flights per airport
- **Table**: Number of canceled and diverted flights per airport


### **Page 14: Delay Overview**
![Screenshot (128)](https://github.com/user-attachments/assets/37cacd00-9f34-4932-ae8c-5620080c9723)

- **Cards**:
  - Average Arrival Delay
  - Average Departure Delay
  - Delay breakdown by reason
- **Charts**:
  - Monthly change in average arrival delay
  - Contribution of different delay reasons (pie and column charts)
- **Insights**:<br>
 **AvgArrDelay (Average Arrival Delay)**: 42.20: This is a significant average delay, suggesting systemic issues affecting incoming flights.<br>
**AvgDeptDelay (Average Departure Delay)**: 43.09: Similar to arrival delays, this indicates problems causing departures to be late.<br>
**AvgCarrierDelay (Average Carrier Delay)**: 12.41: This isolates delays specifically caused by the airline, such as maintenance, crew scheduling, or baggage handling.  <br>
**AvgLateAircraftDelay (Average Late Aircraft Delay)**: 16.36: This refers to delays caused by the late arrival of the incoming aircraft for a particular flight.<br>
**AvgSecurityDelay (Average Security Delay**): 0.06: This is a very low average delay, indicating security is generally efficient.<br>
**AvgUnknownReasonDelay (Average Unknown Reason Delay)**: 1.89: While relatively low, understanding the causes behind these unknown delays could lead to further improvements.<br>
**AvgWeatherDelay (Average Weather Delay)**: 2.40: This indicates the impact of weather on delays.<br>
**AvgNASDelay (Average NAS Delay - likely National Airspace System)**: 9.72: This points to delays within the airspace system, potentially due to air traffic control, congestion, or other factors.<br>
**Reasons for Delays (Bar Chart)**: The chart enables identification of the largest contributors to delays. This is crucial for targeted intervention and improvement efforts.<br>
**AvgArrDelay MoM% by Month Name (Line Chart)**: The trendline helps visualize the evolution of arrival delays over time. Seasonal patterns or the impact of specific events can be observed. Spikes or increases warrant further investigation into the underlying causes.<br>
**Pie Chart**: This visualization reinforces the information in the bar chart but in a different format. The size of each slice represents the proportion of each delay reason.<br>
### **Page 15: Cancellations**
![Screenshot (129)](https://github.com/user-attachments/assets/a3c0558d-1559-4024-a8e1-74c7d34d607a)

- **Pie Chart**: Cancellations categorized by reason
- **Stacked Column Chart**: Cancellations by region
- **Bar Chart**: Cancellations by airport
- **Insights**:<br>
 **Number of Cancelled Flights by Description (Pie Chart)**: The pie chart reveals the dominant reasons for cancellations. This is crucial for targeted interventions and mitigation strategies. For instance, if "Carrier" related issues are dominant, the airline needs to address internal operational challenges. If "Weather" is a significant slice, improved forecasting and passenger communication strategies are essential.<br>
**Number of Cancelled Flights by Airport (Horizontal Bar Chart)**: Identifying airports with a high number of cancellations is vital for resource allocation and operational adjustments. Factors like hub size, weather patterns, and local airport challenges can influence these numbers. Airports with frequent cancellations require further investigation to understand underlying causes.<hr>
**Number of Cancelled Flights by Region (Vertical Bar Chart)**: Regional analysis helps identify geographic areas with higher cancellation rates. This can be related to weather patterns, airspace congestion, or regional events.<br>
<hr>
<hr>


