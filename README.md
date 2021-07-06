IPinfo.io Client Libraries
==========================

This repo tracks our official client libraries and integrations.

Language Libraries
------------------

Official libraries for common programming languages, like PHP, Python etc.

See [GUIDELINES](GUIDELINES.md) for implementation guidelines.

| Language          | Status   | Link                                              | Package Manager                                            | Published Link                                                                            |
|-------------------|----------|---------------------------------------------------|------------------------------------------------------------|-------------------------------------------------------------------------------------------|
| Javascript (Node) | Released | [ipinfo/node](https://github.com/ipinfo/node)     | [npmjs](https://npmjs.com)                                 | [node-ipinfo](https://npmjs.com/package/node-ipinfo)                                      |
| Java              | Ready    | [ipinfo/java](https://github.com/ipinfo/java)     | [Maven Central](https://search.maven.org/)                 | [Snapshot](https://oss.sonatype.org/content/repositories/snapshots/io/ipinfo/ipinfo-api/) |
| Python            | Released | [ipinfo/python](https://github.com/ipinfo/python) | [PyPI](https://pypi.org/)                                  | [ipinfo](https://pypi.org/project/ipinfo/)                                                |
| C#                | Released | [ipinfo/csharp](https://github.com/ipinfo/csharp) | [Nuget](https://www.nuget.org/)                            | [IpInfo](https://www.nuget.org/packages/IpInfo/)                                   |
| PHP               | Released | [ipinfo/php](https://github.com/ipinfo/php)       | [Composer](https://packagist.org/)                         | [ipinfo/ipinfo](https://packagist.org/packages/ipinfo/ipinfo)                             |
| Ruby              | Released | [ipinfo/ruby](https://github.com/ipinfo/ruby)     | [Ruby Gems](https://rubygems.org/)                         | [IPinfo](https://rubygems.org/gems/IPinfo)                                                |
| Go                | Released | [ipinfo/go](https://github.com/ipinfo/go)         | [GitHub](https://golang.org/doc/code.html#ImportingRemote) | [ipinfo/go](https://github.com/ipinfo/go)                                             |
| R                 | Proposed |                                                   | [CRAN](https://cran.r-project.org/)                        |                                                                                           |
| Perl              | Released | [ipinfo/perl](https://github.com/ipinfo/perl)     | [CPAN](https://pause.perl.org/pause/query)                 | [Geo-IPinfo](https://metacpan.org/release/Geo-IPinfo)                                     |
| Erlang            | Released | [ipinfo/erlang](https://github.com/ipinfo/erlang) | [hex.pm](https://hex.pm)                                   | [ipinfo](https://hex.pm/packages/ipinfo)                                                                                          |
| Rust              | Released | [ipinfo/rust](https://github.com/ipinfo/rust)     | [crates.io](https://crates.io)                             | [ipinfo](https://crates.io/crates/ipinfo)                                                 |

Framework Libraries
-------------------

Official libraries for common frameworks. These libraries should use the
official lanaguge library as a dependency, so for example the Django library
should use the Python library.

In the framework libraries we can assume more about the developer's use case,
and we probably have access to more information, such as a HTTP request object.
We can therefore implement additional functionality that doesn't make sense in
the core language library. This includes bot filtering (not sending requests to
our API if the user agent belongs to a "bot").

The framework libraries should make it *as simple as possible* to use our API.
For example, ideally only a few lines of code would be required to get IPinfo
data for everyone accessing your Ruby site.

| Framework        | Status   | Link                                                | Published Links                                                             |
|------------------|----------|-----------------------------------------------------|-----------------------------------------------------------------------------|
| Express (NodeJS) | Proposed |                                                     |                                                                             |
| Spring (Java)    | Ready    | [ipinfo/spring](https://github.com/ipinfo/spring)   |                                                                             |
| Laravel (PHP)    | Released | [ipinfo/laravel](https://github.com/ipinfo/laravel) | [ipinfo/ipinfolaravel](https://packagist.org/packages/ipinfo/ipinfolaravel) |
| Django (Python)  | Released | [ipinfo/django](https://github.com/ipinfo/django)   | [ipinfo-django](https://pypi.org/project/ipinfo-django/)                    |
| Rails (Ruby)     | Released | [ipinfo/rails](https://github.com/ipinfo/rails)     | [ipinfo-rails](https://rubygems.org/gems/ipinfo-rails)                      |

README
------

For many developers our libraries will be their first contact with our service -
they'll never have been to our website, or read anything else about us.
Therefore it's important to do a good job of explaining the service to them in
the library documentation. See our standard [HEADER](README_HEADER.md) and
[FOOTER](README_FOOTER.md) that should be added to every README.

The libraries are also a great opportunity for new developers to discover us,
so we should make sure we include relevant search terms in our description and
summary text, and keywords if applicable.
