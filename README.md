• Technologies used:
- Neo4j graph database
- Flask python framework
- Networks to visualize graph 

• App service:
- Registration form to collect information from users like (firstname, email,…)
- Create graph database for register users.
- Graph database contains relationships between users and this address and 
company name.
- Every user has status (yellow, green, red), and you can search by username 
to know user status.
- Can change status for specific user.
- If you change status to red app automatically change all users in the same 
address or in same company and have green status to yellow status.
- If you register new user with green status and there is user with red status 
in same address or same company app automatically change register user 
status to yellow.
- Can visualize a graph for all user in same company.
- Can visualize a graph for all user in same address.

• Design Overview:
- This is three pages in app (registration page, search page, change state 
page).
- Registration page: implemented in registerAuthStaff() method 
and it have three parts:
1- collect data from form.
2- check user status and convert it if it green and there is user has 
red status in same address or company.
 Report
3- add collected data to graph database (Neo4j).

- search page: implemented in searchForStatus() method and 
it have three parts:
1- save all data related to user you need to search for in list and 
send this list to html to display the list as table.
2- Get all users have the same address from database and create a graph 
to visualize user’s data have same address using networks package in 
python and save this graph in image and send this image to html to 
display it.
3- Get all users have the same company from database and create a graph 
to visualize user’s data have same company using networks package in 
python and save this graph in image and send this image to html to 
display it.

- Change status page: implemented in changeStatu() 
method and it have two parts:
1- If new status of specified user is red, it will firstly get all 
users have the same user address or company and 
green status and change their status to yellow finally 
change specified user status to red.
2- If new status of specified user is green or yellow just 
change their status to green or yellow.
