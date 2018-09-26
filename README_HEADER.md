# ![image](https://ipinfo.io/static/favicon.ico?v2) IPinfo $LANGUAGE Client Library

This is the official $LANGUAGE client library for the [IPinfo.io](https://ipinfo.io) IP address API, allowing you to lookup your own IP address, or get any of the following details for an IP:
 - IP geolocation (city, region, country, postalcode, latitude and longitude)
 - ASN details (ISP or network operator, associated domain name, and type, such as business, hosting or company)
 - Company details (the name and domain of the business that uses the IP address)
 - Carrier details (the name of the mobile carrier and MNC and MCC for that carrier if the IP is used exclusively for mobile traffic)



### Getting Started

You'll need an IPinfo API access token, which you can get by singing up for a free account at [https://ipinfo.io/signup](https://ipinfo.io/signup?ref=lib-$LANGUAGE). 

The free plan is limited to 1,000 requests a day, and doesn't include some of the data fields such as IP type and company data. To enable all the data fields and additional request volumes see [https://ipinfo.io/pricing](https://ipinfo.io/pricing?ref=lib-$LANGUAGE)

#### Installation

*Installation instructions, eg:*

```npm install ipinfo```

#### Quick Start

*Include a simple example of initializing it with an access token, and 2 quick examples, something like...*

```
require 'ipinfo'
ip = ipinfo(process.env.TOKEN)
console.log ip.my_ip()
# => 127.0.0.1
ip = ipinfo(process.env.TOKEN)
details = console.log ip.details('8.8.8.8')
console.log details.country
# => United States
console.log details.company
# => {...}
```
