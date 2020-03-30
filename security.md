### RSA
1. **Symmetric vs Asymmetric encryption**. [packetlife](http://packetlife.net/blog/2010/nov/23/symmetric-asymmetric-encryption-hashing/) 
    1. *Symmetric encryption* may also be referred to as shared key or shared secret encryption. In symmetric encryption, a single key is used both to encrypt and decrypt traffic. 
    1. *Asymmetric encryption* is also known as public-key cryptography. Asymmetric encryption differs from symmetric encryption primarily in that two keys are used: one for encryption and one for decryption. The most common asymmetric encryption algorithm is RSA. 
1. **Asymmetric Encryption vs Asymmetric Signing**. [stackoverflow](https://stackoverflow.com/a/454069)
    1. When encrypting, you use their public key to write message and they use their private key to read it. 
    1. When signing, you use your private key to write message's signature, and they use your public key to check if it's really yours. 
1. **How Asymmetric Signing works?** [stackexchange](https://crypto.stackexchange.com/q/9896) 
    1. If I have a message that I want to sign, I don't sign the message itself but I create a hash of it and then sign that hash by using my private key
    1. The signature gets attached to the message and both are transferred to the recipient
    1. The recipient recalculates the hash of the message and then uses my public key to verify the signature he received 

### JWT
-

### HTTPS [stackoverflow](https://stackoverflow.com/a/39183636)
**Hybrid cryptosystem** algorithm which uses a public-key mechanism for key exchange (such as Diffie-Hellman) and a symmetric-key mechanism for data encapsulation [wiki](https://en.wikipedia.org/wiki/Hybrid_cryptosystem)

- Website owner first generates a **public key** and **private key**, keeping the private key secret. He gives a CSR file (Certificate Signing Request) and his public key to the CA (Certificate Authorities).
- CA creates a **personal certificate** based on CSR including domain name, owner name, expiry date, serial no. etc and also adds an encrypted text (= digital signature) to the certificate and finally encrypts the whole certificate with the public key of the server and sends it back to the website owner.
- This **personal certificate** is then decrypted with the private key of the website owner and finally, he installs it on the website.

- Establishing secured connection requires 2 steps - **Certificate validation** and **Session Key exchanging**
- **Certificate validation**: server sends the Certificate with Public Key -> client validates the Certificate trying decrypt digital signature using Root-Certificates and get a public key (browsers come with a pre-installed list of public keys from all the major CA’s).
- **Key exchanging**: client creates 2 copies of **Session Key** -> client sends one copy of Session Key ecrypted by servers' Public Key back to the server -> server decrypts Session Key using its Private Key -> client and server use this Session Key to encrypt-decrypt request data


