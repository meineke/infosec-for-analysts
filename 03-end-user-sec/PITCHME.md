## Day 3: End-User Security for Analysts

---

#### There's too much to cover today, so the TL;DR<sup>*</sup> is

The bare minimum on security for everyone is to

1. Start using a password manager
    - Make a new, truly random passphrase for it that you **never** use for anything else
        - Use a Diceware generator, here's a good one: https://www.rempe.us/diceware
    - Change the passwords on every site you have an account on to something very long, random, and **unique**
        - Your password manager has a password generator to do this
    - You can also use your password manager to keep track of API tokens, private keys, credit cards, 2FA backup codes, setc.

<sup>*</sup> too long; didn't read

---

The bare minimum on security for everyone is to

2. Put two-factor authentication (2FA) everywhere
    - First inventory your accounts. What are your top priority accounts?
        - **Password manager**, email, work/school, finance, social media, GitHub, domains you own?
    - These all need to be behind 2FA
    - Use a TOTP app like Google Authenticator, Authy, or Duo
        - More secure than SMS passcodes
        - Even better (phish-proof, convenient, but costs): U2F key
    - Always have a backup 2FA method
        - Keep backup codes in your password manager
        - Use an old phone as second TOTP generator

---

The bare minimum on security for everyone is to

3. Don't leave the back door unlocked: secure your "account recovery" options
    - Don't allow phone numbers to recover your account
    - Don't use security questions or password hints
    - Only allow account recovery from an email address whose security you trust

---

The bare minimum on security for everyone is to

4. Remember, phishers use analytics too
    - Automated targeted phishing is real
    - Every time a website gets hacked and your personal info gets out, there's more data available for phishing
    - Don't assume phishers have bad spelling or janky websites
    - The padlock icon doesn't mean you're safe