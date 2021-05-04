
# Colab

How to import data into a Colab session.

## Publicly accessible data in github

To load publicly accessible data from a github repository, 
use the URL that appears provided by the "Raw" button that appears when you view the file from your browser.
For example, the following code loads the Iris dataset from Raschka's 
[public repo for Chapter 2]( https://github.com/rasbt/python-machine-learning-book-3rd-edition/tree/master/ch02).

    url = "https://raw.githubusercontent.com/rasbt/python-machine-learning-book-3rd-edition/master/ch02/iris.data"
    data = pd.read_csv(url, header=None)

This works for small files below the 100 MB
[github file-size limit](https://docs.github.com/en/github/managing-large-files/conditions-for-large-files). 

## A shared file in your Google Drive

If you choose the "Get shareable link" option for a file in your Google Drive,
that link contains a unique ID that will allow anyone can load the file into their Colab session.
For example, here's a shareable link (it is not a working example):

    https://drive.google.com/file/d/1C7Rw06hhv0HgyjN28nMie6iI77F7hewoL/view?usp=sharing

The unique ID is the string `1C7Rw06hhv0HgyjN28nMie6iI77F7hewoL` that appears between the two `/` characters.
Use it to construct a URL that you can use to download the file:

    https://drive.google.com/uc?export=download&id=1C7Rw06hhv0HgyjN28nMie6iI77F7hewoL

The download URL can be used to load the file into Colab without authentication.
For example, if the shared file is CSV, then you can load it with pandas (again, this is not a working example):

    import pandas as pd
    url = "https://drive.google.com/uc?export=download&id=1C7Rw06hhv0HgyjN28nMie6iI77F7hewoL"
    df = pd.read_csv(url)

There are file-size restrictions for this approach, but it works for files that exceed the github limits.

## Compressed files

Use the `curl` command to load publicly accessible files into a Colab session.
Then use unix commands to manipulate those files.
For example, 

    ! curl -Lo movie_data.csv.gz https://github.com/rasbt/python-machine-learning-book-3rd-edition/blob/master/ch08/movie_data.csv.gz?raw=true
    ! gunzip -f movie_data.csv.gz
    ! ls /content

## Large files shared from your Google Drive

You can load large files from your [UMBC Google Drive](https://wiki.umbc.edu/display/faq/Google+Drive).
[Google documentation](https://colab.research.google.com/notebooks/io.ipynb) describes several methods.
This approach works for larger files, but requires authentication
that can expose all the data in your folder, so be careful.
Here's an example: https://github.com/umbcdata602/howtos/blob/master/colab_data.ipynb
