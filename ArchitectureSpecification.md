# User class

## Properties

| Name  | Type | Description
| ------------- | ------------- | ------------- 
| userInterests  | Interest[]  | An array of Interest objects with accessable variables and displays, and a button to access their page.  	
| nInterests  | int | A size integer for the interest array.	

## Functionality

| Name  | Parameters | Return | Description
| ----------  | ---------- | --------- | -----------
| addInterest()  | String interestname, int activityAmount, String activityPeriod, int activityLength, int numNotifications  | None  | Initializes an interest.
| searchInterest()  | String interestName | int arrayPos | Given an interest name, this function searches through the userInterest array and finds the array position of that interest.	
| deleteInterest()  | int arrayPos  | None  | Deletes an interest by initializing the constructor array position to null, the pulling all subsequent interests in the array down to fill in, and subtracts one from nInterests if the interest is found.	
| displayInterest()  | int arrayPos  | None  | Accesses a user's interest.	
| onAddActivity()   | View v | None | Takes user to add activity page. 

## Connections 
| Input or Output  | Function | Description
| -------------    | ---------- | ---------- 
| Input            | onAddActivity   | Takes user to addInterest page when Add Interest button is clicked. 


# Interest Class

## Properties:														
| Name  | Type | Description
| ------------- | ------------- | ------------- 										
| startTimer | boolean | boolean for whether the start button was pushed.												
| stopTimer	| boolean |	boolean for whether the stop button was pushed.												
| interestName |	String |	Name of the User's Interest.												
| periodFreq |	int	| How frequent the user would like to practice their interest per period.												
| basePeriodSpan |	int |	How often the user wants to reset the period.												
| activityLength |	int |	How long the user wants to practice their interest per period.												
| numNotifications |	int |	The number of notifications the user would like tor receive on a daily basis.
| updateTimer |	int |	Updates the timer based on how much time remains.
| timer       | Timer | Instance of Timer API. 
														
## Functionality											
| Name  | Parameters | Return | Description
| ----------  | ---------- | --------- | -----------					
| editInterest() |	String interestName, int periodFreq, int basePeriodSpan, int activityLength, int numNotifications | none | Edits the interest to change any of the parameters.
| submitInterest() |	none | none	| submits the interest's information back to the user class.
| displayTimer() |	none(?) |	none |	Instantiates timer object specific to interest. 
| startTimer() |	boolean startTimer | none |	starts the timer for the interest. Also calls displayTime() and will do so until stopTimer() is called.	
| stopTimer() |	boolean stopTimer | none |	stops the timer and saves the progress.
| timerRunning() |	int updateTimer | none |	Continuously being reduced in seconds until 0 seconds remain or stopTimer() is called.
														
## Connections:
| Input or Output  | Function | Description
| ----------  | ---------- |  -----------							
| Output |	submitInterest() |	Submits the interest's updated settings to the user class.
| Output |      timerRunning()   |      Increments timer when running. 
| Input  |      startTimer()     |      Starts timer object when user clicks Start Activity button. 
| Input  |      stopTimer()      |      Stops timer object when user clicks stop Activity button. 
