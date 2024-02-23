# ElGamal Public Key Cryptosystem
The ElGamal public key cryptosystem is an asymmetric encryption algorithm that provides secure communication over an insecure channel. Named after its inventor, Taher ElGamal, it is widely used for key exchange and digital signatures.

## Key Components
### 1. Key Generation
ElGamal uses a pair of keys: a public key and a private key.
- **Public Key (PK):** (g, p, y)
  - g: a generator of a finite cyclic group
  - p: a large prime number
  - y: (g^x) mod p, where x is the private key

- **Private Key (SK):**
  - x: a random integer, 1 < x < p-1

### 2. Encryption
The sender uses the recipient's public key to encrypt the message.
1. **Select Random Number (k):**
   - k is a random integer, 1 < k < p-1, relatively prime to p-1.

2. **Compute Temporary Values:**
   - a = (g^k) mod p
   - b = (y^k * message) mod p

3. **Transmit the Cipher (a, b):**
   - The ciphertext is (a, b).

### 3. Decryption
The recipient uses their private key to decrypt the received ciphertext.
1. **Compute the Shared Secret:**
   - s = (a^x) mod p

2. **Compute the Inverse of s:**
   - s_inv = multiplicative_inverse(s, p)

3. **Recover the Original Message:**
   - message = (b * s_inv) mod p
