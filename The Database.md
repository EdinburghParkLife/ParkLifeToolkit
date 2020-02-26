## The database
The SQLite database is one file named `botpressDatabase.db` in the botpress folder. This can be renamed, as long as the contents of the `.env` file is also updated with this name.

To read the database you need SQLite installed on your system, or at least software capable of reading SQLite databases. An example is sqliteBrowser https://sqlitebrowser.org/

*The database is by default in SQLite. You can change to using PostGres as the database, but this is more advanced and you can refer to the botpress documentation on how to do so.*

To obtain data for visualisations and/or manipulation, you will need sqlite installed.
To check if you already have sqlite installed, run `sqlite` in your terminal window. If the prompt changes to say `sqlite` then you do, else it will say that the command is not recognised in which case you do not have it installed.


* Install sqlite from here: https://www.sqlite.org/download.html. Select the version that is for your operating system and has `A bundle of command-line tools for managing SQLite database files...` in the description.
* Once the correct version of sqlite is downloaded, extract it to a folder.
* Open a terminal window and navigate to this foler
* Enter `sqlite C:\botpress\botpressDatabase.db` in the terminal. Replacing the path with e=wherever you have put your database file.
* You are now in sqlite and can now run queries on the database.