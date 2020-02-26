## Visualisations

You can make useful visualisations from the data you collect for users.

### Obtaining data

The `getCSV.sql` file included in the toolkit is a script to extract a list of questions and answers from the botpress database. Use this script to extract a list of questions and answers from the database in CSV format. You have two options for doing this:
 
#### Option 1

This option uses sqlite's inbuilt functions to create a CSV file from a query.

1. Open a terminal window
2. Run `sqlite`
3. Now in sqlite, run the command `.mode csv`
4. Run the command `.output myFile.csv`
5. Run you query. This can be as simple as `SELECT * FROM EVENTS` or more complex, such as the contents of the `getCSV.sql` file.
6. This should have created the `myfile.csv` file with the data in your current directory.

#### Option 2

If this method does not work for you, you may not have the latest version of sqlite installed. If not, try this method:

1. Open a terminal window
2. Run `sqlite`
3. Now in sqlite, run the command `"SELECT * FROM events;" > myFile.txt`
4. This should have created the `myfile.csv` file with the data in your current directory.
5. Now run your own query, or use the contents of the `getCSV.sql` file

You will now have a CSV of questions and answers that you can use in visualisations.

### Excel

You can open the CSV file directly in excel to view the data.
If you are familiar with Excel, you can use this data to immediately start creating tables visualising it.

#### Pivot table

* Select the data you want to visualise (Drag over all the cells of data, including field names.)
* Select insert > Pivot table
* Select the columns you want to use (BotID, Question and Answer)
* Select the metrics you want to use to visualise the data

#### Chart

* Select the data you want to visualise (Drag over all the cells of data, including field names.)
* Select insert > chart (Be it pie chart, bar chart etc)
* Alter the details of the chart(s) to your liking.

### Word cloud

You can use this CSV file and import it into software such as Wordle to create Word Clouds.

![alt text](https://github.com/EdinburghParkLife/ParkLifeToolkit/raw/master/documentation%20images/wordle%20word%20cloud.png "Wordcloud")

The word cloud above is an example made in Wordle, displaying the most used words in a provided dataset. This could also be narrowed down to the most used words for specific questions.

Kibana is the front end for visualising data from the Parklife ChatBots. This too provides a tool for creating word clouds.