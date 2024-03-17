# ElGamal Encryption Scheme

This README provides an overview of the ElGamal encryption scheme implemented in the provided Jupyter notebook. The ElGamal encryption scheme is a public-key cryptosystem that is used for secure communication over insecure channels. It is based on the Diffie-Hellman key exchange and provides semantic security, meaning that an attacker cannot gain any information about the plaintext from the ciphertext.

## Overview

The ElGamal encryption scheme consists of two main components:

1. **Key Generation**: This involves generating a public key and a private key. The public key is used to encrypt messages, while the private key is used to decrypt messages.

2. **Encryption and Decryption**: Messages are encrypted using the public key and can only be decrypted using the corresponding private key.

## Implementation Details

The implementation in the provided Jupyter notebook includes the following steps:

### Key Generation

1. A safe prime `p` is generated. This  number is used as the basis for the encryption and decryption process.

2. The public key and private key are generated using the `key_generation` function. The public key consists of a pair of numbers, while the private key is a single number.

### Encryption

1. A message is generated as a random integer between 1 and `p`.

2. The message is encrypted using the `encrypt` function, which takes the message and the public key as input. The encrypted message, or ciphertext, is the result of this function.

### Decryption

1. The encrypted message (ciphertext) is decrypted using the `decrypt` function, which takes the ciphertext and the private key as input. The decrypted message is the result of this function.

## Example Usage

The notebook demonstrates the encryption and decryption process for a series of messages. For each message:

1. A random message is generated.
2. The message is encrypted using the public key.
3. The encrypted message is decrypted using the private key.
4. The original and decrypted messages are printed for comparison.

## Conclusion

The ElGamal encryption scheme provides a secure method for encrypting and decrypting messages over insecure channels. By using a public key for encryption and a private key for decryption, it ensures that only the intended recipient can decrypt the message. This README provides a brief overview of the implementation details and usage of the ElGamal encryption scheme in the provided Jupyter notebook.

## Hash Function

The hash function plays a crucial role in the ElGamal encryption scheme, providing a way to generate a fixed-size output (hash) from an input of any size. This is particularly useful in the context of digital signatures and message integrity verification.

### Implementation

The hash function used in this implementation is based on a cryptographic hash function that operates in the group Zp*. It calculates the hash of a message (a, b) using the formula H(a, b) = g^a * h^b mod p, where:

- `p` is a large prime number.
- `g` is a generator of the group Zp*.
- `h` is a fixed element in the group Zp*.
- `a` and `b` are the components of the message.

The function `is_generator(g, p)` checks if `g` is a generator of the group Zp*, ensuring that the chosen generator can generate all elements of the group. The function `find_generator(p)` searches for a suitable generator `g` in the range [2, p-1].

The `hash(a, b, details)` function calculates the hash of a message (a, b) using the provided details (p, g, h). It uses the modular exponentiation operation to efficiently compute the hash.

### Usage

The hash function is used to generate a hash value for a message, which can then be used for various purposes, such as verifying the integrity of a message or creating digital signatures. The hash function ensures that even small changes in the input message result in a significantly different hash output, making it suitable for cryptographic applications.

### Example

An example of using the hash function is provided in the Jupyter notebook, demonstrating how to generate a hash for a pair of random integers (a, b) and how the hash changes with different inputs.

## Authors
- Zohar Simhon
- Matan Weiss