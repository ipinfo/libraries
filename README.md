# IPinfo.io Client Libraries

This repo tracks our official client libraries and integrations.

## Language Libraries

Official libraries for common programming languages, like PHP, Python etc.

See [GUIDELINES](GUIDELINES.md) for implementation guidelines.

| Language   | Status       | Link                                                    | Package Manager                                                                          | Published Link                                                                            |
| ---------- | ------------ | ------------------------------------------------------- | ---------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------- |
| Javascript | In progress  |                                                         | [npmjs](https://npmjs.com)                                                               |                                                                                           |
| Java       | Ready        | [ipinfo/java](https://github.com/ipinfo/java)           | [Maven Central](https://search.maven.org/)                                               | [Snapshot](https://oss.sonatype.org/content/repositories/snapshots/io/ipinfo/ipinfo-api/) |
| Python     | Released     | [ipinfo/python](https://github.com/ipinfo/python)       | [PyPI](https://pypi.org/)                                                                | [ipinfo-wrapper](https://pypi.org/project/ipinfo-wrapper/)                                          |
| C#         | Proposed     |                                                         | [Nuget](https://www.nuget.org/)                                                          |                                                                                           |
| PHP        | In Progress     | [ipinfo/php](https://github.com/ipinfo/php)             | [Composer](https://packagist.org/)                                                       |                                                                                           |                                                   |                                                         
| Ruby       | Needs update | [ipinfo/ruby](https://github.com/ipinfo/ruby)           | [Ruby Gems](https://rubygems.org/)                                                       |                                                                                           |
| Go         | In progress  | [ipinfo/go-ipinfo](https://github.com/ipinfo/go-ipinfo) | [GitHub](         https://golang.org/doc/code.html#remote)                                                                          |                                                                                           |
| R          | Proposed     |                                                         | [CRAN](https://cran.r-project.org/)                                            |                                                                                           |
| Perl       | Needs update | [ipinfo/perl](https://github.com/ipinfo/perl)           | [CPAN](https://pause.perl.org/pause/query) |  [Geo-IPinfo](https://metacpan.org/release/Geo-IPinfo) |                                                                                           |


## Framework Libraries

Official libraries for common frameworks. These libraries should use the official lanaguge library as a dependency, so for example the Django library should use the Python library.

In the framework libraries we can assume more about the developer's use case, and we probably have access to more information, such as a HTTP request object. We can therefore implement additional functionality that 
doesn't make sense in the core language library. This includes bot filtering (not sending requests to our API if the user agent belongs to a "bot"). 

The framework libraries should make it *as simple as possible* to use our API. For example, ideally only a few lines of code would be required to get IPinfo data for everyone accessing your Ruby site.

| Framework                      | Status      | Link                                              | Published Links |
| ------------------------------ | ----------- | ------------------------------------------------- | --------------- |
| Express  (NodeJS - Javascript) | Proposed    |                                                   |                 |
| Spring  (Java)                 | Ready       | [ipinfo/spring](https://github.com/ipinfo/spring) |                 |
| Larvel (PHP)                   | None        |                                                   |                 |
| Django (Python)                | In progress | [ipinfo/Django](https://github.com/ipinfo/django) |                 |
| Rails (Ruby)                |   |  |                 |


## README

For many developers our libraries will be their first contact with our service - they'll never have been to our website, or read anything else about us. Therefore it's important to do a good job of explaining the service 
to them in the library documentation. See our standard [HEADER](README_HEADER.md) and [FOOTER](README_FOOTER.md) that should be added to every README.

The libraries are also a great opportunity for new developers to discover us, so we should make sure we include relevant search terms in our description and summary text, and keywords if applicable.

