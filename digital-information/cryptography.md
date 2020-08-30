# Cryptography

## Privacy Matters

Privacy is one of the greatest concerns in the Internet age, as more and more of our information is splashed across the web. To keep things private, we need ways to hide data from others.

* Credit card numbers
* Health records and information
* Passwords and PINs
* Bank account numbers
* Private communications

{% embed url="https://www.youtube.com/watch?v=x1yxOHG5IWk&list=PLUEYQSaHI9SKkvRjT-z1rbLI\_wLo-oMtu" %}



All of these things are personal, and should be kept private. But how? Cryptography!

### Encrypt and Decrypt

Encrypting data is the process by which we scramble the original data into a form unreadable to anyone who doesn't have the ability to unscramble and read it. Typically, you need a password or key to unscramble the data.

The scrambling process is called encryption, and the unscrambled process is call decryption.

#### How it Works

For now, we're going to gloss over the specifics. In general, though, you need a key to encrypt and decrypt data. You pass the raw data and the key to a function that produces the scrambled output.

To reverse the process, you pass the encrypted data and the key to another function that produces the original raw data.

## History of Cryptographic Algorithms

There are many, many cryptographic algorithms in use, and even more than are no longer used. After an encryption scheme has been broken \(via demonstrated weakness\), it quickly and understandably falls out of favor.

* Caesar Cipher

Julius Caesar used what became known as the Caesar Cipher to mask messages he sent to his generals. It was a simple shift cipher, and here's how it worked.

{% embed url="https://www.youtube.com/watch?v=aFoBfI4Evd8&list=PLUEYQSaHI9SKkvRjT-z1rbLI\_wLo-oMtu" %}

Using the regular English alphabet and a predetermined key, shift each letter by the key. For example, consider the following message.

_We will attack at dawn._

Suppose we use a key of 3. Each letter is shifted forward \(wrapping around back to the beginning of the alphabet if necessary\) by 3 letters.

_Zh eloo dwwdfn dw gdzq._

Shift _W_ by 3 letters and you get _Z_. Then, shift _e_ by 3 letters and you get _h_. So on and so forth. You would decrypt the message by shifting in the other direction.

The problems with this cipher is that it only works for alphabetic data, and it's pretty easy to crack it. There are only 26 possible keys to try and you'll figure it out.

## Modern Cryptography

Modern cryptography still shares some similarities with the Caesar Cipher.

* Uses a key to encrypt the data
* Very much based in mathematics.

There are some differences, though. Here are some of the major ones.

* The keys used are much, much larger.
* The mathematics is far more complex than shifting up or down the alphabet.

Using a computer to crack a Caesar Cipher \(with 26 possible keys\) will take under a second.

Using 40-bit keys used to be the industry standard. This resulted in over a trillion possible key values, but even this wasn't enough to keep the ever-increasing speed and computational power of computers at bay. Now, the industry standard is 256-bit keys. It would take trillions of years to brute-force every possible key value even with today's fastest computers. Try raising 2 to the 256th power. Pretty big number, right?

### Hard or Easy

The goal in cryptography is for the encryption scheme to be computationally _hard_ to crack \(such has trying every possible key\).

* An easy problem
  * As the input size grows, the time it takes to solve it increases at a reasonable rate.

An example would be finding the smallest element in an array. If you increase the array by 10 elements, you only need to check 10 more numbers.

* A hard problem
  * As the input size grows, the time it takes to solve it increases exponentially.

Brute-forcing every possibly key. If we increase the number of bits in the key by 1, the number of possible key values doubles \(think powers of 2\).

### Encryption Types

There is more than one type of encryption, as you might've guessed.

* Symmetric
* Asymmetric

In a symmetric encryption scheme, the same key is used to encrypt and decrypt the data. In an asymmetric encryption scheme, two keys are used. One key encrypts the data, while a different key decrypts it.

Asymmetric encryption is far more common because it is much more feasible with the number of Internet-connected devices.

#### Public Key Encryption

This is a form of asymmetric encryption, which uses two different keys for encrypting and decrypting.

With public key encryption, each party \(i.e., person or Internet-connected device\) has its own public key and private key. The public key is responsible for encrypting the data, while the private key is responsible for decrypting it. The public key \(as its name suggests\) is something you can share with others. The private key should never be shared with anyone else.

If I want to send my friend Patrick an encrypted messaged, I need to request Patrick's public key from him. I use Patrick's public key to encrypt the message before sending it to him. He then uses his private key to decrypt my message.

