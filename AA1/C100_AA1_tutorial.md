Switch the Testnet
======================
In this activity, you will learn to add an option to switch the testnet type.
<img src= "https://s3.amazonaws.com/media-p.slid.es/uploads/1525749/images/10759127/C100AA1.gif" width = "100%" height = "50%">


Follow the given steps to complete this activity.


1. Switch testnet
* Open the file "wallet.py".


* Create the `web3` object and set it to `None`.
`web3 = None`
 
* Define the `setweb3()` function to pass the selected testnet using `Web3.HTTPProvider()`. 
```
def setweb3(url):
    global web3
    web3 = Web3(Web3.HTTPProvider(url))
```


* Open the file "app.py".


* Create the `isTestnetSelected` flag variable that tells if testnet is selected or not and set it to `False` initially.
`isTestnetSelected = False`


* Create a `testneturl` string to pass the address of the selected testnet and set it to an empty string initially.
`testneturl = ""`


* Create a `/selectTestnet` path to select the testnet on startup using `@app.route()`.
`@app.route("/selectTestnet", methods= ["GET", "POST"])`


2. Define `selectTestnet()` function
* Access `account`, `allAccounts`, `myWallet` and `isTestnetSelected` as `global`.
```
def selectTestnet(): 
    global account, allAccounts, myWallet, isTestnetSelected
```
   
* Access the `testnet` argument sent on the path and store it in the `selectedTestnet` variable. 
```
    selectedTestnet = request.form.get("testnet")
    print(selectedTestnet)
```


* Check the value of the `selectedTestnet` variable, if it's `"sepolia" or `"goerli"`. 
```
    if selectedTestnet == "sepolia":
```


* Set the `testneturl` to the respective URLs and set the `isTestnetSelected` to `True`. 
```
    testneturl = "https://sepolia.infura.io/v3/5f29b851d6984f498f84032f3ccae759"
    isTestnetSelected = True
```


* Call the `setweb3()` function and pass the `testneturl` to set the Sepolia testnet.
`setweb3(testneturl)`
    
* Else, set the `testneturl` to the Goerli API with key and and set the isTestnetSelected to `True`. 
```
    else:
    testneturl = "https://goerli.infura.io/v3/5f29b851d6984f498f84032f3ccae759"
    isTestnetSelected = True
```


* Call the `setweb3()` function and pass the `testneturl` to set the goerli testnet.
```
    setweb3(testneturl)
    return redirect("/")
```


* Save and run the code to check the output.
