<img align="right" src="https://github.com/nanoflakes/.github/raw/master/profile/LOGO.png" height="200" width="200" alt="Nanoflakes Logo">

# Nanoflakes

"Nanoflakes" is a specification for unique identifiers which can be
generated locally or from a remote server.  The specification is
designed to be simple and easy to implement, and to be compatible with
Twitter's Snowflake algorithm, which Nanoflakes is based on.

## What's a Nanoflake?

A nanoflake is a 64-bit signed integer, and supports 1024 unique
ID generators, each being able to generate 4096 (2^12) unique IDs
per millisecond, and with 41-bit timestamps.

The main and only difference between a nanoflake and a Twitter Snowflake
is that nanoflakes merges Twitter's 5-bit `datacenter` ID and 5-bit `worker`
ID into a single 10-bit `generator` ID.

Additionally, the specification suggests encoding nanoflakes using base-36,
in order to fit the largest possible nanoflake into a 13-character string.

The official, full specification can be found [here](https://github.com/nanoflakes/spec).

## Implementations

Nanoflakes have reference implementations in the following languages:

* [Java](https://github.com/nanoflakes/nanoflakes-java)
* [Kotlin](https://github.com/nanoflakes/nanoflakes-kotlin)
* [TypeScript](https://github.com/nanoflakes/nanoflakes-js)

You're more than welcome to implement nanoflakes in other languages!
If you do, please open a pull request to add your implementation to this
list.

## License

The official Nanoflakes specification is licensed under the [CCO 1.0 Universal](https://creativecommons.org/publicdomain/zero/1.0/) license.

The reference implementations are licensed under the [MIT License](https://opensource.org/licenses/MIT).

## Contributing

Contributions are welcome!  Please open an issue or pull request to
suggest changes to the specification or to add a new implementation.
