Given a UNIX timestamp in a spreadsheet, this can be converted
into a spreadsheet-friendly date using the following:

````
=A1/86400+DATEVALUE("1970-01-01")
````

So, we're dividing the timestamp by 86400 (24 hours in seconds),
then we're adding enough to bring the zero forward in time to match
the timestamp's zero - that is, 1/1/1970. 