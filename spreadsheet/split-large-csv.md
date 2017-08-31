Given a large CSV file, e.g. the Companies House free csv, this can be split
from a bash window. Use the `split` command like so:

    split -n l/1/100 InputFile.csv > Output-1-of-100.csv
    
That will fetch a specific fragment of the file, e.g. for extracting headings. 

Or you can split by number of lines like so

    split -l 10000 InputFile.csv