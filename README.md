import csv
import json
with open('airlines.csv', newline='') as csvfile:
    data = csv.DictReader(csvfile)

    col = []
    for i in data:
        col.append(i['Airport.Name'])

#getting unique airports and their repeated times in dict    
airports = {i: col.count(i) for i in col}

#converting to json format   
conv_to_json = json.dumps(airports, indent=4, sort_keys=True)

print("Output 1 :" + conv_to_json)

# value of airport mentioned highest number of times
maxtime_apper_airport_value = max(airports.values())

# key of airport mentioned highest number of times
for key, value in airports.items():
    if maxtime_apper_airport_value == value:
        maxtime_apper_airport_key = key
print("Output 2 : " + maxtime_apper_airport_key, maxtime_apper_airport_value)

# value of airport mentioned lowest number of times
lowtime_apper_airport_value = min(airports.values())

# key of airport mentioned lowest number of times
for key, value in airports.items():
    if lowtime_apper_airport_value == value:
        lowtime_apper_airport_key = key
print("Output 3 : " + lowtime_apper_airport_key, lowtime_apper_airport_value)
