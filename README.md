## This 'Binding to External Data with Queue.js lesson (from Code Institute Full-Stack Diploma course). Transcription from lessons, included in comments sections in the code. 


# Binding to External Data with Queue.js

1. What is it?

Queue.js

Link from lesson:
https://raw.githubusercontent.com/Code-Institute-Solutions/DataVisualisation/master/data/transactions.json

2. What does it do?

Binds to one or more datasources while deferring the rendering of visualizations until the datasources are fully imported.

3. How do you use it?

Use Queue.js when binding to one or more external datasources.

LESSON:

More often than not, rather than having your data embedded in the same file -
your HTML file - in the form of an array, you'll generally be reading your data
from an external source. It may be from an external file locally on your
project or on your desktop. Or you may be reading it live from from a database or
through an API(an application Programming Interface). In this example
we're going to look at how you bind data that lives in an external file to our
charts so the first thing we do is we create a new directory called data using
the MK der then we change directory to data and we're going to access some data
from our github account and you can do that very easy using cloud 9 using
clever little utility called wget and that will allow you to pull in files
across HTTP and download into a particular location and our case is
going to download to our data directory
and there we have the data one thing we need to make sure next is that our
dashboards don't render before the data is available there can be a lag if we're
accessing from a database or across the wire so one of the things we use is yet
another library called queue and that again was written by Mike Bostock the
creator of d3 and it allows you to defer calling a function until the data is
ready so in our case we've downloaded and added a script reference to QGIS you
from the content delivery network and then we defer we're deferring JSON
content and we refer to its location which is it's a file call transactions
dot jJSON and it lives in our data folder so basically what's happening
between lines 29 and 38 says go and get transactions JSON file in the in the
data folder and bring it back in the form of d3 that JSON
when that's finished when that's successful
call a method and in our case is called make graphs it can be whatever you call
it yourself it's whatever you refer to inside in a wait so one of two things
will happen either the data will return or will you get an error and we can deal
with the error we can put exception handling in there if the data fails to
load in some way but we'll assume that the data will download and once that's
done it will it will appear or be injected into the transactions data
parameter inside in our custom made function called make graphs whatever you
call the function in line 30 inside in our await must match our custom function
after that normal service resumes and what I mean by that is you create a new
cross filter object then you create a new dimension in our case we're using
the names and then we group and some based on that dimension we then use DC
object in in our case again we're creating a bar chart we're binding that
to a particular div in order to render that bar chart we make sure our
dimensions match our dimension for example created on line 34 we create our
chart now one thing I didn't mention up till now is in order to render the chart
you call DC render all
you
that must be called in order to render the charts let's test it and there we
have it binding external data to our charts
