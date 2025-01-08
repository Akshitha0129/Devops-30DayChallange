# 30-Day DevOps Challenge | Day 1

## Creating a Weather Dashboard using AWS S3 buckets and OpenWeather API

Day 1: Building a weather data collection system using AWS S3 and OpenWeather API
This project is a Weather Data Collection System designed to fetch, store, and manage real-time weather data, showcasing core DevOps principles and Python development skills.

Project Overview

This project is a Weather Data Collection System that demonstrates core DevOps principles by combining:
External API Integration (OpenWeather API)
Cloud Storage (AWS S3)
Version Control (Git)
Python Development
Environment Management

Key Features
Real-Time Weather Data Collection: Fetches up-to-date weather information for multiple cities worldwide.
Detailed Weather Insights: Displays temperature (°F), humidity levels, and current weather conditions at a glance.
Cloud Storage Integration: Automatically saves weather data to AWS S3 for secure and scalable storage.
Multi-City Tracking: Monitor weather conditions across various locations simultaneously.
Historical Tracking: Timestamps every data entry for easy analysis and record-keeping.

Technical Architecture
Language: Python 3.x
Cloud Provider: AWS (S3) ️
External API: OpenWeather API
Core Dependencies:

-🛠️ boto3 — AWS SDK for Python -🔑 python-dotenv — Secure environment variable management -🌐 requests — Simplified HTTP requests for API integration

Setup Instructions
1. Clone the repository
Initially, I could have cloned the repository but I wanted to recreate and do it all myself. Create all the files that are within the Project Structure. Then insert the required information in each file
2. Create a Virtual Environment
Before you install you must create a virtual environment for Python. This won't install as the package is being handled externally. This could simply be "Apt".So make sure to isolate the environment and install it within there.
   To do this:
   To create a virtual environment 
   python3 -m venv (your virtual environment name)
   Then you have to activate the virtual environment 
   source envname/bin/activate 
3. Install dependencies
   pip install -r requirements.txt
4. Configure environment variables (.env)
   Copy OPENWEATHER_API_KEY=your_api_key
   AWS_BUCKET_NAME=your_bucket_name
5. Configure AWS credentials
 Use aws configure to connect to the CLI
6. Run the application:
   python src/weather_dashboard.py

<img width="484" alt="Screenshot 2025-01-06 at 6 51 54 PM" src="https://github.com/user-attachments/assets/a1506225-5c0e-4ec7-a2e2-3e76059ba94c" />

   
<img width="1122" alt="Screenshot 2025-01-06 at 6 38 44 PM" src="https://github.com/user-attachments/assets/9ed19972-9c27-4f6c-8ee2-3cb04bae9765" />

<img width="786" alt="Screenshot 2025-01-06 at 6 38 27 PM" src="https://github.com/user-attachments/assets/652d65a7-ff1a-4604-a969-d301fbc5c54d" />

Make sure to delete everything after using S3 to escape from additional costs.


