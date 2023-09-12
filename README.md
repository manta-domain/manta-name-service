# Manta Name Service for Manta Pacific 
This document will help you incorporate .manta into your projects. In the document, available functions are examined by including web3.js and .manta name service in your project.


### Requirements
>If you are not actively using it in your project, you should install web3.js.

**NODE**
```
npm install web3
```

**YARN**
```
yarn add web3
```

**In the Browser**
```javascript
<script src="https://cdn.jsdelivr.net/npm/web3@latest/dist/web3.min.js"></script>
```
or
```javascript
<script src="https://unpkg.com/web3@latest/dist/web3.min.js"></script>
```

### Installation

**NODE**
```
npm i mantanameservice
```

**In the Browser**
```javascript
<script src="https://www.unpkg.com/mantanameservice@1.0.0/index.js"></script>
```


### Usage
First, we connect with the libraries.

```javascript
const web3 = new Web3(Web3.givenProvider)
// First create a web3js provider

const MANTAns = new MANTAns(web3)
// You are now ready for .manta
```

## GETS

**Primary Address (Ethereum Address to Manta Name)**

Returns the primary address registered to this address.
```javascript
MANTAns.primaryAddress("ETH_ADDRESS")
.then(function(result){
    console.log(result)
    // Returns the primary address registered to this address.
})
```

**Resolve Address  (Manta Name to Ethereum Address)**

Returns the resolved ethereum address of the .manta name.
```javascript
MANTAns.resolveAddress("name.manta").then(function(result){
    console.log(result)
    // Returns the resolved ethereum address of the .manta name.
})
```

**Address Owners**

Returns the domains owned by an address.
```javascript
MANTAns.addressOwners("ETH_ADDRESS").then(function(resultOwners){
	console.log(resultOwners)	
})
```  

**Last registered names**

Returns the last  registered .manta names
```javascript
MANTAns.lastAddresses(20).then(function(result){
    console.log(result)
    //Returns the last 10 registered .manta name
})
```

**Is this domain name taken ?**

Returns whether a domain name has been registered by another user.
```javascript
MANTAns.isTaken("manta").then(function(resultTaken){
    if (resultTaken>0) {
        //This domain name has been registered.
    } 
})
```


**Get Data**

Get domain name information.
```javascript
MANTAns.getData("name","data_name").then(function(result){
    console.log(result)
});
```


**Get Twitter Account**

Get Twitter account from .manta name.
```javascript
MANTAns.getTwitter(name).then(function(account_twitter){
     console.log(account_twitter)
})
```


**Get Instagram Account**

Get Instagram account from .manta name.
```javascript
MANTAns.getInstragram(name).then(function(account_instagram){
     console.log(account_instagram)
})
```

**Get Discord Account**

Get Discord account from .manta name.
```javascript
MANTAns.getDiscord(name).then(function(account_discord){
     console.log(account_discord)
})
```

**Get Telegram Account**

Get Telegram account from .manta name.
```javascript
MANTAns.getTelegram(name).then(function(account_telegram){
     console.log(account_telegram)
})
```

**Get URL**

Get URL from .manta name.
```javascript
MANTAns.getUrl(name).then(function(account_url){
     console.log(account_url)
})
```

**Get Email**

Get Email from .manta name.
```javascript
MANTAns.getEmail(name).then(function(account_email){
     console.log(account_email)
})
```


**Get Description**

Get Description from .manta name.
```javascript
MANTAns.getDescription(name).then(function(account_description){
     console.log(account_description)
})
```

**Get Avatar**

Get Avatar from .manta name.
```javascript
MANTAns.getKeywords(name).then(function(account_keywords){
     console.log(account_keywords)
})
```

## SETS

**Set New Primary Address**

Changes the primary address.
```javascript
MANTAns.setPrimaryAddress("name.manta","OWNER_ETH_ADDRESS").then(function(result){
    if (result['status']) {
     //Successful
     } else {
     //Failed
     }
})
```

**Set New Resolve Address**

Changes the resolve address.
```javascript
 MANTAns.setResolveAddress("name.manta","NEW_RESOLVE_ETH_ADDRESS", "OWNER_ETH_ADDRESS").then(function(result){
        if (result['status']) {
        //Successful
        } else {
        //Failed
        }
 })
```

**Register Domain**

Registers a new .manta address and returns the result.
```javascript
MANTAns.register("name.manta",YOUR_ETH_ADDRESS,"3000000000000000").then(function(result){
    if (result['status']) {
        // Registration Successful
    } else {
        // Registration Failed
    }
})
```


**Set Data**

It allows you to add data for the domain name you have.
```javascript
MANTAns.setData("name","data_type","data_value", "Owner_Eth_Address").then(function(result){
    if (result['status']) {
     //Successful
     //eq: data_name: twitter, data_value: twitter_account
     } else {
     //Failed
     }
})
```
