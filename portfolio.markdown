---
layout: page
title: Portfolio
permalink: /portfolio/
---

Here is a collection of a number of projects to which I have contributed.

## Table of Contents

### [Python](#python) :snake:

- [pygsuite](#pygsuite), _2020 - present_
- [Taser PDFs](#taser-pdfs), _2019_

## Python :snake:

### [pygsuite](https://pygsuite.readthedocs.io/en/latest/)

A Python package designed to make working with the various GSuite APIs a bit more Pythonic, and far more concise. This project started as something to automate repetitive tasks at work, and has grown into a more fleshed-out framework used by many coworkers. Keep an eye out for an upcoming production release!

#### sample

Please feel encouraged to check out some of the examples on our docs site, as these are much more thorough. Here is a simple example of authorizing, creating a file, sharing it with a friend, and ultimately deleting the file before they get to see it :smile:

{% highlight python %}
from pygsuite import Clients
from pygsuite.drive import File
from pygsuite.enums import PermissionType


# authenticate
Clients.local_file_auth("credentials.json")

# create an image object
response = requests.get("https://upload.wikimedia.org/wikipedia/commons/thumb/e/e0/SNice.svg/1280px-SNice.svg.png")
bytes = BytesIO(response.content)

# create a new file from this image
image_file = File.create(
    name="Test Smiley",
    mimetype="image/png",
    media_body=bytes,
)

# file metadata can be accessed as attributes
print(image_file.id)
print(image_file.name)

# share the file with a friend
image_file.share(
    role=PermissionType.OWNER,
    user="lou@gmail.com",
)

# delete the file
image_file.delete()
{% endhighlight %}

#### learnings

This project has been an awesome opportunity to work on a client side library for a complex and robust API (thanks, Google). Most specifically, this project has had many good exercises in thinking Pythonic ways of interacting with tangible objects, such as a Google Drive _File_, and creating methods and abstractions to allow for simple, intuitive user actions; e.g. inserting data from a dataframe in a Google Sheet, uploading a File by providing a local filepath, etc. All of these methods abstract a way the lengthy JSON requests that Google expects, and make a simpler, more pleasant experience for users.

This project was my first exposure to many great concepts, including enumerations, dataclasses, API performance boosting by bundling requests, and much more. Also my first time using GitHub actions!

### [Taser PDFs](https://github.com/samgaudet/taser_pdf)

This was one of my first ever adventures into Python. Written back in the Summer of 2019, this Python utility served as a proof of concept for how data collection from an unfriendly source, PDF documents, could be automated. This application is based on a real world need by organizations such as the ACLU to scan individual documents, extract data fields, and produce an aggregated form of this data. Perhaps someday I will be reviving this sort of application in a future job someday!

#### sample

The [README](https://github.com/samgaudet/taser_pdf#readme) file contains an overview of the motivation, functionality, and a simple example of the program. The main idea is to be able to execute a simple command and iterate over a directory of PDF files:

{% highlight python %}
import scraper


myScraper = scraper.Scraper(filepath="/Users/samgaudet/Documents/GitHub/taser_pdf/test_pdfs/")

myScraper.scrape()
{% endhighlight %}

From here, the `Scraper` performs a series of operations, including getting all the PDF files, opening them, resolving various fields, and formatting them into a dataframe that can be written to a CSV file.

#### learnings

This project was one of my first that really felt like I was creating something useful, and one that I enjoyed running over and over to see the end results. While this was my first foray into object oriented programming in Python, the class itself is very functionally designed with sequential methods all being called one-by-one in a main method. Ultimately, this could just be written as one big function, but then again, what is the value in criticizing the code that ultimately taught me what I know today.

