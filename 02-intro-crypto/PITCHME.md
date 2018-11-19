
# Day 2: Fundamentals of cryptography

---

@ul

- Alice, Bob, and Eve
- Basics of encryption algorithms, key exchange, and cryptosystems
- Keeping track of what's secret, and from whom
- Encryption vs. hashing, strong vs. weak, fast vs. slow
- What does it take to attack encryption?

@ulend

---

#### Intro: Alice, Bob, Eve

---

(TK A,B,E slides)

---

#### Symmetric encryption (private key cryptography)

@ul

- Example: Alice password-protects a file and emails it to Bob
    - She has to transfer the password "out of band" (over the phone, text message etc.)
- Requires a trusted communication channel to share the encryption key
- Doesn't work for establishing trusted sessions with arbitrary partners over the internet

@ulend

---

#### Asymmetric encryption (public key cryptography)

@ul

- Much harder than symmetric encryption (and usually slower)
- Each party has a *keypair* consisting of a *private key* and *public key*
- Plaintext is encrypted using the other party's public key
- Anything encrypted with a given public key can only be decrypted with the corresponding private key
- *Still* requires some means of verifying that you're getting the right public key

@ulend

---

#### What are these keys, anyway?

- There are lots of good explanations of keypair generation, but without going into detail:
- The RSA cryptosystem takes advantage of the fact that large numbers are hard to factor, especially if their factors are large
- The public key and private key are generated together using a random seed value

---

#### Example: TLS workflow for HTTPS connection

![https](img/diagram-https.png)

---

#### Digital signatures

- You can also encrypt a message with your private key
- Only the corresponding public key can decrypt the message
- If you have a known public key, you can prove you signed something by encrypting it with your private key
- The receiver decrypts it with your unique public key

#### Server-side and client-side encryption

---

#### Hashing

**Hash function**: A function that takes variable-length input (the *message*) and returns fixed-length output (the hash or *digest*). 

```bash
$ echo '1' | md5
b026324c6904b2a9cb4b88d6d61c81d1
$ echo 'Hello world' | md5
f0ef7081e1539ac00ef5b761b4fb01b3
$ curl -s http://www.textfiles.com/etext/FICTION/mobydick | md5
3123669b027112a39dc9848b3801b516
```

---

#### Cryptographic hashing

Hash functions that are useful for cryptography have certain properties:

@ul

- Deterministic: the same input always produces the same hash value
- Infeasible to reverse: it should not be possible to find a message that returns a given hash value
- Infeasible to find *hash collisions*, two messages that have the same hash
- Similar input messages should produce uncorrelated hash values (small changes to a message should result in wildly different hashes)

@ulend

---

#### Uses for hashing

- Password checking: a hash of the password is stored, not the password itself
- Integrity checking: instead of comparing large files, compare their hashes
- Digital signatures: the message digest is signed with a private key

---

#### Encryption vs. hashing

Encryption is *information-preserving* and *reversible*

Hashing is *information-destroying* and (in principle) *irreversible*

---

#### Hashes are used wrong all the time

- Some common hashes like md5 are too fast
- GPUs are making hash checking many orders of magnitude faster
- Common hash functions (e.g., md5) don't include salting, making parallelization more effective
- This becomes a huge avenue of attack. Come back next time