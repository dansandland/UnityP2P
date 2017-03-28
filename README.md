# UnityP2P
Peer to peer networking in Unity using a free Heroku server for signaling.

Here's how to do it:

1. Make an account on https://www.heroku.com/. It is free and doesn't even require you to enter payment info
2. Go into https://dashboard.heroku.com and click New, then Create New App.
3. Pick some random app name or let it choose one for you it doesn't really matter because this is just the websocket url that no one will see. Mine is nameless-scrubland-88927 but insert yours into the commands below instead
4. Install the [heroku cli](https://devcenter.heroku.com/articles/heroku-cli)
5. Clone this repo

git clone `https://github.com/Phylliida/UnityP2P.git`

then copy the server code (HerokuServer) into a directory without the .git file

6. In that directory, to login call

`heroku login`

7. Then create a new git repo there that will store your server code (Heroku works by having a git repo you manage your server code with)

`git init`
`heroku git:remote -a nameless-scrubland-88927`

(except use your server instead)

8. Now deploy your server

`git add .`
`git commit -am "Initial upload"`
`git push heroku master`

You can tweak the config.json file if you want but that isn't really needed

9. Open Unity, then select the UnityProject folder in this git repo to open it
10. Open the scene ExampleP2P (in the Assets folder) if it is not already open
11. In the ExampleP2PServer and ExampleP2PClient scripts attached to the server and client objects (respectively), change the Signaling Server variable to

`wss://nameless-scrubland-88927.herokuapp.com`

except use your sever instead. Note that you don't add the ports on the end.

12. Press play. This runs a server and a client, so look at the debug logs and you should see things happening :)

I haven't documented things yet but if you look at the ExampleP2PServer and ExampleP2PClient code it is simple enough that it should give you a jist of what is going on