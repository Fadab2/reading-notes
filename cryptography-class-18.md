# Cryptography

* Cryptography is the practice and studying of techniques for secure communication in the presence of adversarial behavior.

### Encryption

* One of the earliest encryption techniques is the Caesar Cipher, invented by Julius Caesar more than two thousand years ago to communicate messages to his allies.
* The Caesar Cipher idea was very simple and it hides the real message by substituting or shifting letters with different letters. For example: SECRET MEETING AT THE PALACE becomes YKIXKZ SKKZOTM GZ ZNK VGRGIK in this ciphar the message is shifted by 6 letters in such a way that A becomes G and S becomes Y etc.
* Another example is ALEXANDRIA SOON becomes GRKDGTJXOG YUUT

### Decryption
* As Caesar used to shift by a certain amount of letters that is agreed upon, the receiver only had to shift the letters back to their original position to read the correct message.
* For example if Caesar a sends FURVV WKH UXELFRQ and it was shifted by 3 letters the receiver will shift it back by 3 so it becomes CROSS THE RUBICON

### Cracking the cipher
* Cracking is trying to break the encryption without know the code.
* The techniques someone uses to break the cipher could be:
    * frequency analysis because some letters used more than others it makes it possible to narrow guesses and give hints.
    * known plaintext if the interceptor already knew some part of the plaintext they can find it easy to crack the rest. , * brute force is to try every possible way to break the code.

## Symmetric encryption techniques

* A symmetric encryption is any technique where the same key is used to both encrypt and decrypt the data

### Vigenère Cipher
* Was invented in 1500 by a French cryptologists.
* Was considered very strong at that time.
* It was considered unbreakable until 1868.
* It used an entire word instead of a letter as a shift key. For example to encrypt the world V E R S A I L L E S using the word C H E E S E C H E E we get X L V W S M N S I W. 
* To decrypt Vigenere cipher we are provided with the shift key word and just check the rows of the corresponding letter using the key word letter and then find the top of the column letter.
* Breaking Vigenère Cipher was impossible at that time if you do not know the keyword because you have to try every word which is impossible to do manually.

### Modern ciphers
* With computers and software, ciphers became very advanced and many techniques were developed to secure communication and data transmission. They are hard to break even with the most powerful computers int he world.
* AES-128 is a standard block cipher that is approved and used for secure file transfer.
* Because the key is 128 bits long we have 340,000,000,000,000,000,000,000,000,000,000,000,000 possible keys.
* In addition, the AES-128 applies additional 10 mathematical operations for each bit of the key.
* The fastest computer would still take 500 trillion years to try every possible 128-bit key!

<br />

## References

[Encryption, decryption, and cracking](https://www.khanacademy.org/computing/computers-and-internet/xcae6f4a7ff015e7d:online-data-security/xcae6f4a7ff015e7d:data-encryption-techniques/a/encryption-decryption-and-code-cracking)


<br />

## [<-- Back](README.md)
