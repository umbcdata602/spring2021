
# Colab and data

There are many ways to get external data into a Colab notebook. 
Some of these methods (e.g., uploading files from a local filesystem) do not work when 
you're sharing your notebook with others.
With shared notebooks, the easiest methods involve publicly accessible URLs that link to shared data files.

## Loading publicly accessible data

You can load publicly accessible data files into Colab using various techniques. 
One approach we used in class involves the `curl` command, which is available in Colab notebooks.
For example, the first line of the following sequence will load a compressed file
from Raschka's publicly accessible github respository into any notebook.
The `gunzip` command uncompresses the file in the notebook.
And the `ls` command lists the uncompressed filenames so that you can access them from Python in your notebook.

    ! curl -Lo movie_data.csv.gz https://github.com/rasbt/python-machine-learning-book-3rd-edition/blob/master/ch08/movie_data.csv.gz?raw=true
    ! gunzip -f movie_data.csv.gz
    ! ls /content

The critical element is the URL that points to the "raw" data file. 
Github repositories have a "Raw" button that provides that URL for individual files.

## Github

If you store your data in a publicly accessible github repository from your github account, then you can share
the data with anyone. 

Note however, github file-size limits mean this will only works for "small" files.

## UMBC & Google Drive

UMBC uses Google Drive: https://wiki.umbc.edu/display/faq/Google+Drive

## Google Drive & Colab

[Google documentation](https://colab.research.google.com/notebooks/io.ipynb) describes several methods of
getting data from a Google Drive into a Colab notebook.
This approach works for larger files.
But these methods require authentication, so they won't work in shared notebooks.

In particular, one of the methods involves mounting your entire Google Drive in a Colab notebook. 
This approach exposes all of the data in your Google drive to your Colab notebook.
I do not recommend that you mount your entire Google Drive in Colab.
Moreover, it requires authentication so it won't allow you to share data.

## Sharing a single file

You can share a single file from your google drive. 
There are security considerations in this case as well, so be careful about this approach.
However, if you choose to use the "Get shareable link" option for a file in your Google Drive, 
that link has the information necessary so that anyone can load the file into Colab.  

Here's an example of a shareable link (it is not a working example):

    https://drive.google.com/file/d/1C7Rw06hhv0HgyjN28nMie6iI77F7hewoL/view?usp=sharing

That URL contains a unique ID for the file of interest. 
The ID is the string `1C7Rw06hhv0HgyjN28nMie6iI77F7hewoL` that appears between the two `/` characters.
You can use the ID to construct a URL that will allow anyone to download the file. In this example, the URL is

    https://drive.google.com/uc?export=download&id=1C7Rw06hhv0HgyjN28nMie6iI77F7hewoL

Once you have such a string, anyone can use it to access the data from Colab without authentication.
For example, if the shared file is a CSV file, then you can load the file with pandas as follows (again, this is not a working example):

    import pandas as pd
    url = "https://drive.google.com/uc?export=download&id=1C7Rw06hhv0HgyjN28nMie6iI77F7hewoL"
    df = pd.read_csv(url)

There are file-size restrictions for this approach.
Nevertheless, it works for files that exceed the github limits.
