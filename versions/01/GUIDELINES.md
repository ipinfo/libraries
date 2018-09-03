# Guidelines 1.0

This document contains guidelines for both official and unofficial wrappers. Contact @aaomidi if you have questions.

## Programming methodology

### Libraries

If the target language provides an http client API, you should try to preferably use that. We want to keep the libraries small and to the point.

### User Agent

The wrapper should send all requests with the following user agent format:

```
IPinfoClient/Language/Version
```


For example:

```
IPinfoClient/Go/1.0
```

### Error Communication

The error that's most relevant to the developer is when the user has hit it's limits. We are communicated this by the API returning HTTP Error 429. We need to catch this and return this to the user according to the conventions of the language.

For example, in Go the error would be returned by returning it directly as a result of the call. In Java, the error would be thrown as a custom exception.

If there are other errors returned by the API, pass it up to the caller so they can handle it. Do not silence/ignore these errors.

## Included responses

All the information in the [ip full response](https://ipinfo.io/developers/responses#full-response) and the [asn full response](https://ipinfo.io/developers/asn) must be included in the code.

All of these objects must have a named access to them. For example in a C-Like language:

`ipresponse.getCountry();`

In a language with structures instead of classes, omitting the getter is recommended (unless the language conventions say otherwise):

`ipresponse.Country;`

### Fields

#### IP

In the responses, the IP field should be preferably represented by an `ip` type in the language the wrapper is being written in. Essentially follow the language conventions on how to represent IPs in memory. 

#### Country

The country response by the API is the ISO2 code of the country. The API must provide a well documented and reasonable method to convert this country code into a country name.

This conversion should extend to other languages as well. A sample lookup dictionary for ISO2 -> Country Name is included [here](en_US.json).

The wrapper must give the developer the ability to provide their own language files.

The english language file must be included and loaded by default.

## Caching

Caching will allow the developer to conserve their API calls if multiple API calls with the same request has been made.

### Location

The caching location should at least include in-memory storage. 

### Length

The default caching length should be 24 hours per element with a 5000 limit. This should be configurable by the developer.

### Extensibility

To implement caching, use the strategy design pattern. Allow the developer full control in implementing whatever caching strategy they would like. This means that if they want to use carrier pigeons as a caching strategy they should be able to.

## License

All libraries should be released with an [Apache License 2.0](https://choosealicense.com/licenses/apache-2.0/).

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

You can develop more sophisticated versions of this but be careful about false positives.
