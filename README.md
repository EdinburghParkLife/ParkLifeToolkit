# Parklife Toolkit

This is a quick-start guide for setting up your own instance of botpress and using the template chatbots created in the Parklife project.
For more information and more details documentation, please visit https://botpress.com/docs.

## Setup

### Downloading the toolkit
Download botpress for your operating system from here: https://botpress.com/download and unzip the folder to a sensible location.

Download the toolkit from here: https://github.com/EdinburghParkLife/ParkLifeToolkit/raw/master/Parklife%20toolkit.tar.gz and unzip the folder to a sensible location.

Place the contents of the toolkit folder into the botpress folder. Your botpress folder should now look something like this:

![alt text](https://github.com/EdinburghParkLife/ParkLifeToolkit/raw/master/documentation%20images/botpress%20folder.png "Botpress folder contents")

**The contents**:

* bindings folder
* modules folder
* data folder
* bp / bp.exe

These are included by default in the botpress download. They are used to run and manage the chatbot server.

* botpressDatabase.db

This is an empty database file used by the chatbot to store interactions with it. This has been provided by the Parklife toolkit so you don't have to create one. This will become populated with data as the chatbot is used.

* .env

This is the environment file that points the chatbot at the database it should use. This points to a file named `botpressDatabase.db`, which is the previously mentioned file.

* getCSV.sql

This is an sqlite script to extract a list of questions and answers in CSV format from the database.

* ParklifeChatbot.tgz

This is the parklife chatbot. It has been provided so that it can be imported into a new instance of botpress and immediately used.

* images folder

This folder contains the chat bot images used in the Parklife project. It contains an image of Alfred the owl, used as the chatbot image, and backgrounds of four parks.

*Do not worry if you are missing the `data` folder, as this is not included in the Windows download.*

*Folders and files may be created as the chatbot(s) are used.*


### Starting up botpress
* Open a terminal window. (Alternatively named Console/Command prompt, depending on your operating system).
Navigate to your botpress folder. (Type `cd` followed by the path to the botpress folder. e.g. `cd C:\botpress` in windows, or `cd /home/username/botpress` in Linux or `cd /Applications/botpress` in MacOS.)
* Type `./bp` to run botpress. (Alternatively just `bp` or `bp.exe`, again OS dependent)
You will see text appearing displaying the startup of the chatbot. Botpress will now be up and running!
* To stop botpress at any point, press ctrl+C or just close the terminal window.
* In your web browser, navigate to `http://localhost:3000`. You will be shown a login window.

![alt text](https://github.com/EdinburghParkLife/ParkLifeToolkit/raw/master/documentation%20images/botpress%20login.png "Botpress login window")

*Note that if you have anything already running on your machine that uses this port, botpress will attempt to use the next available one. This should be noted on the startup text.*

It will ask you to sign up. All you need to provide is an email and passsword. These can be anything you choose as they are purely used for login security. Remember these credentials as you will need them again to log back in.

## Usage

### Importing the chatbots
To import the chatbot provided, click the dropdown `Create Bot` and select `Import Existing`.

![alt text](https://github.com/EdinburghParkLife/ParkLifeToolkit/raw/master/documentation%20images/botpress%20import%20bot.png "Botpress import chatbot")
 
The window you are given allows you to create the bot ID for the chatbot. This will be used as part of the web address the end users will visit when they use the bot. So this should be something succinct and meaningful.

![alt text](https://github.com/EdinburghParkLife/ParkLifeToolkit/raw/master/documentation%20images/botpress%20botID%20and%20Name.png "botpress botID and Name")


Then select the bot archive. Choose the `Parklife Chatbot.tgz` to import.

Once imported, the chatbot will appear in the bot list.
Now selected ‘configure’ next to this newly imported bot.
Here, you can change the Name of the bot, Description and More Details such as website and contact details.
You can also change the Bot avatar, which will be displayed to end users, and the cover picture.

![alt text](https://github.com/EdinburghParkLife/ParkLifeToolkit/raw/master/documentation%20images/botpress%20details.png "botpress details")


### Starting a chat

Click `Open Chat` next to any chatbot in the list to start a chat.

![alt text](https://github.com/EdinburghParkLife/ParkLifeToolkit/raw/master/documentation%20images/botpress%20Open%20Chat.png "Botpress Open Chat")


## Editing the chatbot

*I will only give basic instructions on changing and editing questions here, as you should consult the botpress documentation for more complex and detailed guidance and instructions.*

### Overview

Click on the name of any chatbot in the list. You will now see the construction of the chatbot.

The chatbot is built as a flow diagram:

![alt text](https://github.com/EdinburghParkLife/ParkLifeToolkit/raw/master/documentation%20images/botpress%20flow.png "Botpress import chatbot")

Each box (named a `node` by botpress) is where the chatbot will perform an action, such as asking a question.
Once the action is complete, the chatbot moves to the linked box as illustrated by the black lines.

The chatbot starts where the `start` green dot is indicated, on the very top, left, of the flow. When the chatbot has performed its action, in this case introducing itself, it goes to the next node where it asks a question.

*Use the scrollwheel to zoom in and out. Note that this may be time consuming on larger chatbots!*

### How it works

Click on a box (a `node`) to see its contents on the left panel of the page.

A `node` has 3 things it does:
1. On Enter - What it does immediately
2. On Receive - Does it save user input
3. Transitions - What node it goes to next

![alt text](https://github.com/EdinburghParkLife/ParkLifeToolkit/raw/master/documentation%20images/botpress%20node.png "Botpress node")

* An example of `On Enter` - Say some text
* An example of `On Receive` - Wait for user input
* An example of `Transitions` - Go to next question

## Create a new question

![alt text](https://github.com/EdinburghParkLife/ParkLifeToolkit/raw/master/documentation%20images/botpress%20nodes.png "Add a node")


### Add a free text question

* Drag and drop `Node` under `Tools` on the left panel onto the flow diagram in an open space.
* Make sure this new `node` is selected and press the plus button under the `On Enter` section and select `Text` > `Add new text` to add the question you want. Type it in and select`Save` and `Update node`.

![alt text](https://github.com/EdinburghParkLife/ParkLifeToolkit/raw/master/documentation%20images/botpress%20add%20text.png "Add text")


### Wait for user feedback

* Select the node you created
* Click on `On Receive` on the left panel.
* Tick the `Wait for user feedback` box.

### Add question transition

This is adding the link to the next question after this question is answered. This is required for the chatbot to continue after this question.
* Make sure this new `node` is selected
* Click on `Transitions` on the left panel
* Click the Plus icon button
* Select `Always` and `Transition to node` to always go to another question after this one is answered.
* Click `Create`

### Add a multiple choice question

* Drag and drop `Choice` under `Tools` on the left panel onto the flow diagram in an open space.
* In the pop-up window, select the folder button, then `Create new single choice`.
* Now enter your question and the answers you want. Each answer has text and a value. Press the green plus button to add another possible answer.
* *The message and values for each choice are what is displayed to the user, and what will be saved to the database, respectively. These can be the same for simplicity.*
* Now select `Save` and then `Insert`.
* *`Wait for user feedback` and transition points are already created for you.*

![alt text](https://github.com/EdinburghParkLife/ParkLifeToolkit/raw/master/documentation%20images/botpress%20add%20choice.png "Add choice")


### Connect the new question

Connect the question to a previous and next question in the flow by dragging the small square at the top of the node to the previous questions bottom.

![alt text](https://github.com/EdinburghParkLife/ParkLifeToolkit/raw/master/documentation%20images/botpress%20node%20connection.png "Botpress node connection")

### Copy an existing question

To make the question creation process easier, right click and copy an existing node then right click and paste. Edit as before.

## Change an existing question

* Click on a question
* Click on the `On Enter` section on the left panel
* Hover over the text and click `edit`.
* Click the pencil icon to edit the text
* Click `Submit` then `Update action` topm2 start './bp start -p' update the wording.

Some questions have information about the park following them.
To change this, do the exact same as above, but change the text in the `On Receive` section.

### Add error handling

If, on a multiple choice question, the user types something in that isn't one of the options you can ask the question again.
To do this, connect the `on error` Transition to either an error message `node`, then back to the question again. Or simply back to the question immediately to re-ask it.


## Using the chatbot on a remote server
If you intend on running this on a remote server, like the parklife chatbot which runs on the parklife website, you will need to connect to the remote server and upload your botpress folder to it.

From the remote server, run `./bp` and botpress will be running on the remote machine the same way as it runs on your local machine.

If connecting from a terminal window, this window must remain open for botpress to continue running. To have it run it the background, you will need to have nodejs and npm installed.

* Install nodejs. Refer here for how to install it on your system: https://nodejs.org/
* Install pm2. `sudo npm install -g pm2`. Now you can use the `pm2` `node module` to run and monitor botpress without keeping the window open.
* Use the command `pm2 start 'bp start -p'` from within the botpress folder. You may need to use a variant of `bp`, `./bp`, `bp.exe` etc, OS dependent.
* You can check the status of your botpress process by running `pm2 list`
* You can stop botpress using `pm2 stop 'bp start -p`

## Chatbot example

The Parklife project has multiple chatbots for parks in and around Edinburgh. One such chatbot is at The Meadows park.

This chatbot can be accessed from this link: [Link currently unavailable].

You can visit this chatbot to see it in action. The aim of this chatbot is to collect data from people who visit the park. It is also the chatbot that is provided as an example in this toolkit.

## The database
The SQLite database is one file, named `botpressDatabase.db` in the botpress folder.

To read the database you need SQLite installed on your system, or at least software capable of reading SQLite databases.

*The database is by default in SQLite. You can change to using PostGres as the database, but this is more advanced and you can refer to the botpress documentation on how to do so.*

To check if you already have sqlite installed, run `sqlite` in your terminal window. If the prompt changes to say `sqlite` then you do, else it will say that the command is not recognised in which case you do not have it installed.

To read from the database, you can install any sqlite database reader tool. An example is sqliteBrowser https://sqlitebrowser.org/

* Install sqlite from here: https://www.sqlite.org/download.html. Select the version that is for your operating system and has `A bundle of command-line tools for managing SQLite database files...` in the description.
* Once the correct version of sqlite is downloaded, extract it to a folder.
* Open a terminal window and navigate to this foler
* Enter `sqlite C:\botpress\botpressDatabase.db` in the terminal. Replacing the path with e=wherever you have put your database file.
* You are now in sqlite and can now run queries on the database.


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

Kibana is the front end for visualising data from the Parklife Chatbots. This too provides a tool for creating word clouds.