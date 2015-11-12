#To run:

(in app directory)

```
http-server
```

``` 
nodemon server.js
```

open in browser: 

```
http://localhost:8080
```


#API

all endpoints return an object with a success key (true or false) and in the case of an error, a message key that includes the error message

legend:
method /endpoint  
expects: (in request data)  
returns: fields other than success and message

```
// example return object
 {
	success: true,
	profile: {	
		name: 'Stan Lee',
		likes: 'cameos',
		favColor: 'yellow',
		friends: ['Charles', 'Logan', 'Bruce']
	}
```

####Find a User
post /api/profiles  
expects: name (string)  
returns: profile (object)  

####Delete a User
delete /api/profiles/:id  
expects: n/a (in params)  
returns: deleted (user document that was deleted)  

####Search friends
post /api/searchFriends  
expects: query (string)  
returns: friends (array)  

```
friends: ['Larry', 'Irene', 'Nate']
```

####Add Friend
put /api/addFriend  
expects: myId, addId (mongo _ids)  
returns: profile (user profile with new friend added)  

####Get 2nd connections
post /api/getFriendsFriends  
expects: friendId, myId (myId optional to filter out self from 2nd connections)  
returns: friends (array of 2nd connections)  

####Unfriend
put /api/deleteFriend  
expects: myId, deleteId  
returns: profile (user profile with friend removed)  

####All Users
get /api/allUsers  
expects: n/a  
returns: users (array of all users)  

---



Black Diamond

sign up sign in
gets all those with that name and can select one or create new

on client
do not allow create new with existing names

exclude yourself from 2nd connections