Step 1. What This Project Does

✔ Fetches weather data for cities (Hyderabad, Chennai, Mumbai, Bangalore)
✔ Gets temperature, humidity, and weather condition
✔ Saves the data into a JSON file
✔ Uploads the JSON file to AWS S3

Step 2. Project Folder Structure

weather_project/
│
├── src/
│   ├── config.py
│   ├── weather_client.py
│   ├── s3_client.py
│   └── main.py
│
├── .env          (not uploaded to GitHub)
├── .gitignore
└── README.md

Step 3. Requirements

Install Python libraries:

pip install requests boto3 python-dotenv


Step 4. Setup .env File

Create a .env file in the project folder:

OPENWEATHER_API_KEY=3cc7b78dc455a8481f01189decc066ce

AWS_ACCESS_KEY_ID=aws acces key
AWS_SECRET_ACCESS_KEY=uBZB9/X9oa9rXbMUlb4qfJISA9toqu14b9mxf7R2
AWS_REGION=us-east-1

S3_BUCKET_NAME=weather-project-bucket-joy
CITIES=Hyderabad,Chennai,Mumbai,Bangalore

Step 5. Run the Project

Activate your virtual environment:

source venv/bin/activate


Run the main script:

python -m src.main

Step 6. Output

(venv) joyelisha@DESKTOP-LJFKFEK:~/weather_project$ nano .env
(venv) joyelisha@DESKTOP-LJFKFEK:~/weather_project$ python -m src.main
Fetching weather data...
Getting weather for: Hyderabad
Getting weather for: Chennai
Getting weather for: Mumbai
Getting weather for: Bangalore

Weather Results:
{'city': 'Hyderabad', 'timestamp': '2025-12-09T05:21:35.005932', 'temperature': 26.23, 'humidity': 25, 'condition': 'haze'}
{'city': 'Chennai', 'timestamp': '2025-12-09T05:21:35.136265', 'temperature': 27.76, 'humidity': 75, 'condition': 'mist'}
{'city': 'Mumbai', 'timestamp': '2025-12-09T05:21:35.266215', 'temperature': 29.99, 'humidity': 20, 'condition': 'smoke'}
{'city': 'Bangalore', 'timestamp': '2025-12-09T05:21:35.453544', 'temperature': 24.16, 'humidity': 60, 'condition': 'clear sky'}

Uploading to AWS S3...
Uploaded to S3: weather_data_20251209_052135.json

summary 

This project:

Takes weather data

Saves it

Uploads to S3

we can use in this project  APIs + Cloud + Python.

author - Joy elisha
