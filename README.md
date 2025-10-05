# Real-time Vehicle Detection & License Plate Recognition System

*Gif image please wait*

![Demo Animation](documents/images/demo_v2.gif)

> **Portfolio Showcase**: This repository contains documentation for a project I developed and led during my employment. Therefore, source code is not available. This `README` serves as a detailed showcase of the system's architecture, features, and technical implementation.

## Project Narrative & My Role

As the sole developer at my company, I was tasked with building a real-time Automatic Number Plate Recognition (ANPR) system from the ground up to serve as the core technology for a new automated security platform. I was responsible for the **entire project lifecycle**, from research and data collection to deployment and integration.

*   **Data Scarcity Problem:** Collecting, augmenting, and labeling a custom dataset for Thai license plates, as no suitable public dataset existed.
*   **AI Model Development:** Training and optimizing computer vision models for vehicle detection, brand/color classification, and license plate recognition.
*   **Full-Stack Development:** Designing and building a robust, multi-threaded backend with Django and a responsive frontend from scratch.
*   **System Architecture:** Engineering a high-performance pipeline capable of real-time processing on hardware ranging from a Raspberry Pi to production servers.
*   **Edge Deployment:** Deploying the initial application on a **Raspberry Pi 5 using Docker**, ensuring it was highly optimized for CPU-only inference.
*   **Production CI/CD & Deployment:** Establishing a **GitLab CI/CD pipeline** to automatically build and publish Docker images to the company's private registry. I also handled pre-production testing, including configuring **Nginx as a reverse proxy** for the final integration.

This project was a fantastic opportunity to take an idea from a solo concept to a key feature in a commercial product, the **[Venus Sentinel](https://bgs.co.th/venus-sentinel-%E0%B8%A3%E0%B8%B0%E0%B8%9A%E0%B8%9A%E0%B9%84%E0%B8%A1%E0%B9%89%E0%B8%81%E0%B8%B1%E0%B9%89%E0%B8%99%E0%B8%AD%E0%B8%B1%E0%B8%95%E0%B9%82%E0%B8%99%E0%B8%A1%E0%B8%B1%E0%B8%95%E0%B8%B4/)** automated barrier system.

## Key Features

The system processes live video streams to detect and analyze vehicles in real-time, providing the following capabilities:

- **Comprehensive Vehicle Analysis**: Extracts vehicle brand, color, and license plate number with over 95% accuracy on plate and province recognition.
- **Live Monitoring Dashboard**: A fully responsive web interface provides a real-time video feed, the latest detection results, and system performance stats.
- **Advanced Accuracy Enhancement**: Utilizes multi-frame processing and automatic perspective correction to ensure high reliability even with motion blur or challenging camera angles.
- **Integrated Data Labeling Workflow**: Includes a "Dataset Mode" with a built-in web UI to review, correct, and validate predictions, creating a feedback loop for continuous model improvement.

> **Supported Brands:**
> <p align="left">
> <img src="documents/car_logo/BMW.svg" alt="BMW" width="45" height="45"/>
> <img src="documents/car_logo/BYD.svg" alt="BYD" width="45" height="45"/>
> <img src="documents/car_logo/Chevrolet.svg" alt="Chevrolet" width="45" height="45"/>
> <img src="documents/car_logo/Ford.svg" alt="Ford" width="45" height="45"/>
> <img src="documents/car_logo/Haval.svg" alt="Haval" width="45" height="45"/>
> <img src="documents/car_logo/Honda.svg" alt="Honda" width="45" height="45"/>
> <img src="documents/car_logo/Hyundai.svg" alt="Hyundai" width="45" height="45"/>
> <img src="documents/car_logo/Isuzu.svg" alt="Isuzu" width="45" height="45"/>
> <img src="documents/car_logo/Lexus.svg" alt="Lexus" width="45" height="45"/>
> <img src="documents/car_logo/Mazda.svg" alt="Mazda" width="45" height="45"/>
> <img src="documents/car_logo/Mercedes Benz.svg" alt="Mercedes Benz" width="45" height="45"/>
> <img src="documents/car_logo/MG.svg" alt="MG" width="45" height="45"/>
> <img src="documents/car_logo/Mitsubishi.svg" alt="Mitsubishi" width="45" height="45"/>
> <img src="documents/car_logo/Nissan.svg" alt="Nissan" width="45" height="45"/>
> <img src="documents/car_logo/Ora.svg" alt="ORA" width="45" height="45"/>
> <img src="documents/car_logo/Subaru.svg" alt="Subaru" width="45" height="45"/>
> <img src="documents/car_logo/Suzuki.svg" alt="Suzuki" width="45" height="45"/>
> <img src="documents/car_logo/Tesla.svg" alt="Tesla" width="45" height="45"/>
> <img src="documents/car_logo/Toyota.svg" alt="Toyota" width="45" height="45"/>
> </p>

## System Architecture & Technical Deep Dive

To achieve real-time performance, the system is built on a high-performance, multi-threaded pipeline.

- **Multi-threaded Pipeline**: The backend separates video capture, AI inference, and WebSocket broadcasting into concurrent threads to prevent blocking and ensure a smooth data flow from the camera to the UI.
- **AI & Computer Vision Pipeline**: Each frame undergoes a multi-step process:
    1.  **Vehicle Detection:** Identifies vehicles using a YOLO-based model.
    2.  **License Plate Detection:** Locates the license plate within the vehicle bounding box.
    3.  **Perspective Correction:** Automatically de-skews the license plate image.
    4.  **Character Recognition (OCR):** Extracts the plate number and province.
- **Data Management**: Uses MySQL for persistent storage of detection logs and Redis for high-speed caching and real-time messaging between backend services.

## The Development Journey: From Edge to Enterprise

The project's architecture was designed to be adaptable, proving its capability across vastly different hardware environments.

-   **Phase 1: Edge Computing Prototype:** The initial version was optimized for low-power hardware, successfully deploying on a **Raspberry Pi 5**. Using the **NCNN** framework, it achieved efficient CPU-only inference at 300ms/frame on a 1080p stream.
-   **Phase 2: Commercial Integration & Scaling:** For the **Venus Sentinel** security platform, the system was scaled up. It was **containerized with Docker** for deployment on production Linux servers. The architecture was expanded to include a **headless REST API**, allowing it to serve as the core ANPR engine that communicates detection results to the main platform, triggering actions like opening gate barriers.

## Tech Stack

The system is built with a modern, full-stack architecture, leveraging specialized tools for each layer of the application.

### Backend
<p>
  <a href="https://www.python.org/" title="Python"><img src="https://api.iconify.design/logos:python.svg" alt="Python" width="50" height="50"/></a>
  <a href="https://www.djangoproject.com/" title="Django"><img src="https://api.iconify.design/skill-icons:django.svg" alt="Django" width="50" height="50"/></a>
</p>

### AI & Computer Vision
<p>
  <a href="https://pytorch.org/" title="PyTorch"><img src="https://api.iconify.design/logos:pytorch-icon.svg" alt="PyTorch" width="50" height="50"/></a>
  <a href="https://docs.ultralytics.com/" title="Ultralytics YOLO"><img src="documents/images/ultralytics.svg" alt="Ultralytics" width="50" height="50"/></a>
  <a href="https://opencv.org/" title="OpenCV"><img src="https://api.iconify.design/logos:opencv.svg" alt="OpenCV" width="50" height="50"/></a>
</p>

### Frontend
<p>
  <a href="https://www.w3schools.com/html/" title="HTML5"><img src="https://api.iconify.design/logos:html-5.svg" alt="HTML" width="50" height="50"/></a>
  <a href="https://www.w3schools.com/css/" title="CSS3"><img src="https://api.iconify.design/logos:css-3.svg" alt="CSS" width="50" height="50"/></a>
  <a href="https://www.w3schools.com/js/" title="JavaScript"><img src="https://api.iconify.design/skill-icons:javascript.svg" alt="JavaScript" width="50" height="50"/></a>
  <a href="https://getbootstrap.com/" title="Bootstrap"><img src="https://api.iconify.design/logos:bootstrap.svg" alt="Bootstrap" width="50" height="50"/></a>
</p>

### Databases & Caching
<p>
  <a href="https://www.mysql.com/" title="MySQL"><img src="https://api.iconify.design/logos:mysql.svg" alt="MySQL" width="50" height="50"/></a>
  <a href="https://www.sqlite.org/" title="SQLite"><img src="https://api.iconify.design/logos:sqlite.svg" alt="SQLite" width="50" height="50"/></a>
  <a href="https://redis.io/" title="Redis"><img src="https://api.iconify.design/skill-icons:redis-light.svg" alt="Redis" width="50" height="50"/></a>
</p>

  > **Note on Databases**: This project leverages the **Django ORM** for all database interactions (MySQL/SQLite). This approach abstracts away raw SQL queries and makes the system flexible, allowing it to work with any database backend officially supported by Django (such as PostgreSQL, MariaDB, etc.). **Redis** is used separately for high-speed caching and real-time messaging tasks.

### Deployment & Infrastructure
<p>
  <a href="https://www.docker.com/" title="Docker"><img src="https://api.iconify.design/logos:docker-icon.svg" alt="Docker" width="50" height="50"/></a>
  <a href="https://www.raspberrypi.com/" title="Raspberry Pi"><img src="https://api.iconify.design/devicon:raspberrypi.svg" alt="Raspberry Pi" width="50" height="50"/></a>
</p>

## System Visuals

I designed the user interface to be intuitive for operators, providing real-time data at a glance while ensuring full functionality across all devices.

### Responsive UI/UX Design
To ensure a seamless user experience, I built the web interface to be fully responsive. The layout automatically adapts for optimal viewing and interaction, whether on a large desktop monitor or a small mobile screen.

**Desktop & Tablet View**
On large screens, the interface uses a multi-column layout for at-a-glance monitoring, allowing operators to see the live feed, detection data, and system settings simultaneously.

![Desktop View](documents/images/LargeScreen.png)

**Mobile View**
On mobile devices, the layout intelligently collapses into a single-column, touch-friendly format, making it easy to monitor the system on the go.

![Mobile View](documents/images/SmallScreen.png)

---

### Real-Time Status Dashboard
The main navigation bar doubles as a live status dashboard. I used WebSockets to push real-time data directly to the UI, giving operators immediate insight into key system metrics:

*   Live viewer count
*   Overall system health
*   Camera connection status
*   System clock

![Live Monitoring Status Bar](documents/images/Navbar.png)

---

### AI Transparency: The Processing Pipeline
To make the AI's decision-making process clear, I created a view that visualizes the entire license plate recognition pipeline. This allows operators to see exactly how the system processes a video frame to identify a plate number, step by step.

![Processing Breakdown](documents/images/Breakdown.png)

---

### Integrated Data Management & Labeling Workflow

To solve the initial data scarcity problem and enable continuous model improvement, I built a powerful data collection workflow directly into the application, which can be activated using **Dataset Mode**.

When this mode is on, the system saves all detection results. I then designed two interfaces to turn this raw data into a high-quality dataset for retraining the AI model.

**Database View**
I created this interface to provide a complete, searchable log of all vehicle data captured by the system while in **Dataset Mode**. It allows an operator to quickly review every entry, including saved images and the AI's predictions, serving as the main hub for managing the collected data.

![Database View](documents/images/Database.png)

**Data Labeling Interface**
From the database view, any entry can be opened in the labeling interface. Here, an operator can carefully review the AI's results, correct any mistakes in the recognized text, and formally mark the data as `correct` or `wrong`. This feedback loop was my solution for creating the clean, human-verified datasets essential for improving the model's accuracy over time.

![Data Labeling](documents/images/Labeling.png)
