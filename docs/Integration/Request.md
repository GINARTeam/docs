---
id: request_number
sidebar_label: Request Number
title: Request Number
---

After passing authentication, you can request secure random numbers from GINAR’s system through the GINAR API. First, you need to initialize your request.
## API initialize
* API URL: 
> https://api.ginar.io/rng/initialize/ **{contribute_number}**
* Method: ``GET``
* Parameters:
	* **contibute_number**:  An arbitrary number that the user contributes to the public blockchain, generating random numbers. Each contributed number from users is a random entropy that affects the random number messages users should get for their sessions.
		* _type_: **string** (required)
		* _constraint_: string length in 1..50
* Return: list (1024 entries) of hex-string ticket Id along with Serial number that can be used as input to the API Generate. This ticket Id is kept in the server until it is used.
* Sample request: ```https://api.ginar.io/rng/initialize/0FFA158E185C42C971FB73B4B03EE28D5D921571```
* Sample response:
```
[
    {
        "serialNumber": "462-1574331364154-1",
        "ticketId": "d40b57134f7fbb21568c50827d17634dd5ca890abd2c19e8455b7bb1bca9e20c"
    },
    {
        "serialNumber": "462-1574331364154-2",
        "ticketId": "b750b9849912e300d87c12adaf6a6ca75ef107ba18ad887b387368ea567716f9"
    },
    ...
]
```
## API Generate
* API URL:
> https://api.ginar.io/rng/generate/ **{ticketId}**
* Method: ``POST``
* Parameters:
	* **ticketId**: a valid ticket Id
		* _type_: **string** (required)
		* _constraint_: 256-bit hex-string
* Body:
	* **userData**: custom data of requester for each request
		* _type_: **json** (optional)
		* _constraint_: size 128 bytes
* Return:  a JSON string
	* **usedTimestamp**: the time (GMT) for generating random number from GINAR system with ticketId.
	* **beacon**: the random number as a hex string
		* _type_: **string** (256-bit hex-string)
	* **signature**: a short digital signature to ensure the result is undeniably coming from GINAR.
	
* Sample request: 
``` 
https://api.ginar.io/rng/generate/4f0be1540f958247f71ad78b47674b80507017d6ba137fdd68e813bc080f3a68
```
``Sample body:``
```
{
	"gameId": "a47897b7-cce8-4bf9-94cd-83471d6ff0ba",
	"roomId": "18",
}
```

* Sample response:
```
{
    "usedTimestamp": 1574331609173,
    "beacon": "70d8659abec694eae3afc8fa33070641b12d6cc9c993b63ae53dde404cd32523",
    "signature": "0xea25fb13aac41cd719537875f05e98d7d4d2b221b208d5955abe3cf05df89db467c3f44c2d356b37da6e4b9ade0d70b9c0f36f0af388122ac8e6a20ef05109411c"
}
 ```
