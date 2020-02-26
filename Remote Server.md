## Using the ChatBot on a remote server
If you intend on running this on a remote server, like the parklife ChatBot which runs on the parklife website, you will need to connect to the remote server and upload your botpress folder to it.

From the remote server, run `./bp` and botpress will be running on the remote machine the same way as it runs on your local machine.

If connecting from a terminal window, this window must remain open for botpress to continue running. To have it run it the background, you will need to have nodejs and npm installed.

* Install nodejs. Refer here for how to install it on your system: https://nodejs.org/
* Install pm2. `sudo npm install -g pm2`. Now you can use the `pm2` `node module` to run and monitor botpress without keeping the window open.
* Use the command `pm2 start 'bp start -p'` from within the botpress folder. You may need to use a variant of `bp`, `./bp`, `bp.exe` etc, OS dependent.
* You can check the status of your botpress process by running `pm2 list`
* You can stop botpress using `pm2 stop 'bp start -p`
