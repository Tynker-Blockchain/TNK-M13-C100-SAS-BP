Check the Password
======================
In this activity, you will add the functionality to check the password when a user signs in to prevent the account from overriding the password. 
<img src= "https://s3.amazonaws.com/media-p.slid.es/uploads/1525749/images/10759135/C100AA2.gif" width = "100%" height = "50%">


Follow the given steps to complete this activity.


1. Prevent password override
* Open the file "wallet.py".


* Create a `wrongPassword` flag variable and set it to `False`.
`self.wrongPassword = False`
def addUser(self, username, password):
`ref = db.reference('users/'+ username + "/")`
* Create a userData variable to get the data inside the reference to user/username
`userData = ref.get()`
`print(userData)`
* Check if the userData is already present in db. 
`if(userData):`


* Set the username if the password entered by the user matches with the password in userData(db). 
`if userData.get('password') == password:`
    `self.username = username`
* Set self.wrongPassword to False, i.e. password is correct.
    `self.wrongPassword= False`
* Return True
    `return True`
`else:`
* Set self.wrongPassword to True if the password doesn't match.
print("Password does not match")
self.wrongPassword= True
return False
* If the userData is not available in the db, then add data in the db.
  
 * Set the username and password keys in the db along with updation of the current username and return `True` if userData is available.
```
ref.set({'username': username, 'password': password})
self.username = username
return True
```


* Save and run the code to check the output.
