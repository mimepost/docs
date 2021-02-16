
## Installation

### For [Python](https://www.python.org/)


## Requirements.

Python 2.7 and 3.4+

## Installation & Usage

### pip install

Installation for Python 3.4 & below

```sh
pip3 install mimepost
```

Installation for Python 2.7 & below

```sh
pip install mimepost
```

Install directly from Github

```sh
pip install git+https://github.com/mimepost/mimepost-python.git
```
(you may need to run `pip` with root permission: `sudo pip install git+https://github.com/mimepost/mimepost-python.git`)


### Setuptools

Install via [Setuptools](http://pypi.python.org/pypi/setuptools).

```sh
python setup.py install --user
```
(or `sudo python setup.py install` to install the package for all users)

### Import the package

Then import the package:
```python
import MimePost
```


## Send Email Example

Please follow the [installation procedure](#installation--usage) and then run the following:

```python
from __future__ import print_function
import time
import MimePost
from MimePost.rest import ApiException
from pprint import pprint

# Configure API key authorization: api_key
configuration = MimePost.Configuration()
configuration.api_key['X-Auth-Token'] = 'YOUR_API_KEY'
# Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
# configuration.api_key_prefix['X-Auth-Token'] = 'Bearer'

# create an instance of the API class
api_instance = MimePost.EmailsApi(MimePost.ApiClient(configuration))

to_email     = MimePost.EmailTo(email = "to@example.com");

body = MimePost.Email(
    subject     =   "Test email sent using MimePost Python SDK",
    from_email  =   "from@example.com",
    html        =   "<p>This is a body of the test email sent using MimePost Python SDK</p>",
    to          =   [to_email],
) # Email | Single Email object 

try:
    # Send email
    api_response = api_instance.send_email(body)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling EmailsApi->send_email: %s\n" % e)

```


# Read about 
* [How to create an API token for MimePost](https://mimepost.com/blog/how-to-create-an-api-token-for-mimepost/)

## Documentation for API Endpointsd

* [Read More About API Endpoints](https://github.com/mimepost/mimepost-python/blob/master/README.md)
