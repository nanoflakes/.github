# Nanoflakes

Specification of unique ID numbers generated locally or from workers, based on Twitter Snowflakes.

## A Nanoflake

A nanoflake is a 64-bit unsigned integer, which contains the following information:

- 41 bits for `time`
   - The ID creation time, in milliseconds, with a custom epoch. (up to 69 years)
- 10 bits for `generator`
   - Supports up to 1024 standalone ID generators
- 12 bits for `sequence`
   - A generator can generate up to 4096 IDs per millisecond.

The only difference between Twitter Snowflakes and a Nanoflakes, in fact, is Twitter splitting `generator` in `datacenter` (5 bits) and `worker` (5 bits), while Nanoflakes treat the entire 10 bits as a single `generator` ID.

### Encoding

This specification suggests encoding nanoflakes as a string, since [some languages doesn't support 64-bit integers](https://tqdev.com/2016-javascript-cannot-handle-64-bit-integers).

We recommend encoding as either as a decimal number, as a hexadecimal number, or using [Base36](https://en.wikipedia.org/wiki/Base36) to encoding (which fit the largest 64-bit unsigned in 13 characters!)
