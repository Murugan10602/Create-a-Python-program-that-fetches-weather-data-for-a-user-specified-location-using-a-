# Create-a-Python-program-that-fetches-weather-data-for-a-user-specified-location-using-a-
import requests

def get_weather(city):
    api_key = 'YOUR_API_KEY'
    url = f'http://api.openweathermap.org/data/2.5/weather?q={city}&appid={api_key}'
    response = requests.get(url)
    data = response.json()
    weather = data['weather'][0]['description']
    temp = data['main']['temp']
    print(f"Weather in {city}: {weather}")
    print(f"Temperature: {temp}°C")

city = input("Enter a city: ")
get_weather(city)
