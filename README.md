<h1>Data Modeling with Cassandra for a startup called Sparkify</h1>

<h2>1. purpose of this database</h2>

<p>The purpose of this database is collectiong songs and user activities on the new music streaming app 
and understanding what songs users are listeing to optimize their user analysis.</p>

<h2>Datasets</h2>
For this project, working with one dataset: event_data. The directory of CSV files partitioned by date. Here are examples of filepaths to two files in the dataset:
event_data/2018-11-08-events.csv
event_data/2018-11-09-events.csv

<h2>2. database schema design and ETL pipeline</h2>
This database is star schema that simplifies business reporting and implements fast aggregation for this analysis.

<h4>Fact Table</h4>
<ol>
      <li><strong>songplays</strong> - records in log data associated with song plays i.e. records with page NextSong
            <ul>
                  <li>songplay_id  --> PRIMARY KEY </li>
                  <li>start_time </li>
                  <li>user_id </li>
                  <li>level</li>
                  <li>user_id </li>
                  <li>song_id</li>
                  <li>artist_id</li>
                  <li>session_id</li>
                  <li>location</li>
                  <li>user_agent</li>
            </ul>
      </li>
</ol>

<h4>Dimension Tables</h4>
<ol>
      <li><strong>users</strong> - users in the app
            <ul>
                  <li>user_id  --> PRIMARY KEY</li>
                  <li>first_name</li>
                  <li>last_name</li>
                  <li>gender</li>
                  <li>level</li>
            </ul>
      </li>
      <li><strong>songs</strong> - songs in music database
            <ul>
                  <li>song_id  --> PRIMARY KEY</li>
                  <li>title</li>
                  <li>artist_id</li>
                  <li>year</li>
                  <li>duration</li>
            </ul>
      </li>
      <li><strong>artists</strong> - artists in music database
            <ul>
                  <li>artist_id  --> PRIMARY KEY</li>
                  <li>name</li>
                  <li>location</li>
                  <li>latitude</li>
                  <li>longitude</li>
            </ul>
      </li>
      <li><strong>time</strong> - timestamps of records in songplays broken down into specific units
            <ul>
                  <li>start_time  --> PRIMARY KEY</li>
                  <li>hour</li>
                  <li>day</li>
                  <li>week</li>
                  <li>month</li>
                  <li>year</li>
                  <li>weekday</li>
            </ul>
      </li>
</ol>

<h2>3. Explanation of the files</h2>

<p><strong>Project_1B_ Project_Template.ipynb</strong> - reads and processes files from event_data and loads them into tables. </p>

<p><strong>event_datafile_new.csv</strong> - Denormalized data should appear like in the event_datafile_new.csv after the code is run.

