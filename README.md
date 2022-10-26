# ElGamal_Public_Key_Cryptosystem
RSA (Rivest–Shamir–Adleman) is an asymmetric public-key cryptosystem that is widely used for secure data transmission.

In a public-key cryptosystem, the encryption key is **public** and distinct from the decryption key, which is kept **private**. 


## Idea of ElGamal

The idea of ElGamal is based on the difficulty of finding discrete logarithm in a cyclic group, that is even if we know $g^a$ and $g^k$, it is extremely difficult to compute $g^{ak}$.

**This is based on the Diffe-Hellman key exchange.**
## Working of ElGamal

### Generating the Keys
A prime number $p$ is chosen, along with a generator $G$, along with a random number $a$, which acts as the Private Key.

$A$ is computed with $G^a$ and the Public Key, consisting of $p$, $g$ and $A$ is created.

### Encrypting a message
The sender wants to send an encrypted message to the receiver, who has the public key $(p,g,A)$.

First, sender choses a random number, which is private key $b$. Then, using the public key of the receiver, $B$ is computed, which is $g^b$.

The sender then computes a **shared secret** $S$, which is $A^b( = g^{ab})$. The cipher $C$ is created by multiplying (by using modulus multiplication ideally) the message to $S$.

The encrypted message is sent to receiver as $(B, C)$.

### Decrypting a message
The receiver now has to decrypt the message, which was received as $(B,C)$.

Using the private key $a$, $B^a$ is computed, which is $g^{ab}$, creating the **shared secret** $S$. The receiver calculates the inverse of $S$, which is $S^{-1}$ and multiplies that (modularly) to $C$, computing the orignal message.

## Security

ElGamal is not a impenetrable cryptosystem and thus faces a few security threats:

- The security mainly depends on the properties of the underlying group $G$. [^1]
  - If Computational Diffie–Hellman assumption (CDH) holds in the underlying cyclic group $G$, then the encryption function is one-way.
  - If the Decisional Diffie–Hellman assumption (DDH) holds in $G$, then ElGamal achieves semantic security.
- This model is not secure under an attack model, based on the information gather from past ciphers.
[^1]: Please refer to [Elgamal Encryption Scheme](https://web.archive.org/web/20160722005050/https://crypto.cs.uiuc.edu/wiki/index.php/Elgamal_encryption_scheme) in the References for more information.

# References
1. https://web.archive.org/web/20160722005050/https://crypto.cs.uiuc.edu/wiki/index.php/Elgamal_encryption_scheme
2. https://en.wikipedia.org/wiki/ElGamal_encryption#Security
3. https://en.wikipedia.org/wiki/ElGamal_encryption#Security
4. https://mathstats.uncg.edu/sites/pauli/112/HTML/secelgamal.html


