# infosec-for-analysts
Materials for workshops on information security for data analysts.

I'll use this repo to host presentations, notes, and resource lists as we continue to develop this material over time.

## Resources

### Threat models and mental frameworks

Ars Technica's explanation of [why threat models are useful for everyone](https://arstechnica.com/information-technology/2017/07/how-i-learned-to-stop-worrying-mostly-and-love-my-threat-model/ "How I learned to stop worrying (mostly) and love my threat model") is a good introduction to thinking about security.

The 2016 Uber hack is pretty much a perfect model of how to do everything wrong. I'll have a bunch more resources on each piece of this hack, but [How to Prevent the Uber Hack: 5 Defensive Tactics](https://www.hitachi-systems-security.com/blog/how-to-prevent-the-uber-hack/ "How to Prevent the Uber Hack: 5 Defensive Tactics") is a decent place to start.

### Cryptography

One of the founders of WhatsApp [walked away](https://www.forbes.com/sites/parmyolson/2018/09/26/exclusive-whatsapp-cofounder-brian-acton-gives-the-inside-story-on-deletefacebook-and-why-he-left-850-million-behind/#2fc8726b3f20 "Forbes story on WhatsApp/Facebook controversy") from close to a billion dollars, in part because of a disagreement about who should hold the decryption keys.

A quick [primer](https://robertheaton.com/2014/03/27/how-does-https-actually-work/ "How does HTTPS actually work?") on what HTTPS does, and a good explanation of the way the encryption sequence between unfamiliar communication partners on the internet generally works.

A much more complete [resource list](https://github.com/sobolevn/awesome-cryptography "cryptography resources") on some of the basic concepts in cryptography

A news story from November 2018 illustrating how [crypto is hard](https://arstechnica.com/information-technology/2018/11/police-decrypt-258000-messages-after-breaking-pricey-ironchat-crypto-app/?comments=1 "Police decrypt 258,000 messages after breaking pricey IronChat crypto app") and you shouldn't trust somebody just because they charge tons of money

#### RSA encryption



A somewhat more terse [description](https://blogs.ams.org/mathgradblog/2014/03/30/rsa/ "RSA Encryption – Keeping the Internet Secure")

A little walkthrough implementing RSA encryption [in R](https://cran.r-project.org/web/packages/openssl/vignettes/bignum.html "Fun with bignum: how RSA encryption works")
