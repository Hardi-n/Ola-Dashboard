#🚖 Ola Dashboard – Data Analysis & Visualization#
📌 Project Overview

This project is a Power BI dashboard created using 20,000 rows of Ola ride data. The analysis covers multiple aspects of Ola’s business operations such as vehicle type distribution, revenue, cancellations, and customer ratings.

The dataset was cleaned and pre-processed in Excel, and insights were validated using SQL queries to ensure accuracy. The final dashboard provides a comprehensive view of Ola’s performance metrics.

📊 Dashboard Pages

The dashboard consists of 5 main pages, each highlighting a different perspective of Ola’s operations:

Overview – High-level summary of total rides, revenue, cancellations, and average ratings.

Vehicle Type Analysis – Breakdown of trips, revenue, and usage trends across different vehicle categories (e.g., Mini, Prime, Auto, Bike).

Revenue Insights – Revenue distribution by vehicle type, region, and time period.

Cancellations – Analysis of cancellations by customers vs drivers, and impact on revenue.

Customer Ratings – Distribution of ratings, trends in customer satisfaction, and correlations with cancellations or ride type.

🛠 Tools & Technologies Used

Power BI – Dashboard development & visualization

Excel – Data cleaning & preprocessing (removal of duplicates, null handling, formatting)

SQL – Validation of key insights (aggregation queries, joins, filtering)

🔑 Key Features

Interactive slicers for filtering by date, region, and vehicle type

Dynamic KPIs for total revenue, completed rides, cancellations, and average rating

Visual storytelling with charts, graphs, and maps

Data validation using SQL queries to ensure accuracy against raw dataset

📂 Data Columns

Date

Time

Booking_ID

Booking_Status

Customer_ID

Vehicle_Type

Pickup_Location

Drop_Location

V_TAT (Vehicle Turn Around Time)

C_TAT (Customer Turn Around Time)

cancelled_Rides_by_Customer

cancelled_Rides_by_Driver

Incomplete_Rides

Incomplete_Rides_Reason

Booking_Value

Payment_Method

Ride_Distance

Driver_Ratings

Customer_Rating

🗄 SQL Analysis
🔹 Questions & Queries

Retrieve all successful bookings

SELECT * FROM bookings WHERE Booking_Status = 'Success';


Find the average ride distance for each vehicle type

SELECT Vehicle_Type, AVG(Ride_Distance) as avg_distance 
FROM bookings 
GROUP BY Vehicle_Type;


Get the total number of cancelled rides by customers

SELECT COUNT(*) 
FROM bookings 
WHERE Booking_Status = 'cancelled by Customer';


List the top 5 customers who booked the highest number of rides

SELECT Customer_ID, COUNT(Booking_ID) as total_rides 
FROM bookings 
GROUP BY Customer_ID 
ORDER BY total_rides DESC 
LIMIT 5;


Get the number of rides cancelled by drivers due to personal and car-related issues

SELECT COUNT(*) 
FROM bookings 
WHERE cancelled_Rides_by_Driver = 'Personal & Car related issue';


Find the maximum and minimum driver ratings for Prime Sedan bookings

SELECT MAX(Driver_Ratings) as max_rating, MIN(Driver_Ratings) as min_rating 
FROM bookings 
WHERE Vehicle_Type = 'Prime Sedan';


Retrieve all rides where payment was made using UPI

SELECT * FROM bookings WHERE Payment_Method = 'UPI';


Find the average customer rating per vehicle type

SELECT Vehicle_Type, AVG(Customer_Rating) as avg_customer_rating 
FROM bookings 
GROUP BY Vehicle_Type;


Calculate the total booking value of rides completed successfully

SELECT SUM(Booking_Value) as total_successful_value 
FROM bookings 
WHERE Booking_Status = 'Success';


List all incomplete rides along with the reason

SELECT Booking_ID, Incomplete_Rides_Reason 
FROM bookings 
WHERE Incomplete_Rides = 'Yes';

📊 Power BI Analysis
🔹 Questions Explored in Dashboard

Ride Volume Over Time

Booking Status Breakdown

Top 5 Vehicle Types by Ride Distance

Average Customer Ratings by Vehicle Type

Cancelled Rides – Reasons & Trends

Revenue by Payment Method

Top 5 Customers by Total Booking Value

Ride Distance Distribution Per Day

Driver Ratings Distribution

Customer vs. Driver Ratings Comparison

📈 Insights Gained

Most revenue comes from Prime Sedan and Prime SUV categories.

Customer cancellations are higher during peak hours compared to driver cancellations.

Driver cancellations due to personal/car issues affect overall ride completion rate.

UPI is the most preferred payment method, followed by credit/debit cards.https://github.com/Hardi-n/Ola-Dashboard/blob/master/dashboard.png

Prime vehicle types consistently achieve higher customer ratings.

🚀 How to Use

Download the repository.

Open ola, ola dashboard.pbit in Power BI Desktop.

Explore interactive pages with filters and slicers.

Review SQL queries inside /sql or in README.

Screenshot:https://github.com/Hardi-n/Ola-Dashboard/blob/master/dashboard.png

📌 Future Improvements

Integrate live Ola API data (if accessible).

Add predictive analytics (ride demand forecasting).

Include geographic heatmaps for deeper regional insights.

🧑‍💻 Author

SUBHAGYA CHHABRA
📧 subhagya.chhabra@gmail.com
