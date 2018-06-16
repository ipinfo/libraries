# Guidelines 1.0

The following are the general guideliens when writing wrappers, contact @aaomidi for more clarifiations:

## Programming methodology

### Libraries

If the target language provides an http client API, you should try to preferebly use that. We want to keep the libraries small and to the point.

### User Agent

The wrapper should send all requests with the following user agent format:

```
IPInfoClient/Vendor/Language/Version
```

Where the Vendor is the github username (if applicable) of the developer of the wrapper.

For example:

```
Official library:
IPInfoClient/IPInfo/GoLang/1.0

User library with a github username:
IPInfoClient/aaomidi/Java/2.0

User library without a github username: 
IPInfoClient/not_applicable/Python3/1.0
```

### Error Communication

HTTP Error 429 tells the developer that their key has run out of its quota.

You need to process and communicate this error in a special payload to the developer. All other errors must also be communicated to the developer.

For example, in Java you can use a custom RuntimeException telling the user their request failed.

## Included responses

All the information in the [ip full response](https://ipinfo.io/developers/responses#full-response) and the [asn full response](https://ipinfo.io/developers/asn) must be included in the code.

All of these objects must have a named access to them. For example in a C-Like language:

`ipresponse.getCountry();`

In a language with structures instead of classes, omitting the getter is recommended:

`ipresponse.Country;`

### Fields

#### IP

In the responses, the IP field should be repressnted using a standard IP definition. Preferrebly this standard definition should be something native to the programming language itself.

#### Country

The country response by the API is the ISO2 code of the country. The API must provide a well documented and resonable method to convert this country code into a country name.

This conversion should extend to other languages as well. A sample lookup dictionary for ISO2 -> Country Name is included [here](en_US.json).

The wrapper must give the developer the ability to provide their own language files.

The english language file must be included and loaded by default.

## Caching

Caching will allow the developer to conserve their API calls if multiple API calls with the same request has been made.

### Location

The caching location should at least include in-memory storage. Other options such as redis could be provided.

### Length

The default caching length should be 1 minute.

## Extra Functionality

### Bot Detection

The library should provide a middleware to detect if the traffic is coming from a suspected bot or a user.

An example of doing this would be to check the user-agent of a request:

``` Javascript
function isBot(userAgent) {
    if (userAgent.match(/bot|spider/i)) {
        return true;
    }
    return false;
}

```

You can develop more sophisticated versions of this but becareful about false positives.
