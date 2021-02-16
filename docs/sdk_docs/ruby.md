## Installation

### For [Ruby](https://www.ruby-lang.org/en)

Via RubyGems

```shell
gem install mimepost
```

## Send Email Example

Example on how to send an simple email:

```ruby
# Load the gem
require 'mimepost'

# Setup authorization
Mimepost.configure do |config|
  # Configure API key authorization: api_key
  config.api_key['X-Auth-Token'] = 'YOUR API KEY'
  # Uncomment the following line to set a prefix for the API key, e.g. 'Bearer' (defaults to nil)
  #config.api_key_prefix['X-Auth-Token'] = 'Bearer'
end

api_instance = Mimepost::EmailsApi.new

body = Mimepost::Email.new
body.html           = '<p>Email send using MimePost ruby sdk</p>'
body.subject        = 'Email send using MimePost ruby sdk'
body.from_email     = 'from@example.com'
body.from_name      = 'Mail Sender'

to                  = Mimepost::EmailTo.new
to.email            = 'to@example.com'

body.to             = [to]


begin
  #Get account profile details
  result = api_instance.send_email(body)
  p result
rescue Mimepost::ApiError => e
  puts "Exception when calling EmailsApi->send_email: #{e}"
end

```

# Read about 
* [How to create an API token for MimePost](https://mimepost.com/blog/how-to-create-an-api-token-for-mimepost/)

## Documentation for API Endpointsd

* [Read More About API Endpoints](https://github.com/mimepost/mimepost-ruby/blob/main/README.md)
