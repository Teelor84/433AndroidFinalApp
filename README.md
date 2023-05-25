# 433AndroidFinalApp
Final app created for my CIS433 Android Design class. 
Tyler Pourmand and Kyle Lombardi 

Major/Required Features:
Navigation:
	-Navigation between screens is facilitiated with simple buttons.
The app includes a MySQLlite database
	-This database has a table genre_points with two columns, Genres and Points
	-Genres consists of strings that are added on app startup. There are four genres, Rock, Rap, Country and Jazz
	-The other column, Points, keeps track of the points each genre has. Each genre (or two depending on the question) will have its associated points value incremented when an answer is submitted. 
	-There are 6 queries
		-Four of them are for incrementing the Points column depending on the column string 
		-One query adds the result of the quiz to a list based off which Points column has the most points, getting the string and storing it. If there is a tie both are put in
		-One query to reset the table on app startup to ensure results from previous quizes do not interfere. 

The app consists of 13 screens
-1 introduction screen 
	-Introduction screen that gives the idea of what the app does and its purpose. The user has the option to check a checkbox. This checkbox will enable notifications. When the user clicks on an option for a question, they will receive a notification for what genres that answer will add a point to. 
-10 question screens
	-The first question screen contains a time picker. The user selects a time on the time picker and based on the hour it will add a point to the genre when submitted. The genres are divided into 6 hour segments that are measured in military time internally. To use the means described in the code, 0 < input < 6 is rap, 6 < input < 12 is country, 12 < input < 18 is rock, 18 < input < 24 is jazz. The user first verifies the time they selected first, this was implemented to provide an onClick means of getting the time. This verify time button is also the means by which notifications are sent if enabled. 
	-Every other question uses radio buttons, most are 4 questions while some have 2, in which case they add points to two genres each. 
-1 results screen
	-The genre winnner is pulled from the List made by the corresponding query mentioned above. If there is a tie between genres, the genre in the first index will be the result. Each genre result has two videos associated with it, the videos put in the video players will depend on the result. 
	-There are three buttons, a Restart quiz button, a History button and a Spoiler button
		-The Restart button prompts the user with a dialog on if they want to restart the quiz, this essentially restarts the app. 
		-The History app will send the user to Google Maps and depending on the result will set the coordinates to a museum where you can learn about that genre. 
		-The Spoiler button takes you to the spoiler page.
-1 spoiler page
	-The spoiler page consists of a recyclerview which lists the genres and the two songs each genre is associated with along with a youtube link to that song. 

Optional Features to be graded:
-Checkbox - 5 pts
	-Click the Spoiler Notifications checkbox at the start of the app
-Time Picker - 7.5 pts
	-Click on the time picker in question 1 after the intro page. Click the verify time to set your answer and submit, thus adding a point to the genre based off the time
-Radio Buttons - 0 pts as it is part of checkbox
	-The main means answering most questions except question 1. 
-Notifications - 7.5 pts
	-Check the Spoiler Notifications checkbox at the start and you will receive notifications every time you click on but do not submit an answer. 
Video Player - 10 pts
	-On the results page two videos will be available to play depending on the quiz result. Click on the video to bring up a media controller at the bottom of the screen to pause/play the video or skip forward or backward. 
-Alert Dialog - 5 pts
	-When you reach the results page, click on the Restart button and you will receive an alert dialog that asks if you want to restart the quiz. You can either cancel the alert or click Restart to restart the app. 
-GPS - 10 pts
	-Click on the History button on the results page and you will be taken to a museum depending on the genre.
-RecylerView - 7.5 pts
	-On the results page click on the Spoiler button and you will be presented with a RecyclerView containing all possible genres and the two songs associated with them.  

Usage/Special Info:
In order to restart the app from the results page properly no videos must be playing. If you do not pause the videos before clicking the restart button in the dialog it will crash the app rather than restart it.
