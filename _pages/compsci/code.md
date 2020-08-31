---
layout: single
author_profile: true
permalink: /compsci/code
toc: true
title: Code Repo
toc_label: "Contents"
toc_icon: "fab fa-fw fa-th-list"
---

## Code Page

Here is the GitHub link to my actual code repo - [**Here**](https://github.com/71xn/IB-CompSci-Code-Log)

Currently this page is just showing samples of what my code page will look like but eventually it will have a gigantic table of contents and external links to my code on github / gitlab etc. This is more of a place to show off the code I have enjoyed to write, the rest of thje code will be in the [GitHub Repo](https://github.com/71xn/IB-CompSci-Code-Log)


### Coffee or Soda Logic Spark - Python
[GitHub Link](https://github.com/71xn/IB-CompSci-Code-Log/blob/master/python/coffee-soda-logic-spark.py)

{% highlight python linenos%}
# Finn Lestrange 2020
# Drink Suggester - Coffee or Soda


def checker(nameinput):
    if nameinput.count("e") == 2 or nameinput.count("E") == 2 or nameinput.count("e") == 1 and nameinput.count(
            "E") == 1 or nameinput.count("E") == 2:
        drink = "coffee"
        print(nameinput + "'s drink is: " + drink)
    else:
        drink = "soda"
        print(nameinput + "'s drink is: " + drink)


def anothername():
    print("Would you like to check another name?, Y or N")
    againname = input()
    if againname == 'Y' or againname == 'y' or againname == 'yes' or againname == 'Yes':
        print("What is your name?:")
        name = input()
        checker(name)
    elif againname == 'N' or againname == 'n' or againname == 'no' or againname == 'No':
        exit()
    else:
        print("Sorry please enter a Y or an N: ")
        anothername()


time = 0
i = 0

while i >= 0:
    if time == 0:
        time += 1
        print("What is your name?:")
        name = input()
        checker(name)
    else:
        anothername()
{% endhighlight %}


### Name Program - Python
[GitHub Link](https://github.com/71xn/IB-CompSci-Code-Log/blob/master/name-class-1.py)

{% highlight python linenos %}
# Finn Lestrange - 2020
# Name program

# https://www.geeksforgeeks.org/python-find-current-weather-of-any-city-using-openweathermap-api/ - This is where I got the weather API code

from datetime import date, datetime
import json
import requests
api_key = "125ae9807f4b8f5b0bacd1398d102070"
url = "http://api.openweathermap.org/data/2.5/weather?"

today = date.today()
senior = datetime(2022, 8, 21)
senior_year = senior - datetime.now()
senior_string = str(senior_year)
name = input('What is your name? ')
city = input("What city do you live in? ")

print("Hello " + name + "! Todays date is " + str(today) +". It is " + senior_string[:8] + " until you are a senior!")

### Code from https://www.geeksforgeeks.org/python-find-current-weather-of-any-city-using-openweathermap-api/
complete_url = url + "appid=" + api_key + "&q=" + city
response = requests.get(complete_url)
json_convert = response.json()

if json_convert["cod"] != "404":
    # store the value of "main"
    # key in variable y
    y = json_convert["main"]
    # store the value corresponding
    # to the "temp" key of y
    current_temperature = y["temp"]
    # store the value corresponding
    # to the "pressure" key of y
    current_pressure = y["pressure"]
    # store the value corresponding
    # to the "humidity" key of y
    current_humidiy = y["humidity"]
    # store the value of "weather"
    # key in variable z
    z = json_convert["weather"]
    # store the value corresponding
    # to the "description" key at
    weather_description = z[0]["description"]

    # print following values
    print("The weather in " + city + " city today is:")
    print(" Temperature = " + str("{:.2f}".format(round(current_temperature, 2) - 273.15)) + " degrees Celsius ")
    print(" Atmospheric pressure is " + str(current_pressure) + "hPa")
    print(" Humidity is " + str(current_humidiy) + "%")
    print(" Weather description = " + str(weather_description))
else: # If 404 not found then
    print("Sorry your city could not be found!")

## Extension still Undecided - Would quite like to incorperate anoteher API as this was my first time using an api to get data into a python program ##


{% endhighlight %}