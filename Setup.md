## Setup

### Downloading the toolkit
Download botpress for your operating system from here: https://botpress.com/download and unzip the folder to a sensible location.

Download the toolkit from here: https://github.com/EdinburghParkLife/ParkLifeToolkit/raw/master/Parklife%20toolkit.tar.gz and unzip the folder to a sensible location.

Place the contents of the toolkit folder into the botpress folder. Your botpress folder should now look something like this:

![alt text](https://github.com/EdinburghParkLife/ParkLifeToolkit/raw/master/documentation%20images/botpress%20folder.png "Botpress folder contents")

That's it, you're setup and ready to go.

**Explanation of the contents**:

* bindings folder
* modules folder
* data folder
* bp / bp.exe

These are included by default in the botpress download. They are used to run and manage the ChatBot server.

* botpressDatabase.db

This is an empty database file used by the ChatBot to store interactions with it. This has been provided by the Parklife toolkit so you don't have to create one. This will become populated with data as the ChatBot is used.

* .env

This is the environment file that points the ChatBot at the database it should use. This points to a file named `botpressDatabase.db`, which is the previously mentioned file.

* getCSV.sql

This is an sqlite script to extract a list of questions and answers in CSV format from the database.

* ParklifeChatBot.tgz

This is the parklife ChatBot. It has been provided so that it can be imported into a new instance of botpress and immediately used.

* images folder

This folder contains the chat bot images used in the Parklife project. It contains an image of Alfred the owl, used as the ChatBot image, and backgrounds of four parks.

*Do not worry if you are missing the `data` folder, as this is not included in the Windows download.*

*Folders and files may be created as the ChatBot(s) are used.*
