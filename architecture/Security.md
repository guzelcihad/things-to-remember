## Symmetric Key Encryption
- Encryption and decryption is achieved by same key.
- The key available in both client and server
- Symmetric key is efficient yet there is a question. How server will trust the clients to be able to share the key?
this is where public key cryp. comes in.

## Public Key Encryption
- Also called as asymmetric key enc. or public-private key  enc.
- There are two keys public and private. We enc. text with public key and only the private key holder
can see the data. It is valid for opposite.
- We achieve privacy(confidentiality), authentication

## Secure Network Communication
- When client wants to get data from server through https, it first request from web server
- Web server sends its public key
- Client generates a symmetric key from that public key and send it to server
- Server dec. it using its private key. This way server holds client keys
- Even if one attackers can achieve this sym. key, it can nor decr. because it doesn't have private key
![alt text](images/86.PNG)

Questions:<br>
Why we use symm. key
> symm. key algo. is very fast comparing to asym. algo.

Sym. key has drawback because its not secure to exchange it. But we have overcome that limitation by using public and private key combination

## Some Considerations
How clients know that it communicates with the right server. How can we guarantee that, server identity?
> With certificate

## Hashing
Another building block for cryptography algorithms
![alt text](images/87.PNG)

Importan concepts of hashing
- Its one way algorithm, means that if we hash password we can not get back the original input even we know hash function.
- Even if we change small thing in input like one character, output will be completely different
- SHA-2 commonly used