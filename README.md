# var readlineSync = require('readline-sync');
var playerName = readlineSync.question("Please enter your name! ");

var introMessage = `Welcome ${playerName} to the Escape Room, enter if you Dare`;
console.log(introMessage);

//Boolean Flags
var isAlive = true;
var hasKey = false;

while(isAlive == true) {
    var menuID = readlineSync.keyIn("Press 1 to Place hand in hole \nPress 2 to locate the key \nPress 3 to Open the door and exit", {limit: '$<1-3>'});
    if (menuID == 1){
        //Player has selected menu option 1
        //Player put hand in the hole
        //Player is DEAD
        //Display appropriate message
        //Game is OVER
        console.log(" You put your hand in the hole. You're DEAD!!! Dare to try again? ");
        isAlive = false;
    }
    else if (menuID == 2 && hasKey == false)
    {
        //Player has never found the key before.
        console.log(`${playerName}, you found the key succesfully!`);
        hasKey = true;
    }
    else if (menuID == 2 && hasKey == true)
    {
        //Player has already found the key.
        console.log(`${playerName}, you have the key DUMMIE. Stop wasting time and proceed to menu option 3!`);
    }
    else if (menuID == 3 && hasKey == false)
    {
        //Player has never found key before.
        console.log(`${playerName}, you need to locate key first, then come back to this option.`);
    }
    else if (menuID == 3 && hasKey == true)
    {
        //Player has found the key.
        console.log(`${playerName}, proceed to door and run for your life!!! Congratulations, YOU WIN THE GAME`);
        isAlive = false;
        }
    }
