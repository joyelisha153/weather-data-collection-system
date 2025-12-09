🌤️ Weather Data Collection System

A Python-based automation project that fetches real-time weather data, processes it, and securely stores the results in an AWS S3 bucket.
This project demonstrates API integration, cloud storage, environment variable usage, error handling, and clean project structure.

🚀 Features

Fetch real-time weather data for multiple cities using OpenWeather API

Extract temperature, humidity, and weather condition

Error handling for failed API requests

Automatically generate a timestamped JSON file

Upload weather data to an AWS S3 bucket

Fully environment-driven configuration (.env)

Modular and clean Python code architecture

🏗️ Architecture Diagram (GitHub-friendly)
               ```
+----------------------+
|   OpenWeather API    |
|  (Weather Provider)  |
+----------+-----------+
           |
           v
+----------------------+
|  weather_client.py   |
|  Fetch weather data  |
+----------+-----------+
           |
           v
+----------------------+
|       main.py        |
| Process + Format     |
|  Save JSON File      |
+----------+-----------+
           |
           v
+----------------------+
|     s3_client.py     |
|  Upload to AWS S3    |
+----------+-----------+
           |
           v
+----------------------+
|    AWS S3 Bucket     |
| Stores Weather Files |
+----------------------+
```

📁 Project Structure 
weather-data-collection-system/
│
├── src/
│   ├── main.py             # Main runner
│   ├── weather_client.py   # Fetch weather data from OpenWeather
│   ├── s3_client.py        # Upload data to AWS S3
│   ├── utils.py            # Helper utilities
│
├── .gitignore              # Ignore venv, .env, cache files
├── requirements.txt        # Python dependencies
└── README.md               # Documentation 

🔧 Requirements

Python 3.8+

An OpenWeather API key

AWS Account + IAM User with S3 Write Access

AWS S3 bucket

Install dependencies:

pip install -r requirements.txt

🔑 Environment Variables (.env)

Create a .env file in the project root:

OPENWEATHER_API_KEY=YOUR_API_KEY

AWS_ACCESS_KEY_ID=YOUR_AWS_KEY
AWS_SECRET_ACCESS_KEY=YOUR_SECRET_KEY
AWS_REGION=us-east-1

S3_BUCKET_NAME=your-bucket-name
CITIES=Hyderabad,Chennai,Mumbai,Bangalore


⚠️ Never upload .env to GitHub
(You already did this correctly — good job!)

▶️ Running the Project

Use the Python module runner:

python -m src.main

Example Console Output:
Fetching weather data...
Getting weather for: Hyderabad
Getting weather for: Chennai
Getting weather for: Mumbai
Getting weather for: Bangalore

Weather Results:
{'city': 'Hyderabad', 'temperature': 26.2, 'humidity': 25, 'condition': 'haze'}
...

Uploading to AWS S3...
Uploaded to S3: weather_data_20251209_052135.json


Once uploaded, you’ll see a JSON file in your AWS S3 bucket.

📦 Sample JSON Output
{
  "city": "Hyderabad",
  "timestamp": "2025-12-09T05:21:35",
  "temperature": 26.23,
  "humidity": 25,
  "condition": "haze"
}

🛡️ Error Handling

This project gracefully handles:

Invalid API keys

Network timeouts

Missing environment variables

S3 upload failures

API request errors (401, 404, 500...)

🚀 Future Improvements

Add retry logic for unstable API responses

Store data in DynamoDB for history tracking

Build a dashboard using Streamlit

Run the script on a schedule using AWS Lambda + CloudWatch

Add GitHub Actions CI workflow

Create Docker container support

👤 Author

Joy Elisha
Project: Weather Data Collection & Cloud Storage Automation
