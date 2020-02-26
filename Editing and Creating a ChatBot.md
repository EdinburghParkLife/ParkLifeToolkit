
## Editing and/or Creating a ChatBot

*I will only give basic instructions on changing and editing questions here, as you should consult the botpress documentation for more complex and detailed guidance and instructions.*

### Overview

Click on the name of any ChatBot in the list. You will now see the construction of the ChatBot.

The ChatBot is built as a flow diagram:

![alt text](https://github.com/EdinburghParkLife/ParkLifeToolkit/raw/master/documentation%20images/botpress%20flow.png "Botpress import ChatBot")

Each box (named a `node` by botpress) is where the ChatBot will perform an action, such as asking a question.
Once the action is complete, the ChatBot moves to the linked box as illustrated by the black lines.

The ChatBot starts where the `start` green dot is indicated, on the very top, left, of the flow. When the ChatBot has performed its action, in this case introducing itself, it goes to the next node where it asks a question.

*Use the scrollwheel to zoom in and out. Note that this may be time consuming on larger ChatBots!*

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

This is adding the link to the next question after this question is answered. This is required for the ChatBot to continue after this question.
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
