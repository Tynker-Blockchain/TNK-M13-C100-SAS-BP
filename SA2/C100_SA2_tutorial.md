Add a Live Server and Mine Ethereum
======================
In this activity, you will learn to add a live server and mine ethereum using Sepolia.
<img src= "https://s3.amazonaws.com/media-p.slid.es/uploads/1525749/images/10727227/pasted-from-clipboard.png" width = "100%" height = "50%">


Follow the given steps to complete this activity.


1. Add a Live Server
* Create an account and login to Infura to get the URL of the live server.
`https://app.infura.io/`


* Replace the Ganache URL in the code with the url of the live Sepolia server.
`"sepoliaUrl = "https://sepolia.infura.io/v3/7cc0d838c6304750ab8f26877179b0b3"`


* Pass `sepoliaUrl` instead of `ganacheUrl` to connect to the live server. 
```
web3 = Web3(Web3.HTTPProvider(sepoliaUrl))
```


Note: Make sure you create new wallet accounts on the Sepolia server.


* Open the link “`https://sepolia-faucet.pk910.de/#/”` and add the wallet address to start the mining process in the Sepolia faucet.

Note: Also, you can use the website to send ethers.

* Save and run the code to check the output.
