# Flight Reservation System for Airlines ✈️

A **responsive web-based Flight Reservation System** developed for Turkish Airlines following the **MVC (Model-View-Controller)** design pattern using **Java Servlets** and **JSP (Java Server Pages)**. The application includes **role-based user authentication and authorization** configured in Tomcat and is designed with protection against **SQL Injection** and **Cross-Site Scripting (XSS)** vulnerabilities.

## Technologies Utilized

- **Frontend:** HTML, CSS, JavaScript, jQuery, Bootstrap, JSP, AJAX (for the flight search component)  
- **Backend:** Java Servlets, Java Beans/Models, Microsoft Access Database  
- **Web Services:** SOAP-based services providing seat pricing and availability  
- **Security:** SQL Injection prevention, XSS protection, and Tomcat-based role management  

## User Roles

- Airline Administrator  
- Airline Manager  
- Customer  

## System Workflow

This system supports a single airline in selling seats online through the following operational process:  

1. **Administrator** defines pricing for the three seat categories:  
   - First Class  
   - Business Class  
   - Economy Class  
2. The Admin can create or update features associated with each seat type.  
3. The Admin sets the total seat count for every flight.  
4. **Manager** reviews the newly added or modified seat details upon login.  
5. Manager must approve the updates or pricing before they become publicly available.  
6. Only **approved** seat configurations are visible to customers.  
7. **Customers** can book seats based on availability.  
8. The system automatically adjusts available seat counts after each booking and forbids further purchases when no seats remain.  
9. Customers can select flights based on:  
   - Departure and destination cities  
   - Travel dates  
   - Number of passengers  
10. After selection, a **flight itinerary** is displayed for confirmation.  
11. Once the itinerary is confirmed, users are redirected to the **payment page**, which displays the total fare. Completing the payment confirms the booking and marks the seats as sold.  
12. A confirmation email with the itinerary details is automatically sent to the customer post-booking.  

## UI Overview

#### Home Interface  
<p align="middle">
   <img src="../master/Images/main.png" width="400"/>
   <img src="../master/Images/main2.png" width="400"/>
</p>

#### Login and Reservation Screens  
<p align="middle">
   <img src="../master/Images/login.png" width="400"/>
   <img src="../master/Images/book.png" width="400"/>
</p>

#### Active Bookings and Itinerary  
<p align="middle">
   <img src="../master/Images/current.png" width="400"/>
   <img src="../master/Images/itenary.png" width="400"/>
</p>

#### Seat Configurations and Approvals  
<p align="middle">
   <img src="../master/Images/features.png" width="400"/>
   <img src="../master/Images/approve.png" width="400"/>
</p>

## Setup Instructions

1. **Install Prerequisites:**  
   - [Java SE Development Kit 8 (JDK 8)](http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)  
   - [NetBeans IDE](https://netbeans.org/downloads/) with **Apache Tomcat Server** included  

2. **Configure Tomcat Roles:**  
   - Open NetBeans → *Services > Servers > Apache Tomcat > Properties*  
   - Locate the *Catalina Base Path* → navigate to `conf/tomcat-users.xml`  
   - Insert the following block before the closing `</tomcat-users>` tag:  


```
<role rolename="Manager"/>
<role rolename="Admin"/>
<role rolename="Customer"/>

<user username="haris@admin.com" password="a" roles="Admin"/>
<user username="haris@manager.com" password="m" roles="Manager"/>
<user username="shariq@customer.com" password="c" roles="Customer"/>
```

<p align="middle">
   <img src="../master/Images/tomcat.png" width="400"/>
   <img src="../master/Images/tomcat-users-xml.png" width="400"/>
</p>

Morever, open and read the file. Only the users authenticated in this file are allowed to login and use the Booking System. Use above mentioned credentials to login through the Login Page.

3- Restart NetBeans IDE. Click on File -> Open Project and browse to the downloaded folder named "Project". There will be two projects there "Turkish Airlines" and "WSTester" (which is basically a project to test the Web Services). Select both and open them.
Both projects will be loaded. Now first run the Turkish Airlines project, then to test the web services run WSTester project. 


## Author
You can get in touch with me on my LinkedIn Profile: [![LinkedIn Link](https://img.shields.io/badge/Connect-AishwaryaSharma-blue.svg?logo=linkedin&longCache=true&style=social&label=Follow)](https://yeahmeash-portfolio.netlify.app/www.linkedin.com/in/aishwarya-sharma-799428205)

You can also follow my GitHub Profile to stay updated about my latest projects: [![GitHub Follow](https://img.shields.io/badge/Connect-yeahmeash-blue.svg?logo=Github&longCache=true&style=social&label=Follow)](https://github.com/yeahmeash)

If you liked the repo then kindly support it by giving it a star ⭐ and share in your circles so more people can benefit from the effort.

## Contributions Welcome
If you find any bugs, have suggestions, or face issues:

- Open an Issue in the Issues Tab to discuss them.
- Submit a Pull Request to propose fixes or improvements.
- Review Pull Requests from other contributors to help maintain the project's quality and progress.

This project thrives on community collaboration! Members are encouraged to take the initiative, support one another, and actively engage in all aspects of the project. Whether it’s debugging, fixing issues, or brainstorming new ideas, your contributions are what keep this project moving forward.

With modern AI tools like ChatGPT, solving challenges and contributing effectively is easier than ever. Let’s work together to make this project the best it can be! 🚀

## License
[![MIT](https://img.shields.io/cocoapods/l/AFNetworking.svg?style=style&label=License&maxAge=2592000)](../master/LICENSE)

Copyright (c) 2025-present, yeahmeash                                                        

