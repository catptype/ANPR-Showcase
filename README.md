# ANPR-Showcase

![Demo Animation](documents/images/demo.gif)

> **Note**: This repository showcases a project I led during my worktime at company.

This project began as a Django-based web application designed for **real-time Automatic Number Plate Recognition (ANPR)**. The system automates the detection and identification of vehicles. During my time at company, the system is adapted to integrate with barrier control systems for access management. Additionally, the solution was optimized for deployment on **Raspberry Pi 5**.

## Tools and Frameworks for Development
<p>
<a href="https://www.python.org/" title="Python"><img src="https://api.iconify.design/logos:python.svg" alt="Python" width="50" height="50"/></a>
<a href="https://www.w3schools.com/html/" title="HTML"><img src="https://api.iconify.design/logos:html-5.svg" alt="HTML" width="50" height="50"/></a>
<a href="https://www.w3schools.com/css/" title="CSS"><img src="https://api.iconify.design/logos:css-3.svg" alt="CSS" width="50" height="50"/></a>
<a href="https://www.w3schools.com/js/" title="JavaScript"><img src="https://api.iconify.design/skill-icons:javascript.svg" alt="JavaScript" width="50" height="50"/></a>
<a href="https://opencv.org/" title="OpenCV"><img src="https://api.iconify.design/logos:opencv.svg" alt="OpenCV" width="50" height="50"/></a>
<a href="https://www.djangoproject.com/" title="Django"><img src="https://api.iconify.design/skill-icons:django.svg" alt="Django" width="50" height="50"/></a>
<a href="https://getbootstrap.com/" title="Bootstrap"><img src="https://api.iconify.design/logos:bootstrap.svg" alt="Bootstrap" width="50" height="50"/></a>
<a href="https://www.mysql.com/" title="MySQL"><img src="https://api.iconify.design/logos:mysql.svg" alt="MySQL" width="50" height="50"/></a>
<a href="https://www.sqlite.org/" title="SQLite"><img src="https://api.iconify.design/logos:sqlite.svg" alt="SQLite" width="50" height="50"/></a>
<a href="https://redis.io/" title="Redis"><img src="https://api.iconify.design/skill-icons:redis-light.svg" alt="Redis" width="50" height="50"/></a>
<a href="https://docs.ultralytics.com/" title="Ultralytics"><img src="documents/images/ultralytics.svg" alt="Ultralytics" width="50" height="50"/></a>
</p>

## Features

### **Live Video Streaming**
Stream real-time video from RTSP-protocol IP cameras directly to the web-based live monitoring

### **Vehicle Detection and License Plate Recognition**
The backend processes video frames from the live stream to detect vehicles and extract key details, including:

- Images of **vehicle** and **license plate**
- Vehicle's **brand**, **color**, and **license plate number**

> **Supported Brands**
    <p>
    <img src="documents\car_logo\BMW.svg" alt="BMW" width="50" height="50"/>
    <img src="documents\car_logo\BYD.svg" alt="BYD" width="50" height="50"/>
    <img src="documents\car_logo\Chevrolet.svg" alt="Chevrolet" width="50" height="50"/>
    <img src="documents\car_logo\Ford.svg" alt="Ford" width="50" height="50"/>
    <img src="documents\car_logo\Haval.svg" alt="Haval" width="50" height="50"/>
    <img src="documents\car_logo\Honda.svg" alt="Honda" width="50" height="50"/>
    <img src="documents\car_logo\Hyundai.svg" alt="Hyundai" width="50" height="50"/>
    <img src="documents\car_logo\Isuzu.svg" alt="Isuzu" width="50" height="50"/>
    <img src="documents\car_logo\Lexus.svg" alt="Lexus" width="50" height="50"/>
    <img src="documents\car_logo\Mazda.svg" alt="Mazda" width="50" height="50"/>
    <img src="documents\car_logo\Mercedes Benz.svg" alt="Mercedes Benz" width="50" height="50"/>
    <img src="documents\car_logo\MG.svg" alt="MG" width="50" height="50"/>
    <img src="documents\car_logo\Mitsubishi.svg" alt="Mitsubishi" width="50" height="50"/>
    <img src="documents\car_logo\Nissan.svg" alt="Nissan" width="50" height="50"/>
    <img src="documents\car_logo\Ora.svg" alt="ORA" width="50" height="50"/>
    <img src="documents\car_logo\Subaru.svg" alt="Subaru" width="50" height="50"/>
    <img src="documents\car_logo\Suzuki.svg" alt="Suzuki" width="50" height="50"/>
    <img src="documents\car_logo\Tesla.svg" alt="Tesla" width="50" height="50"/>
    <img src="documents\car_logo\Toyota.svg" alt="Toyota" width="50" height="50"/>
    <p>

### **Enhanced Accuracy with Multiple Frame Processing**
To ensure reliability, the system processes multiple video frames during license plate recognition, cross-verifying results to achieve a higher accuracy in recognizing **license plate number**.

### **Automatic Perspective Correction**
Detected license plates are automatically preprocessed to correct perspective distortions, improving the accuracy of recognition results.

### **Region of Interest Customization and Filtering**
Users can define a region of interest to limit detection to a specific area of the video frame. The system also allows filtering out smaller detected vehicles to optimize processing resources.

### Comprehensive Data Management
All detected vehicle details are stored in a database. Users can review and label the data as **correct** or **wrong**, providing valuable feedback to improve the system's performance in future.

> **Note**: Django [officially](https://docs.djangoproject.com/en/5.1/ref/databases/) supports several databases, including **PostgreSQL**, **MariaDB**, **MySQL**, **Oracle**, and **SQLite**. For other databases, [third-party](https://docs.djangoproject.com/en/5.1/ref/databases/#third-party-notes) backends are available.

## Screenshots

### **Processing Breakdown Visualization**

This screenshot showcases the detailed breakdown of the system's processing workflow. It highlights how each vehicle and license plate is detected, recognized, and processed step by step.

![Processing Breakdown](documents/images/Breakdown.png)

### **Database View (License Plate Number Recognition)**

The database view provides a centralized interface for managing recognized license plate information.

![Database View](documents/images/Database.png)

### **Data Labeling Interface**

The data labeling interface allows users to review and label recognition results as either **correct** or **wrong**. This feedback improves the accuracy of the system over time by enhancing the underlying models.

![Data Labeling](documents/images/Labeling.png)


### **Data Dashboard**

The dashboard interface allows users to review and summarize the recognition system's accuracy after data labeling. Note that, it displays only approved data.

![Dashboard](documents/images/Dashboard.png)
