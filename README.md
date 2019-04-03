# De-identifying Scripts

Jihyun Park (`jihyunp@uci.edu`)  
Aug 24, 2017

Modified by Renzhe Yu (`renzhey@uci.edu`)  
Apr 1, 2019

To deidentify clickstream data, you need to first run 'update_keys.py' which updates the 'master_keys.csv' file.


### `update_keys.py`
This file reads the 'Merged Data.csv' file for each course and <br>
updates the 'master_keys.csv' file. 

* Usage: `python ./update_keys.py <Mapping File> <New Students File>`
* Example: `python  ./update_keys.py  ./master_keys.csv  ../Year1/Physics3A_Merged_data.csv`




### `deidentify_clickstream.py`
Reads the mapping file (e.g. 'master_keys.csv') and then de-identifies <br>
the clickstream data. Running this file will create two folders <br>
inside the data directory : `processed/` and `deidentified/`

* Usage: `python ./deidentify_clickstream.py <Mapping File> <Clickstream Data Directory>`
* Example: `python  ./deidentify_clickstream.py  ./master_keys.csv  ./identifiable_data/MATH-Clickstream`




### `deidentify_merged_data.py`
Reads the mapping file (e.g. 'master_keys.csv') and then de-identifies <br>
the Merged Data file. It will create another file with the same name with '-deidentified'<br>
at the end which has the random id column at the first column, and does not have any identifiable columns. <br>
Make sure that you have already updated/created the mapping file using the merged file that you are about to deidentify.




### `deidentify_quiz_data.py`
Reads the mapping file (e.g. 'master_keys.csv') and then de-identifies <br>
quiz submission data in the folder. (This script is only for MathXX-FaXX). <br>
It will create two folders inside the existing data directory : processed/ and deidentified/




### `master_keys.csv`
Mapping file where the first five columns correspond to <br>
`[Name_firstlast],[studentid],[ucinetid],[randomid],[canvasid],` <br>
and the columns after that indicate whether the student had taken the course or not.
