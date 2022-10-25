# Overview

Welcome to fana protocol! Here, you can find an easy-to-use Telegram scraping API that will help you to get the most relevant information from Telegram channels.

## What Is this API for
By using our API, you can get the latest posts from any telegram channel in seconds. This can be very useful if you want to create an application or website that displays the latest posts from your favorite telegram channels.


## Get Started

To start the process, you must create an account  [https://fana.ruqad.com/](https://fana.ruqad.com/).

1. Open the link
2. Go through the registration process
3. Check your Email for verification email 
4. After you finish the verifying your account, We will send you **YOUR API Key**.

> If you have any problem while Registering, join our support group on
> telegram.  If everything goes as planned, **Read How to use the API
> Documentation**

------
# How to use Fana Protocol Api

If you get to this point you are registered and you have your API KEY.

> If you don't have your api-key check out the **Get Started Documentation.**

## Base URL
All you requests must be sent to the following Base URL is : **https://fanaprotocol.herokuapp.com/api/v1/** 

## Passing you API-KEY

All your requests must have an `api-key: XXXX-XXXXXXXX-XXXXXXXX-XXXXXXXX` in the request header. To test you api you can send a `Get` request to our  [https://fanaprotocol.herokuapp.com/api/v1/](https://fanaprotocol.herokuapp.com/api/v1/)

**JS Fetch Example** 

    let myHeaders  =  new  Headers();
    myHeaders.append("api-key", "asdjsgfuyaihajkskjahskdhashdkasjkhsjk");
    
    let requestOptions  = {
	    method: 'GET',
	    headers: myHeaders,
	    redirect: 'follow'
    };
    fetch("https://fanaprotocol.herokuapp.com/api/v1/channel/get_info/", requestOptions)
	    .then(response  =>  response.text())
	    .then(result  =>  console.log(result))
	    .catch(error  =>  console.log('error', error));
	    

**cURL Example**

    curl --location --request GET 'https://fanaprotocol.herokuapp.com/api/v1/channel/get_info/' \
        
    --header 'api-key: XXXX-XXXXXXXX-XXXXXXXX-XXXXXXXX'

> if you have any quetions you can contact us [https://birukendris2020.t.me/](https://birukendris2020.t.me/)
-----


# End-Points


## `Get` : /channel/get_info

By using this api end point you can get infromation about the specifyed username. For every request the channel `username :` must be specified in the body request.

### Key Option
| Option		| Type 		| Requierd 	| On			| Value  													|
|-----------|---------|-----------|---------|---------------------------------|
| api_key 	| String | True 			| HEADER 	| abcdefg-hijklmn-opqrstu-vwxyzbt	|
| username 	| String | True 			| BODY  	| @username   \|\|  username      | 

### Request Example

**cURL Example**

    curl --location --request GET ' https://fanaprotocol.herokuapp.com/api/v1//channel/get_info' \
    --header 'api_key: abcdefg-hijklmn-opqrstu-vwxyzab' \
    --header 'Content-Type: application/json' \
    --data-raw '{
        "username" : "@username "
    }'

**Node JS Axios Example**

    var axios = require('axios');
    var data = JSON.stringify({
      "username": "@username "
    });
    
    var config = {
      method: 'get',
      url: ' https://fanaprotocol.herokuapp.com/api/v1/channel/get_info',
      headers: { 
        'api_key': 'abcdefg-abcdefg-asdasdd-asdaasd', 
        'Content-Type': 'application/json
      },
      data : data
    };
    
    axios(config)
    .then(function (response) {
      console.log(JSON.stringify(response.data));
    })
    .catch(function (error) {
      console.log(error);
    });



### Expected Responces

> if everything is woking as expected you will see the following response

    {
    	"title": "Code Night",
    	"about": "",
    	"username": "Code Night",
    	"isVerified": false,
    	"isScam": false,
    	"isFake": false,
    	"totalMember": 92,
    	"totalAdmin": 3,
    	"onlineMember": 0,
    	"totalMessage": 1925,
    	"photoId": "5958379920851842859"
    }


--------------
### Error Message

| Error-Code | Error-Message   |                                          
|------------|---------------------------------------------------------------|
| E-101 | `api_key` is missing from header | 
| E-102 | `api_key` is not valid | 
| E-103 | Request limit reached, check https://fanaprotocol.ruqad.com/pricing |
|	E-104 | Channel `username` is not provided on the body request |
| E-105 | Channel dose not exist |
| E-106 | Can't get channel messages |




## `Get` : /channel/get_message

By using this api end point you can ger the last 10 message from the specified channel username. For every request the channel `username` must be specified in the body request.

---------

### Key Option
| Option | Type | Requierd | On | Value | Default Value |
|--------|------|----------|----|-------|---------------|
| api_key | String | True | HEADER | abcdefg-hijklmn-opqrstu-vwxyzbt | "" |
| username | String 	| True | BODY | @username ** OR ** username| "" |
| limit | Number | True | BODY | 1 - 100 | 10 | 

---------

### Request Example

**cURL Example**

    curl --location --request GET 'https://fanaprotocol.herokuapp.com/api/v1/channel/get_info' \
    --header 'api_key: abcdefg-hijklmn-opqrstu-vwxyzab' \
    --header 'Content-Type: application/json' \
    --data-raw '{
        "username" : "@username "
    }'

---------
**Node JS Axios Example**

    var axios = require('axios');
    var data = JSON.stringify({
      "username": "@username"
    });
    
    var config = {
      method: 'get',
      url: 'https://fanaprotocol.herokuapp.com/api/v1/channel/get_info',
      headers: { 
        'api_key': 'ODIPT4Q-M3YUIPQ-S6JI7VY-BIP632Q', 
        'Content-Type': 'application/json'
      },
      data : data
    };
    
    axios(config)
    .then(function (response) {
      console.log(JSON.stringify(response.data));
    })
    .catch(function (error) {
      console.log(error);
    });

---------

### Expected Responces

> if everything is woking as expected you will see the following response

    {
    	"flags" : 0
    	"inexact" : false
    	"pts" :	1185
    	"count" : 10 
    	"offsetIdOffset: ""	,
    	"messages" :	[…],
    	"chats" :  […],
    	"users " :   […],
    	"className" : "messages.ChannelMessages"
    }


## Error Message

| Error-Code 	| Error-Message   |                                          
|-------------|---------------------------------------------------------------|
| E-101 			| `api_key` is missing from header 															| 
| E-102 			| `api_key` is not valid 																				| 
| E-103 			| Request limit reached, check https://fanaprotocol.ruqad.com/pricing 																																			|
|	E-104 			| Channel `username` is not provided on the body request 				|
| E-105 			| Channel dose not exist 																				|
| E-106 			| Can't get channel messages 																		|



##  For more Information contact us
> if you have any quetions you can contact us [https://birukendris2020.t.me/](https://birukendris2020.t.me/)
