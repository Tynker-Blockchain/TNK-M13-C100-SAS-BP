Add and Fetch Transactions from the Database
======================
In this activity, you will learn to add and fetch the live Ethereum transactions from the database.
<img src= "https://s3.amazonaws.com/media-p.slid.es/uploads/1525749/images/10732638/pasted-from-clipboard.png" width = "100%" height = "50%">


Follow the given steps to complete this activity.


1. Add and fetch the transactions from the database 
* Open the file `app.py`.
* Comment the code for sender form inputs within `addTransactionHash()`, `makeTransaction()` and `getTransactions()` function.
```
# sender = request.form.get("senderAddress")
if(type(account) == dict):
    #if(sender == account['address']):
    else:
    #if(sender == account.address):
.
.
. 
```


* Store the private key and address within `makeTransactions()` function.
```
if(type(account) == dict):
    privateKey = account['privateKey']
    sender= account['address']
else:
    privateKey = account.privateKey
    sender= account.address
```
* Open the file "`wallet.py`".
* Add the list of transactions to the database by creating a database reference using `db.reference()` and setting the values.
```
ref = db.reference('transactions/' + tnxHash)
ref.set({
    "from":senderAddress,
    "to":receiverAddress,
    "tnxHash":tnxHash,
    "amount":amount,
    "time": time.time()
  })
```
Note: Comment the previous written code.


* Display the sent and received transactions in an order for the current user from the database and store them using `order_by_child()`, `equal_to()`, `get()` and `values()` method.
```
asSender = list(db.reference('transactions/').order_by_child('from').equal_to(address).get().values())
asReceiver = list(db.reference('transactions/').order_by_child('to').equal_to(address).get().values())
return  asSender + asReceiver
```
Note: Create a rule in the Firebase database as below by navigating to Realtime Database -> Rules.

* Save and run the code to check the output.
