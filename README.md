# Overview

Welcome to fana protocol! Here, you can find an easy-to-use Telegram scraping API that will help you to get the most relevant information from Telegram channels.

### What Is this API for
Using our API, you can get the latest posts from any telegram channel in seconds. This makes it easy for you to create an application or website that displays the latest posts from your favorite channels.


# 🎉 Whats is New  🎉
Thank you for using Fana API. Yesterday we have released Fana API v1.1 filled with new features and bug fixes based on your feedback which has been very helpful! 

### Bug fix
- ✅ Data Sanitization on `Get Message` Route
- ⚒️ Changed all Get Requests from `Body` to `Query Params`
- 🚗 Increased Response Speed by optimising Scraping time 
- 👋 User Friendly Documentation 

### New Feateure
- ➕ Added Post Limit functionality

## For more Information contact us
Feel free to contact us if you run into problems or even if you would like to give us some advice on how to make our products better.

> If you have any quetions you can contact us [https://birukendris2020.t.me/](https://birukendris2020.t.me/)

----

# Get Started

To start the process, you must create an account  [https://fana.ruqad.com/](https://fana.ruqad.com/).

1. Open the link
2. Go through the registration process
3. Check your Email for verification email 
4. After you finish the verifying your account, We will send you **YOUR API Key**.

> If you have any problem while Registering, join our support group on
> telegram.  If everything goes as planned, **Read How to use the API
> Documentation**

------
## How to use Fana Protocol Api

If you get to this point you are registered and you have your API KEY.

> If you don't have your api-key check out the **Get Started Documentation.**

- Base URL is : **https://fanaprotocol.herokuapp.com/api/v1/** 

## Passing you API-KEY

All your requests must have an `token: abcdefg-hijklmn-opqrstu-vwxyzbt` in the request header. To test you api you can send a `Get` request to our  [https://fanaprotocol.herokuapp.com/api/v1/](https://fanaprotocol.herokuapp.com/api/v1/)



# End-Points


## Get Info

### End Point
`get`  **/channel/get_info**

### Request Headers
| token | abcdefg-hijklmn-opqrstu-vwxyzbt  |
|--|--|

### Query Params

| username | @channel_username  | 
| -- | -- |

### Example

    curl --location --request GET 'https://fanaprotocol.herokuapp.com/api/v1/channel/get_info?username=@codenight_info' \
    
    --header 'token: abcdefg-hijklmn-opqrstu-vwxyzbt'


### Response Body

    {
    	"title": "CodeNight Info",
    	"about": "Info channel for Codenight \n\nCommunity of 🇪🇹 developers to showcase their projects\n\nJoin the discussion group @CodeNight\n \n▶️ Project playlist - https://bit.ly/codenight-yt",
    	"username": "CodeNight_Info",
    	"isVerified": false,
    	"isSam": false,
    	"isFake": false,
    	"totalMember": 437,
    	"totalAdmin": null,
    	"onlineMember": 0,
    	"totalMessage": 0,
    	"photoId": "6023732645738952249"
    }


### Error Message

| Error-Code | Error-Message   |                                          
|------------|---------------------------------------------------------------|
| E-101 | `api_key` is missing from header | 
| E-102 | `api_key` is not valid | 
| E-103 | Request limit reached, check https://fanaprotocol.ruqad.com/pricing |
|	E-104 | Channel `username` is not provided on the body request |
| E-105 | Channel dose not exist |
| E-106 | Username is not a channel |
| E-107 | Can't get channel messages |

----


## Get Message

### End Point
`get`  **/channel/get_message**

### Request Headers
| token | abcdefg-hijklmn-opqrstu-vwxyzbt  |
|--|--|

### Query Params
| Key | Example  |  Default| Is Requierd
| -- | -- | -- |  -- |
| username | @channel_username | - 	| True
|Limit | From 1 To 20 | 20 | False |


### Example

    curl --location --request GET 'https://fanaprotocol.herokuapp.com/api/v1/channel/get_message?username=codenight_info&limit=3' \
    
    --header 'token: abcdefg-hijklmn-opqrstu-vwxyzbt'


### Response Body

    [
      { <<message_data>>}
      { <<message_data>>}
      { <<message_data>>}
    ]




### Error Message

| Error-Code | Error-Message   |                                          
|------------|---------------------------------------------------------------|
| E-101 | `api_key` is missing from header | 
| E-102 | `api_key` is not valid | 
| E-103 | Request limit reached, check https://fanaprotocol.ruqad.com/pricing |
|	E-104 | Channel `username` is not provided on the body request |
| E-105 | Channel dose not exist |
| E-106 | Username is not a channel |
| E-107 | Can't get channel messages |

-----


##  For more Information contact us
> if you have any quetions you can contact us [https://birukendris2020.t.me/](https://birukendris2020.t.me/)
