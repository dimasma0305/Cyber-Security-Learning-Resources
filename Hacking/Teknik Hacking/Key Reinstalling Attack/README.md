### What is key reinstallation attack?

KRACK is an acronym for Key Reinstallation Attack. KRACK is **a severe replay attack on Wi-Fi Protected Access protocol (WPA2), which secures your Wi-Fi connection**. Hackers use KRACK to exploit a vulnerability in WPA2. When in close range of a potential victim, attackers can access and read encrypted data using KRACK.

# Notes
### Initialization vectors (IVs)

**IV and nonce are often used interchangeably**. However, a careful definition does differentiate between these two concepts. For our purposes, an IV is a nonce with an additional requirement: it must be selected in a nonpredictable way. That is, the IV can't be sequential; it must be random.

### PTK (Pairwise Transient Key):

Pairwise Transient key is **used to encrypt all unicast traffic between a client station and the access point**. PTK is unique between a client station and access point.

# Referensi
<iframe width="560" height="315" src="https://www.youtube.com/embed/fOgJswt7nAc" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

https://www.krackattacks.com/ //artikel
https://papers.mathyvanhoef.com/ccs2017.pdf //pappers