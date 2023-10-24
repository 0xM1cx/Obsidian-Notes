## Features

-  Allows users to typing a message with a limit of 300 characters, length not final.
- The site will not ask the user any information e.g. email, name, number, etc. This is to maintain the anonymity of the users. 
- End Devices are tracked via cookies. This is to enable them view their past confession. 
- (TBD) Users will be prompted to allow some browser features to be used e.g. Camera and Location.
- (TBD) When ever a user submits a confession it will automatically be sent on our FB page for approval to be posted on the page. 
- There is a specific Public page where submissions can be viewed. 
- There will be a statistics page that will allow admins to view the statistics related to messages submitted every day, week, month, year. 

## Tools
> An mga tools dire pa final. Mag vovote pa kita kun anu an gamiton.
### Front-End
- HTML
- CSS and/or Bootstrap
- JS(React) or vanilla

### Back-End
- PHP(Laravel), Python(Django, Flask) 
- MySQL or Sqlite or MongoDb
- Meta API
## Website Parts
### Front-End
1. Submission Page Consists of:
	- Box for User Message in the center of the page.
	- Long vertical Box below the message box where the user can see his/her past submitted confessions. 
	- (TBD) Allow for Dark and light Mode. 
	- Colors will be cyan, while and blue or EVSU colors. 
2. Public Viewing of submission Page Consists of:
	- Boxes for messages will be situated at the center of the page. 
	- Each box will contain the message and the date and time that it was posted. 
### Back-End
- Each post will be automatically be posted on the public submission page. 
- We will utilize 2 servers and use load balancing to service the site. 
- Every message submitted will be sent to the database which will be tied to a cookie and a sequential ID. 