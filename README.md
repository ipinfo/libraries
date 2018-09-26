# IPinfo.io Client Libraries

This repo tracks our official client libraries and integrations.

## Language Libraries

Official libraries for common programming languages, like PHP, Python etc.

See [GUIDELINES](GUIDELINES.md) for implementation guidelines.

*Add a table of existing libraries, with links to the repo and the package manager version*

## Framework Libraries

Official libraries for common frameworks. These libraries should use the official lanaguge library as a dependency, so for example the Django library should use the Python library.

In the framework libraries we can assume more about the developer's use case, and we probably have access to more information, such as a HTTP request object. We can therefore implement additional functionality that 
doesn't make sense in the core language library. This includes bot filtering (not sending requests to our API if the user agent belongs to a "bot"). 

The framework libraries should make it *as simple as possible* to use our API. For example, ideally only a few lines of code would be required to get IPinfo data for everyone accessing your Ruby site.

## README

For many developers our libraries will be their first contact with our service - they'll never have been to our website, or read anything else about us. Therefore it's important to do a good job of explaining the service 
to them in the library documentation. See our standard [HEADER](README_HEADER.md) and [FOOTER](README_FOOTER.md) that should be added to every README.

The libraries are also a great opportunity for new developers to discover us, so we should make sure we include relevant search terms in our description and summary text, and keywords if applicable.

