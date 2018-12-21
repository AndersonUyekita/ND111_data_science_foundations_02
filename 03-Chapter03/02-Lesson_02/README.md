# ND111 - Data Wrangling `Lesson02`

#### Tags
* Author : AH Uyekita
* Title  :  _Gathering Data_
* Date   : 18/12/2018
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

### Web Scrapping

This is terminology used to say the data extracted from a website (usually using code to do it).
