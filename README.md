# ANPR-Showcase

![Demo Animation](documents/images/demo.gif)

**Note:** This repository showcases a project I was responsible for while working at my company.

This is a Django-based web application designed for car detection and **Automatic Number Plate Recognition (ANPR)**. It is specifically tailored for use in authorized barrier control systems.

## Tools and Frameworks for Development
<p>
<a href="https://www.python.org/"><img src="https://api.iconify.design/logos:python.svg" alt="Python" width="50" height="50"/></a>
<a href="https://www.w3schools.com/html/"><img src="https://api.iconify.design/logos:html-5.svg" alt="HTML" width="50" height="50"/></a>
<a href="https://www.w3schools.com/css/"><img src="https://api.iconify.design/logos:css-3.svg" alt="CSS" width="50" height="50"/></a>
<a href="https://www.w3schools.com/js/"><img src="https://api.iconify.design/skill-icons:javascript.svg" alt="JavaScript" width="50" height="50"/></a>
<a href="https://opencv.org/"><img src="https://api.iconify.design/logos:opencv.svg" alt="OpenCV" width="50" height="50"/></a>
<a href="https://www.djangoproject.com/"><img src="https://api.iconify.design/skill-icons:django.svg" alt="Django" width="50" height="50"/></a>
<a href="https://getbootstrap.com/"><img src="https://api.iconify.design/logos:bootstrap.svg" alt="Bootstrap" width="50" height="50"/></a>
<a href="https://www.mysql.com/"><img src="https://api.iconify.design/logos:mysql.svg" alt="MySQL" width="50" height="50"/></a>
<a href="https://www.sqlite.org/"><img src="https://api.iconify.design/logos:sqlite.svg" alt="SQLite" width="50" height="50"/></a>
<a href="https://redis.io/"><img src="https://api.iconify.design/skill-icons:redis-light.svg" alt="Redis" width="50" height="50"/></a>
<a href="https://docs.ultralytics.com/"><img src="documents/images/ultralytics.svg" alt="Ultralytics" width="50" height="50"></a>
</p>

## Features

### **Live Video Streaming**
Stream real-time video from RTSP-enabled IP cameras for live monitoring through a web browser.

### **Vehicle Detection and License Plate Recognition**
The backend processes video frames from the live stream, detecting vehicles and extracting their details. This includes: 
- `Vehicle` and `license plate` images
- `Brand`, `color`, and `license plate number` information

### **Multiple Frames Processing**
During license plate recognition, multiple video frames are processed to verify the `license plate number` accurately.

### **Automatic Perspective**
All detected license plates are preprocessed to correct perspective orientation before processing license plate number recognition.

![Perspective Correction](documents/images/perspective.png)

### **Region of Interest Customization and Filtering**
Users can set a region of interest to limit the area for detecting vehicles. Additionally, smaller detected vehicles can be filtered out to save processing resources.

### **Data Collection**
All detected vehicles are saved into a database.

> **Note:** Django [officially](https://docs.djangoproject.com/en/5.1/ref/databases/) supports the following databases: `PostgreSQL`, `MariaDB`, `MySQL`, `Oracle`, and `SQLite`. Additionally, there are [third-party](https://docs.djangoproject.com/en/5.1/ref/databases/#third-party-notes) database backends.
