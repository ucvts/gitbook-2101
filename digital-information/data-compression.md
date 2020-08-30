# Data Compression

## Compress the Data

There is an inordinate amount of data in the world. In order to efficiently store it, we need to make it smaller. Enter, compression!

{% embed url="https://www.youtube.com/watch?v=jFZdD5hc\_OQ&list=PLUEYQSaHI9SKkvRjT-z1rbLI\_wLo-oMtu" %}

Compression is a process by which we can encode information using fewer bits than the original representation of the data.

We can use tried-and-true algorithms to compress our data, and then decompress it later when we need to use or view it. A process that guarantees that the data will be identical before compression and after decompression is called lossless compression.

### Reasons for Compressing Data

There are many reasons to compress data, most of which involve conserving storage space or increasing the speed of sending and receiving data.

* Save storage space \(which saves money\).
* Save time or bandwidth when transmitting data.
  * A compressed file means the network needs to send fewer bits.
* A trade-off between storage \(which is expensive and slow\) and computation \(which is fast and cheap\).
  * A phone doesn't have 300 GB of storage to store an uncompressed, raw movie.
  * A phone does, however, have the computational power to decompress and view that movie.

### How Does it Work?

Compression algorithms look for patterns in the raw data, and use a smaller placeholder to replace these patterns of information.

#### Run Length Encoding

An example of a compression algorithm that uses patterns and placeholders is called run length encoding. Consider the following string of text.

* _HAAAAAAHAAAAAA_

We can compress this by using the character and the number of times that character is repeated.

* _H1A6H1A6_

The original text has 14 characters \(times 8 bits per character\), which requires 112 bits to store. After the run length encoding, there are only 8 characters \(times 8 bits per character\). This requires only 64 bits.

{% embed url="https://www.youtube.com/watch?v=1tXvAJnBrrE&list=PLUEYQSaHI9SKkvRjT-z1rbLI\_wLo-oMtu" %}

We can compute the overall save savings using the following formula.

`spaceSaving = (1 - sizeOfOriginal / sizeOfCompressed) * 100`

Let's use this algorithm to compute the space saving for our compression of _HAAAAAAHAAAAAA_. The original required 112 bits, and the compressed required 64 bits.

`spaceSaving = (1 - 112 / 64) * 100 = 42.9` 

The compressed data is 42.9% smaller than the original.

#### Other Forms of Compression

Run length encoding is, of course, just one example. There are many compression techniques, and some work better with different types of data. Run length encoding works well with text that has many repeated characters. JPEG is a popular compression format for images.

The file extension indicates the compression technique that was used to compressed the data \(`.jpg`, `.zip`, `.tar`, etc.\). This is important because the decompression needs to match the compression technique.

## Lossy Compression

Believe it or not, you can throw away a lot of data \(specifically with images\) without any noticeable difference. The benefit of this is that using a lossy compression technique results in a significantly smaller file than the original \(a lot smaller than a file compressed in a lossless manner\).

{% embed url="https://www.youtube.com/watch?v=DeTYz7DYpgI&list=PLUEYQSaHI9SKkvRjT-z1rbLI\_wLo-oMtu" %}

The only drawback to lossy compression is the decompressed data isn't the same as the original. That being said, it's pretty close and the differences aren't noticeable.

