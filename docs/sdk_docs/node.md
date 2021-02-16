
## Installation

### For [Node.js](https://nodejs.org/)

#### npm

Install it via:

```shell
npm install mimespost --save
```


## Send Email Example
```javascript

var Mimepost = require('mimepost');

var defaultClient = Mimepost.ApiClient.instance;

// Configure API key authorization: api_key
var api_key = defaultClient.authentications['api_key'];
api_key.apiKey = 'YOUR_API_KEY';
// Uncomment the following line to set a prefix for the API key, e.g. "Token" (defaults to null)
//api_key.apiKeyPrefix = 'Token';

var apiInstance = new MimePost.EmailsApi();

var body = new MimePost.Email(); // Email | Single Email object 
var to = new MimePost.EmailTo() // To Email | Single To Email object

to.email = "TO_EMAIL" 


body.html = "<h1>Html Code OR Text</h1>" 
body.from_email = "FROM_EMAIL"
body.from_name = "FROM_NAME"
body.subject = "SUBJECT"
body.to = [to]


var callback = function(error, data, response) {
  if (error) {
    console.error(error);
  } else {
    console.log('API called successfully. Returned data: ' + response.text);
  }
};
apiInstance.sendEmail(body, callback);

```

# Read about 
* [How to create an API token for MimePost](https://mimepost.com/blog/how-to-create-an-api-token-for-mimepost/)

## Documentation for API Endpointsd

* [Read More About API Endpoints](https://github.com/mimepost/mimepost-node/blob/main/README.md)

