# Search service

## Description
The goal of this service is to behave like a search engine for services. <br>
It should accept user inputs and return results that matched the provided service name.<br>
How well the result has to match the input is left to the implementor to decide.

For this exercise the service can communicate over http requests or the standard input/output.

### General info
Our goal with this exercise is to see how you approach writing code. <br>
The specific implementations of scoring/filtering data is not the most important part. <br>
Using 3rd party libraries and packages are okay, but make sure we can see who you are as a coder. <br>
Try to not spend more than 2 hours on the exercise.

### Data
Data can be read from the file "data.json" (located in root in this repository)

Example data:
```
[
    {
        "id": 1,
        "name": "Massage",
        "position": {
            "lat": 59.3166428,
            "lng": 18.0561182999999
        }
    },
    {
        "id": 2,
        "name": "Salongens massage",
        "position": {
            "lat": 59.3320299,
            "lng": 18.023149800000056
        }
    }
]
```

### Input
The service should have the following input paramters
* Service name
* Geolocation


### Output
The output should be in JSON.

It should have the following properties:
* TotalHits
* TotalDocuments
* Results

Where Results should be an array of objects with properties
* Id
* Name
* Position
* Score
* Distance

The Results should be list of services that matched the service name that was inputted. <br>
The Score should be how well the service name matched according to a metric of your choice. <br>
The Distance should be how far away the result item is from the provided location.

Example output:
```
{
    "totalHits": 2,
    "totalDocuments": 10,
    "results": [
        {
            "id": 9,
            "name": "Massage",
            "position": {
                "lat": 59.40411099999999,
                "lng": 18.109118499999962
            },
            "distance": "8.95km",
            "score": 0
        },
        {
            "id": 3,
            "name": "Massör",
            "position": {
                "lat": 59.315887,
                "lng": 18.081163800000013
            },
            "distance": "100m",
            "score": 3
        }
    ]
}
```
