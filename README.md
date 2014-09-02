Nancy.Serialization.Jil
=======================

Implementations of the ISerialization and IBodyDeserializer interfaces, based on [Jil](https://github.com/kevin-montrose/Jil), for [Nancy](http://nancyfx.org). Because a little bit more [Performance](https://github.com/kevin-montrose/Jil/blob/master/README.md#benchmarks) never hurts.

## IMPORTANT

This does not work round-trip wise, yet. Currently only the ISerialization implementation works as I'm waiting for an [issue/feature for Jil to be added](https://github.com/kevin-montrose/Jil/issues/60) to one of the next releases. Once that is done, I'll publish a 1.0 release of this library.

## Usage

Start of by installing the `Nancy.Serialization.Jil` nuget package. When Nancy detects that the `JilSerializer` and `JilBodyDeserializer` types are available in the AppDomain of your application, it will assume you want to use them, rather than the default ones.

### Customization & Jil Options

By default [Jil's Default.Options](https://github.com/kevin-montrose/Jil#configuration) are used for both, Serialization and De-Serialization. If you want to change that behaviour, choose one of the many [Configuration Options](https://github.com/kevin-montrose/Jil/blob/master/README.md#configuration) available and change the Default one used like that:

```
    Nancy.Serialization.Jil.JilSerializer.Options = Options.ISO8601PrettyPrintNoHashing; // changes only the JilSerializer's Options
    Nancy.Serialization.Jil.JilBodyDeserializer.Options = Options.ISO8601PrettyPrintNoHashingIncludeInherited; // changes only the JilBodyDeserializer's Options
    // or
    Nancy.Serialization.Jil.JilSerializer.Options = Nancy.Serialization.Jil.JilBodyDeserializer.Options = Options.ISO8601PrettyPrintNoHashing; // changes both Options (that's usually what you'd like I guess)
```

## Limitations

As this library is based on [Jil](https://github.com/kevin-montrose/Jil), all its Features but also Limitations also apply here: .Net >= 4.5 is required, but even more so please take a close look at its [List of supported types](https://github.com/kevin-montrose/Jil/blob/master/README.md#supported-types) and how to [configure and tailor Jil](https://github.com/kevin-montrose/Jil/blob/master/README.md#configuration) to your specific environment and use case.

## Thanks

This is basically a 1:1: port of [Nancy.Serialization.JsonNet](https://github.com/NancyFx/Nancy.Serialization.JsonNet) but replacing the [Json.NET](http://json.codeplex.com/) parts with Jil. So thanks to Andreas Håkansson, Steven Robbins and the other original contributors.

Moreover thanks alot to [Kevin](https://github.com/kevin-montrose) for his awesome work on [Jil](https://github.com/kevin-montrose/Jil).


## Copyright

Copyright © 2014 Jörg Battermann

## License

Nancy.Serialization.Jil is licensed under [MIT](http://www.opensource.org/licenses/mit-license.php "Read more about the MIT license form"). Refer to [LICENSE.md](https://github.com/jbattermann/Nancy.Serialization.Jil/blob/master/LICENSE.md) for more information.
