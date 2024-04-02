import requests, json
BASE_URL = "https://api.openweathermap.org/data/2.5/weather?"
CITY = "Hyderabad"
API_KEY = "Your API Key"
URL = BASE_URL + "q=" + CITY + "&appid=" + API_KEY
response = requests.get(URL)
if response.status_code == 200:
   data = response.json()
   main = data['main']
   temperature = main['temp']
   humidity = main['humidity']
   pressure = main['pressure']
   report = data['weather']
   print("----------Hyderabad-----------")
   print(f"{CITY:-^30}")
   print(f"Temperature: {temperature}")
   print(f"Humidity: {humidity}")
   print(f"Pressure: {pressure}")
   print(f"Weather Report: {report[0] ['description']}")
else:
   print("Error in the HTTP request")
