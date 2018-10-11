title: "Arctos Notebook Review"
author: "Jesse Woo"
date: "10/11/2018"
output: html_notebook

#Overall
Overall everything seems to be okay. I was able to get all the MVZ records but I was having trouble getting the grouped table. I also suggest maybe displaying more pictures to show how exactly to use the GUI since there are so many options

#API
Also if you want to get use the API information you can do the following:

- Get one the API links at the top from the [website]("https://arctos.database.museum/api/specsrch") and add on search criteria at the end of the link like this:

- "http://arctos.database.museum/SpecimenResultsJSON.cfm?gocsv=true=CSV" + "&taxon_name=wolf"

which gives you this:

- "http://arctos.database.museum/SpecimenResultsJSON.cfm?gocsv=true=CSV&taxon_name=wolf"

The resulting link can be put into your browser to display the results in JSON format.

You can import the data in JSON format into Jupyter notebook using the following code:

>import pandas as pd
>import json
>import requests
>resp=requests.get("http://arctos.database.museum/SpecimenResultsJSON.cfm?&taxon_name=wolf")
>data = resp.json()
>data
