freeCharades
====================

![alt text](/path/to/logo.png)

What is freeCharades?
---------------------

freeCharades is a game application for mobiles that allow users to play charades with friends. Charades is a word guessing game for at least two players. One player holds up the device and a word or phrase will show on the screen once the game starts. The second player who is able to see the word should act out the word or phrase, without using words. The first player has to guess what the word on the screen is. The first player gets one point for every word they guess correctly. When playing freeCharades, the first player flip the phone up above their head if they guessed it right, and the back down onto your forehead to get a point and move to the next word. If the player could not guess the word or had an incorrect guess, they flip the phone down and back up to move on to the next word. To move on to the next word without guessing incorrectly, flip the phone down and back up.

How to run it locally 
---------------------
In order to run the codes locally, I can execute HTTP server using the following command line:
`$python3 -m http.Server 9000`
The HTTP server will serve the HTML file from my current directory on port 9000. The server will also print out an IP endpoint that I can use to load the page on the web-server. 
Since this application is for mobiles, I also test freeCharades locally on modile devices. This can be done by using NGROK. NGROK provides a tunnel for the HTML file, which is currently served on the port of local repository to be served on a port of the public repository of NGROK. NGROK provides a URL with which the test app can run locally on the mobile device. 

Core concepts
-------------
    ### Screens
    The app consists of 9 screens, namely,
    *  The permission request screen, where iOs users allow freeCharades app to access Motion and Orientation of the device since iOs does not allow this by default,
    *  The starting screen, where players hit a start button to start the game,
    *  The instruction screen, where players find instructions of how to play the game,
    *  The acknowledgement screen, where players learn the makers of freeCharades,
    *  The countdown screen, where there is a countdown timer before a game session starts,
    *  The word screen, where words show up during a game session; there is another countdown timer that limits the duration of each session,
    *  The ending screen, where the result shows up along with the list of words that have been shown during the game sessions; there is a restart button for players to start a new game session. 
    *  The two screens that instruct players to flip their screen to the right orientation; note that the only orientation that this app allows is the normal landscape position of the device

    ### Overlays
    The three screens servings as overlays are the permission request screen for iOs devices, and the reorientation screens. Overlays are screens that are on top of other screens.  

    ### Screen orientations 
    Screen orientations are detected to keep track of correct and incorrect words and move on to next words during a game session. I use `window.addEventListener()` method , which listen to the changes in the device orientation, the gamma property of the device orientation event, which detects whether the device is flipped up or down, in order for the appropriate functions to be called accordingly. 

    ### iOS 
    Before playing freeCharades, iOs users must allow freeCharades app to access Motion and Orientation of the device since iOs does not allow this by default.
