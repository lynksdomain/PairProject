# Where to begin

First, the github lead will create a new project. The other fellow will help the lead as the support in making sure the storyboard set up is done correctly. That means: setting the info.plist to allow http calls, creating all the appropriate viewcontrollers (THERE ARE NO STORYBOARD SEGUES), tab bar hook up (the support should look up icons for the tab bar badge and should be set NOW), creating all the constraints for all the objects (imageViews, textViews,labels, activity indicators) you are going to use (remember that custom collection cells themselves do NOT have constaints within the collection view), setting all identifiers for storyboards that need to be segued too as well as cell identifiers, creating all the Cocoa Touch Class files and assigning them to the right VC's, and creating all the appropriate outlets.

![image](https://drive.google.com/uc?export=view&id=1FWIytYIVVDPqtRmaZH5VUs49-HxfXgr4)

YOU REALLY REALLY WANT TO HAVE ALL THE STORYBOARD ELEMENTS AND FILE CREATION DONE BEFORE YOU MOVE ON. AGAIN PLEASE MAKE SURE YOU HAVE THESE THINGS DONE BEFORE YOU TOUCH A SINGLE LINE OF CODE. YOU SHOULD RUN THE APP AND ALTHOUGH YOU WONT SEE ANYTHING, YOU WANT TO MAKE SURE YOU CAN COMPILE. MAKE SURE IT IS ALL DONE. YOU HAVE BEEN WARNED.


now that you have all the set up you need, the lead will create a new repo and push the project onto the repo. Once it is up, the support will go to the repo, fork it, and clone it to their computer. decide who will work on which set of cards and go to the appropriate section:


# Magic

endpoint: https://api.magicthegathering.io/v1/cards?contains=imageUrl

your model should obtain: name, imageUrl, text, and foreignNames. Within foreignNames you need the name, text, imageUrl, and language.

You will need to present a rows of 3 cells where the cell holds the card image. There are objects that you get back that do NOT have an image, you will need to make sure what you use all have images (filter is a thing, remember?) You cannot use the api to do this, you must create your own function or set up for this. You cannot use a default picture (like picture not available)

![image](https://media.giphy.com/media/64avcXl2bRD48B9vAY/giphy.gif)

commit and push.

now when a cell gets selected, a detail viewcontroller is modally presented above the current vc. This will need to be done programatically. On this detailvc, there is only a collection view and the cells will display the foreignnames info. the appropriate picture, two labels for the language and name and one textview for the text description. you should be able to click out of the cell to go back to the list

the activity indicator should turn on and off as needed on all the images


![image](https://media.giphy.com/media/cmzoqNwYtPMByypRU0/giphy.gif)

commit and push.

# Pokemon

endpoint: https://api.pokemontcg.io/v1/cards?contains=imageUrl,imageUrlHiRes,attacks

your model should obtain: imageUrl, imageUrlHiRes, attacks. Inside attacks you need name, damage, and text. All the data should give you these values so there is no need to create functions to filter it out (as far as I tested). 
You will need to present a rows of 3 cells where the cell holds the basic imageUrl image.

![image](https://drive.google.com/uc?export=view&id=1kVsleWhUxr3brDocb3L-buQRYKR32SSq)


commit and push.

now when a cell gets selected, a detail viewcontroller is modally presented above the current vc. This will need to be done programatically. On this detailvc, there is an imageView that displays the imageUrlHiRes image and a collectionview where the cells display the attack information. if the text for the description is an empty string, find a way to hide that cells textview. 

you should be able to click out of the cell to go back to the list

the activity indicator should turn on and off as needed on all the images


![image](https://drive.google.com/uc?export=view&id=1qXABCKz1PQwbZEWoYiXvfdvgJN5H0ITw)

commit and push.


# The Final Boss

Now we are done with both parts and everything has been pushed, we need to merge them to have one single project. The support will create a new pull request from their fork on github. Once created, the lead will go into their original repo and click the pull request tab which should say 1. You should be able to merge this pull request to obtain all the code from the support. Once this is done, both parties should be able to run the command "git pull origin master" on terminal in the folder of the project and be up to date.


# Extra Notes
The pair should be constantly communicating, do not isolate yourselves! Both members will code and equal amount.

merge conficts are the absolute worst, but not the end of everything. Part of the exercise is to begin dealing with the complexities of working with other people. google these new errors that come up and look on a way to solve it. 

if you realize you forgot to create a file or do something on the storyboard, tell the lead and have them make the change. Then they should commit and push. The support should then run the comman "git pull origin master" to take in all the new chaanges. Ideally you won't have to do this often or at all.



Happy coding!
