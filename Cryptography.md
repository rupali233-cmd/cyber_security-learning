# Cryptography

## What is Cryptography?

**Meaning:** Cryptography is the process of securing information by converting it into a form that only authorized users can read.

**Purpose:**
- Protect data from unauthorized access.
- Ensure confidentiality, integrity, authentication, and non-repudiation.

**Used In:**
- Online Banking
- HTTPS Websites
- VPN
- Email Security
- Digital Signatures

---

# Encryption

## Meaning

Encryption is the process of converting **Plaintext (readable data)** into **Ciphertext (unreadable data)** using an encryption algorithm and a key.

## Purpose
- Protect sensitive information.
- Prevent unauthorized access.

## Process

Plaintext → Encryption Algorithm + Key → Ciphertext

## Example

Plaintext:
```
Password123
```

Encrypted:
```
X7@kL91#mP
```

*(Example only)*

---

# Decryption

## Meaning

Decryption is the process of converting **Ciphertext** back into **Plaintext** using the correct key.

## Purpose
- Allows authorized users to read encrypted data.

## Process

Ciphertext → Decryption Key → Plaintext

---

# Encoding

## Meaning

Encoding is the process of converting data into another format so it can be stored or transmitted properly.

## Purpose
- Data compatibility.
- Data transmission.
- Data storage.

## Important

Encoding **does NOT provide security.**

## Example

Text:
```
Hello
```

Base64 Encoded:
```
SGVsbG8=
```

---

# Hashing

## Meaning

Hashing converts data into a fixed-length hash value.

## Purpose
- Verify data integrity.
- Store passwords securely.
- Detect file modifications.

## Important
- One-way process.
- Cannot be reversed.

## Example

Input:
```
Hello
```

SHA-256 Hash:
```
185f8db32271fe25f561a6fc938b2e264306ec304eda518007d1764826381969
```

---


---

# Symmetric Encryption

## Meaning

Symmetric Encryption uses **one single key** for both encryption and decryption.

## Process

Plaintext → Secret Key → Ciphertext

Ciphertext → Same Secret Key → Plaintext

## Advantages
- Fast
- Efficient
- Suitable for large amounts of data

## Disadvantages
- Key sharing is difficult.
- If the key is leaked, data can be compromised.

## Examples
- AES
- DES
- 3DES
- Blowfish

---

# Asymmetric Encryption

## Meaning

Asymmetric Encryption uses **two different keys**.

- Public Key (Encryption)
- Private Key (Decryption)

## Process

Plaintext → Public Key → Ciphertext

Ciphertext → Private Key → Plaintext

## Advantages
- More secure.
- No need to share the private key.

## Disadvantages
- Slower than symmetric encryption.

## Examples
- RSA
- ECC
- DSA

---


---

# Common Hashing Algorithms

| Algorithm | Hash Length |
|------------|------------|
| MD5 | 128 bits |
| SHA-1 | 160 bits |
| SHA-256 | 256 bits |
| SHA-512 | 512 bits |

---

# Real World Examples

### Encryption
- WhatsApp Messages
- HTTPS Websites
- VPN

### Encoding
- Base64 Email Attachments
- URL Encoding

### Hashing
- Password Storage
- File Integrity Checks
- Digital Fingerprints

---

# Interview Questions

### What is Cryptography?
Securing information by converting it into a format that unauthorized users cannot understand.

### What is Encryption?
Converts plaintext into ciphertext using a key.

### What is Decryption?
Converts ciphertext back into plaintext using the correct key.

### What is Encoding?
Converts data into another format for storage or transmission. It is **not used for security.**

### What is Hashing?
Converts data into a fixed-length hash value to verify integrity.

### Difference between Encryption and Hashing?
Encryption can be reversed using a key, while hashing is a one-way process and cannot be reversed.

### Difference between Symmetric and Asymmetric Encryption?
Symmetric uses one key for both encryption and decryption, whereas asymmetric uses a public key for encryption and a private key for decryption.

---

# Quick Revision

- Cryptography → Protects data.
- Encryption → Plaintext → Ciphertext.
- Decryption → Ciphertext → Plaintext.
- Encoding → Changes data format (No Security).
- Hashing → One-way conversion for integrity.
- Symmetric Encryption → One Secret Key.
- Asymmetric Encryption → Public Key + Private Key.
- HTTPS → Uses Encryption.
- Passwords → Stored using Hashing.
