# ND111 - Data Wrangling `Lesson02`

#### Tags
* Author : AH Uyekita
* Title  :  _Gathering Data_
* Date   : 24/12/2018
* Course : Data Science II - Foundations Nanodegree
    * COD    : ND111
    * **Instructor:** David Venturi
    * **Instructor:** Mat Leonard


#### Related Courses

* [UD595 - Get Into the Shell][rel_1]
* [UD001 - Intro to HTML and CSS][rel_2]

[rel_1]: https://classroom.udacity.com/courses/ud595
[rel_2]: https://classroom.udacity.com/courses/ud001

********************************************************************************

## Gathering

This is the first step of any Data Wrangling, sometimes this process is a bit complicated because you need to find these data (probably from different sources and then merge).

### Flat File

This is the way to store data into a single text file, usually, this file has another extension (.csv, tsv, etc.), each one of this extension has your own characteristic.

* Each variable/features is separated by a comma and each row is an observation;
* Each variable/features is separated by a tab and each row is an observation.

There are some **advantages** for using the flat files.

* Anyone could read, even a human;
* Is lightweight;
* You do not need to install a specific software;
* Simple to understand (each variable is delimited by a coma/tab);
* Any software could open it;
* Very good to small dataset.

But has disadvantages also:

* Do not have standard;
* Do not have data integrity checks;
    * Duplicated rows;
    * You can record any value in any field;
* Not great to large datasets.

##### Importing the tsv file

I have used the `read_csv` to load the data, but I have set the sep argument as `\t`, which means tabular. Sometimes, the flat files use `;` or `,`, so it is necessary to define what is the delimiter.

**Example:**
```py
import pandas as pd
df = pd.read_cvs('bestofrt.tsv', sep= '\t')
```

### Web Scraping

This is terminology is used to say the data extracted from a website (usually using code to do it). Due to this code depends on the HTML file, if any change of the website happens, all the code used to web scrapping could stopping to working properly, which requires an adjustments. For this reason, web scraping is not a definitive solution.

### HTTP Request

This is useful to access archives from the internet, combining with the OS package, it is possible to download and store locally the file.


## Encoding and Character Set

This explanation is based on [this][url_1] Stack Overflow thread.

Encoding: Is a proccess to convert a something into bytes.

* Audio is encoded into MP3, WAV, etc.
* Images is encoded into PNG, JPG, TIFF, etc.
* Text files is enconded into ASCII, UTF-8, etc.

The Character Set is as the name, is a set of charaters which I can use to write a phrase, each character has a code which represents the letter/character. There are several character set such as ASCII and UTF-8.

[url_1]: https://stackoverflow.com/questions/6224052/what-is-the-difference-between-a-string-and-a-byte-string

## Application Programming Interfaces - API

The API let you access the data from the internet in a resonable easy manner.

There are several API available in the internet for many social media:

* Facebook;
* Instagram;
* Twitter, etc.;

This lesson will use the [Mediawiki][url_2], which is a Open Source API to Wikipedia.

[url_2]: https://www.mediawiki.org/wiki/MediaWiki

Most of the file from the API are formated as JSON or XML.

### JSON and XML

JSON stands for Javascript Object Notation and XML for Extensible Markup Language.

Sometimes the regular tabular way to structure the data is not a good solution, and for this reason, there are other forms to store data as JSON and XML.

They use a kind of "dictionary" to store data, which allows storing more than one information per variable.

There are some similarities in JSON and Python:

* JSON Array = Python list
* JSON Object = Python dictonary



## Methods in this Lesson

#### `.find()`

This method is used to find tags and containers.

**Example:**
```py
soup.find('title')
```
This code above will find the tag title, and return the content.

#### `.find_all()`

It is almost the same of `.find()`, but will find in all document the given pattern.

**Example:**
```py
something.find_all('div')
```
This code will return all `div` in the document. It could be used with `limit = 1`, which will return the first `div`.

#### `.contents`
The `.contents` get the elements from the `find` and `find_all`.You are capable to select, which element you want (indexing).

```py
something.find_all('div')[1].contents[2]
```
In this fragment of code, I am selecting only the third element of `something.find_all('div')[1]`.

#### `os.listdir()`

This function list all files inside a given folder/directory.

```py
os.listdir(my_path)
```
#### `.glob()`

This method is a part of the glob package.

If you are familiar with Linux CLI, you have alread used the globbing to find a file in a folder.

```py
import glob
glob.glob('any_folder/*.txt')
```
The result of the `.glob()` will be a list with all files which matches the `.txt`.


#### `.read()`

Convert the file into a in memory variable.

```py
my_new_variable = file.read() # my_new_variable is a variable which contains the file.
```

#### `.readline()`

Read line by line every instance which is used this method.

```py
file.readline() # Read the first line of the document file
file.readline() # Read the second line of the document file
file.read()     # Read the rest of the content.
```

#### `.DataFrame()`

This method from the pandas package converts a simple dictonary to a Pandas DataFrame.

```py
pd.DataFrame(my_dataframe, columns = ['column_1', 'column_2', 'column_3'])
```

#### `.page()`

The `.page()` method from the wptools package converts a Wikipedia page into a object.

```py
any_website = wptools.page('E.T._the_Extra-Terrestrial')
```

#### `.get()`

The `.get()` method from the wptools package extract all info from the wptools object.

```py
any_website = wptools.page('E.T._the_Extra-Terrestrial').get()
```
