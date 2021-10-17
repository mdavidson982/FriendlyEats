# Friendly Eats

Branch: Step 4 Set up the Firebase emulators
previous steps:
- clone the repo: git clone https://github.com/firebase/friendlyeats-android
- Create a new firebase project 'friendlyeats-android'
- add android app package name: com.google.firebase.example.fireeats
- download google-services.json file and copy it to the 'app' folder

In this codelab you'll use the Firebase Emulator Suite to locally emulate Cloud Firestore and other Firebase services. This provides a safe, fast, and free local development environment to build your app.

In Android Studio:
- import the project (Use the second option under the three vertical dots on the screen that lists recent projects). Navigate to the project folder on your machine and click 'open'.

- open a new terminal and run the command: npm install -g firebase-tools
if you get EACCESS errors run the same command again but include 'sudo' (Super User DO):
sudo npm install -g firebase-tools

- Check that firebase is installed: firebase --version (it should return a version number)
- run: firebase login 

- run: firebase use --add
Select the project and enter an alias name either 'default' or 'friendlyeats-android'

- Run the emulators: 
In your terminal from within the friendlyeats-android directory run firebase emulators:start to start up the Firebase Emulators.

CodeLab Step 5 'Run the App'

Run the App in the Android Emulator in Android Studio:

- Click: Build > Rebuild Project 
- Click: Run
The Android emulator should start after the build is finished. Use the 'Build' tab at the bottom of Android Studio to see the build progress.
Use LogCat to see the messages between the Android Emulator and Android Studio

- The emulator should present a signo on screen asking for a user and email. Put in a test use email and password.

Now open the Emulators UI by navigating to http://localhost:4000 in your web browser. Then click on the Authentication tab and you should see the account you just created:

Step 6: Write Data to Firestore

Now we will paste in some code from the codelab. For each of the code changes highlight the code in the codelab an paste it into the appropriate place in android Studio. the first change is in MainActivity.java, replace the 
code in the onAddItemsClicked() method with the code from the codelab.
Run the app again and click on the Add Random Items button in the overflow menu of the Android Emulator.
Now go back to the firestore emulators in the browser (http://localhost:4000) and click on Overview then Firestore Emulator. You should see the collection of restaurants added to Firestore.

This data is 100% local to your machine. In fact, your real project doesn't even contain a Firestore database yet! This means it's safe to experiment with modifying and deleting this data without consequence.

Branch: Step7-Display Data from Firestore

In this section, you'll learn how to retrieve data from Cloud Firestore and display it in your app. The two key steps are creating a query and adding a snapshot listener. This listener will be notified of all existing data that matches the query and will receive updates in real time.

Step 8: Sort and Filter Data
Edit the onFilters() method in MainActivity.java. Add the code from the codelab. Run the app and You should now be able to filter the list.

Step 9: Organize data in subcollections
Open RestaurantDetailActivity.java and enter the code from Step 9 in the codelab to implement the addRating function

Step 10: Secure your data

This step involves making more robust rules to manage how data in cloud firestore is managed. In VS Code open the firestore.rules file and enter the updated rules_version = '2' from the codelab.

When you save the firestore.rules file the Firestore emulator will automatically hot reload the new rules and apply them to future requests, there is no need to restart the emulators.

################ CODELAB DOCUMENTATION ################

This is the source code that accompanies the Firestore Android Codelab:
https://codelabs.developers.google.com/codelabs/firestore-android

The codelab will walk you through developing an Android restaurant recommendation
app powered by Cloud Firestore.

<img src="docs/home.png" width="300"/>

If you don't want to do the codelab and would rather view the completed
sample code, see the Firebase Android Quickstart repository:
https://github.com/firebase/quickstart-android

## Build Status

[![Actions Status][gh-actions-badge]][gh-actions]

[gh-actions]: https://github.com/firebase/friendlyeats-android/actions
[gh-actions-badge]: https://github.com/firebase/friendlyeats-android/workflows/Android%20CI/badge.svg
