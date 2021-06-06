# Description:
This Repository is part of Udacity's Data Engineering Nano Degree Program
It conntains the deliverables for **Project: Data Modeling with Cassandra**

The purpose of the project is to provide Analytical Capabilities for a fictional Music Streaming Company called _Sparkify_
regarding User listening habits using JupyterNotebooks for the creation of tables, data loading and development of 
three queries queries in response to User Requirements (detailed in the following sections).

## Dataset
The dataset is comprised of .csv files partitioned by date, located in the _event_data_ folder
Example files can be found in the _data.zip_ file, which need to be extracted along the JupyteNotebook file.

## User Requirements
The User needs to be able to get the data using the following query definitions:
1. Give me the artist, song title and song's length in the music app history that was heard during  sessionId = 338, and itemInSession  = 4
2. Give me the name of artist, song (sorted by itemInSession) and user (first and last name) for userid = 10, sessionid = 182
3. Give me every user name (first and last) in my music app history who listened to the song 'All Hands Against His Own'

## Database
The destination is a Cassandra keyspace called _udacity_ using three denormalized tables:
    * songplays_bySessionId: Returns Song Information (artist,title,lenght) for a particula SessionId and SessionItem
    * songplays_byUserId   : Returns Song (artist,title) and UserName (First,Last) for any given UserId and SessionId, ordered by ItemsInSession
    * userName_bySongTitle : Returns User's FirstName and LastName for users who have listened any given Song (song_title)

## Jupyter Notebook contents
Part I. ETL Pipeline for Pre-Processing the Files:
    * Creation of one Master (_event_datafile_new.csv_) CSV file which includes the data in each CSV file in _event_data_ folder
    * Initialization of Cassandra connector, including _udacity_ keyspace

Part II. Project Code. 
    The following activites were developed for each of the three queries:
    * Development of CREATE query for table creation
    * Development to process and load Master _event_datafile_new.csv_ file
    * Development of SELECT query in order to test/verifiy table fulfill User Requirements

    End of Process
    * Table destruction
    * Session and Cluster termination

## Software Pre-Requisites
The following Tools and Modules need to be installed in order to to run the code in this repository:
* Cassandra Database
* Cassandra Database connector for Python
* Pandas
* os, glob, csv for CSV file processing