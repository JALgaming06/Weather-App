# Weather-App
Tells the Weather
import requests
import json

# Function to get weather data based on city name
def get_weather_data(city):
    # OpenWeatherMap API URL
    url = "http://api.openweathermap.org/data/2.5/weather?q="goldcoast"&appid=<YOUR_API_KEY>&units=metric"

    # Make a GET request to the API
    response = requests.get(url)

    # Parse the JSON response
    data = json.loads(response.text)

    # Extract relevant data
    temperature = data["main"]["temp"]
    weather_desc = data["weather"][0]["description"]
    humidity = data["main"]["humidity"]
    wind_speed = data["wind"]["speed"]

    # Print the weather information
    print("Temperature: {}°C".format(temperature))
    print("Weather Description: {}".format(weather_desc))
    print("Humidity: {}%".format(humidity))
    print("Wind Speed: {} m/s".format(wind_speed))

# Ask user for city name
city_name = input("Enter city name: ")

# Get weather data for the city
get_weather_data(city_name)
