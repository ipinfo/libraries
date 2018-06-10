The following are the general guideliens when writing wrappers, contact @aaomidi for more clarifiations:

- All the information in the [ip full response](https://ipinfo.io/developers/responses#full-response) and the [asn full response](https://ipinfo.io/developers/asn) must be included in the code.
- They should be accessible using named variables (assuming the language has them).
- The IP field should preferebly be an internal data structure of the language. That makes the wrapper be more cohesive to the language and allows the developer use functionality exposed by that data structure.
- The wrapper has the responsibility to include country code -> country name translations. The wrapper should ship with an en_US language file for this purpose and load it by default. It should also include a system to use different language files.
- The en_US language file will be in JSON.
- The language file parser in the wrapper should at least have support decoding JSON. However, other formats such as csv and yaml could be supported as well.
- The format of the language file is included [here](en_US.json)
- If the target language of the wrapper includes an http client api, the wrapper should make it's best effort to provide a method to filter out traffic that's from a bot.
- The API wrapper should provide a customizable caching system. This should include a default implementation for the caching system, however the end developer should be able to override that with either no caching or their own customized caching system.