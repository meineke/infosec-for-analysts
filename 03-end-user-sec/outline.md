#### This outline is more for my use than anyone else's

1. Baseline threat model: programmatic/mass credential theft
	- Case study: LinkedIn hack
	- These affect everybody and need to be part of your threat model
	- Credential stuffing and phishing (yes, phishing) are the biggest threats

2. Before starting, return to cryptographic hashing
	- Encryption vs. hashing
		- Encrypting is *information-preserving* and *reversible*
		- Hashing is *information-destroying* and (in principle) *irreversible*
	- Hashes that are useful for cryptography have certain properties:
		- Deterministic: the same input always produces the same hash value
		- Infeasible to reverse: it should not be possible to find a message that returns a given hash value in reasonable time
		- Infeasible to find *hash collisions*, two messages that have the same hash
		- Similar input messages should produce uncorrelated hash values
		- Too slow to brute force
	- Uses for hashing 
		- Password checking: a hash of the password is stored, not the password itself. This is the one we're mostly concerned with
		- Integrity checking: instead of comparing large files, compare their hashes
		- Digital signatures: the message digest (the hash of the message) is signed with a private key. This is how identity is verified
	- There are lots of different hash functions with different properties
		- Some are fast (MD5, SHA1), some are slow by design (bcrypt, PBKDF-2)
		- Some are simple, some are composites of several hash functions

3. Workflow for stealing identities: credential-stuffing
	- Website or other service stores credentials/user database badly
	- Website gets hacked, TK give one or two examples of how
	- Credentials are stolen, passwords either plaintext (rare) or hashed
	- What the thief has gained is the ability to crack hashes as fast as their hardware allows
	- These creds are usually sold and will then be tried on other sites

4. Password cracking
	- How many hashes per second can the attacker try?
	- Dictionary attacks and other techniques to reduce the problem space
	- Password crackers use ML on mass plaintext hacks to learn the patterns people use
	- This is why the hashing used by the service is so important
	- *Entropy* is a measure of randomness. Higher entropy means less structure. Password cracking works best against lower-entropy passwords

5.  Lessons for good password practices
	- Forget what you've been told about capital letters, special characters, blah blah
	- When people use this advice, they end up using predictable (low-entropy) patterns that can be attacked
	- NIST has deprecated this entire method of doing passwords
	- The most important thing is that your passwords are
		- High-entropy, i.e. long and truly random
		- Unique
		- Whenever possible, not your only line of defense
    - Meeting these requirements for all the services you use is impossible without the use of a password manager

6. How to use a password manager
	- Password managers are safer than any other way of doing passwords
	- Find a reputable one that has the features you want. I'll tell you which one I use (Bitwarden), but look around
	- (when you're alone and have some time) Generate a random passphrase.  Rules:
		- Minimum four words and two numbers/specials, or just more words
		- You can't pick the words yourself or change them to make them meaningful
		- You can add a little entropy--change a separator, spelling etc.
		- You can't use it for anything other than your password manager
		- Practice typing it, then write it down somewhere extremely safe
	- Make your account and add 2FA to it (we'll talk about 2FA later)
		- Turn off your browser-based password manager (it's really weak and you need to have a single source of truth)
		- Practice by making a new account at some place you don't care about
		- Then log into it using your password manager
		- Get familiar with how it works, then change a password at a low-importance site
		- Make an inventory of your high-value accounts and get to work
	- They're for more than just passwords--credit cards, PINs, private keys, 2FA recovery codes, other kinds of secure notes

7. Two-factor authentication
	- Something you know, something you have, something you are
	- Traditional 2FA works by sending a one-time SMS, but you should avoid this whenever possible
	- Rank ordering of 2FA methods:
		1. U2F token, e.g. Yubikey
		2. Trusted device confirmation (Google, Apple, Microsoft, Duo Push)
		3. Time-based one-time passcode (TOTP), e.g. Google Authenticator, Authy, Duo
		4. SMS OTP or phone call to VoIP or other secured number
		5. SMS OTP or phone call to cell number

8. Don't leave the back door unlocked: secure your recovery options
	- Exploiting recovery options is the biggest source of cred theft after phishing and credential stuffing
    - Usually the easiest available targeted attack
	- An account is only as secure as the phone number, email address, or security question that allows you to do a password reset
	- **Don't** rely on phone numbers as a recovery option
	- Password hints are extremely garbage, never ever use them
        - Assume password hints are stored in plaintext

9. Phishing
    - You get generic advice about avoiding being phished all the time.
    - Don't discount phishing. It's getting way more advanced
    - Automated phishing attacks now use data from previous breaches to appear more legitimate