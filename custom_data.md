## Custom Data

### Adding custom data to your messages

There will be a time when you will be required to add custom data to your email messages. Example, you want to add your own ID to every messages. MimePost provides a way to add those data. 

### Ways to attach your Custom Data
You can add your custom key & value pairs to each email messages using:

1. SMTP headers

2. HTTP API

#### SMTP Headers

You can add your custom data using "X-Vars" SMTP headers, like in below example:

```
X-Vars: {"user_id":"ea1fd1fd-8a4e-4e14-a8ad-ff06c6420ea1", "invoice_id": "3339d083-7cc9-4d2a-9c77-9b6e862c27b9"}

```

NOTE: The value of the header should be in a valid JSON format.

#### API

You can add *vars* hash in the JSON body of your HTTP API call, like in below example:

```
POST https://api.mimepost.com/v1/emails/

{
...
	"vars": {
	    "user_id": "ea1fd1fd-8a4e-4e14-a8ad-ff06c6420ea1",
	    "invoice_id": "3339d083-7cc9-4d2a-9c77-9b6e862c27b9"
	}
}
```

### Ways to retreive your custom data

#### Webhook

The MimePost will pass your custom data in every event of webhook call, like below example


**Delivered event Webhook call**

![Webhook Event Sample](images/custom-data-vars.png)

#### Front-end & API

Your custom data won't be available from our front-end or from API, this is because we have No-data policy. As we do not store any user data, so you can not search your custom varaibles using our front-end (like emaillogs) or any get email api.


#### Email Messages Source

The custom data will be available in your email message source code, like any other MIME headers.



### Limits

1. You should not use multiple X-Vars headers in SMTP 

2. Do not use more than 10 key value fields

3. Total length of all the values should not be more than 255 characters


