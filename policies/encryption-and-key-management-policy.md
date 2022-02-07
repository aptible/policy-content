# Storage Encryption
In order to maintain the security and privacy of our information at rest, all workforce members must abide by the following storage requirements:

- all laptops, workstations, tablets, phones, other mobile devices and portable drives used to store or access non-public information must have full-disk encryption enabled; and
- Sensitive/Regulated Information must be encrypted at rest.

If it is determined that encryption is not reasonable, appropriate, or possible the company must document the rationale and acceptance of risk in the risk register.

# Transmission Encryption

In order to maintain the security and privacy of our information in transit, all workforce members must abide by the following transmission requirements:

- Sensitive/Regulated Information from our clients (including database backups) must be encrypted in transit with an approved method;
- any transfer of non-public information outside of our networks must utilize an approved encryption method;
- the physical transfer of non-public information must be encrypted using an approved method;
- authentication information (user ID, password, MFA token, etc.) must be encrypted in transit at all times; and
- all remote access methods must be approved by the Security Team and must utilize approved encryption technology.
- use secure (e.g., non-clear text and authenticated) standardized network protocols for the import and export of data and to manage the service, and shall make available a document to consumers (tenants) detailing the relevant interoperability and portability standards that are involved.

We shall ensure that security is maintained through all aspects of transactions.

# Key Management Life Cycle

The Security Team shall ensure that encryption keys are securely generated, stored, assigned, revoked, and destroyed when no longer in use. All keys must have identifiable owners.

# Key Generation

## Secure Generation

Encryption keys must be generated in a secure manner that prevents loss, theft, or compromise.

## General Algorithm Requirements

We shall use [NIST SP 800-52 Rev. 2](https://csrc.nist.gov/publications/detail/sp/800-52/rev-2/final) and [NIST FIPS 140-2](https://csrc.nist.gov/projects/cryptographic-module-validation-program/standards) as guiding documents for our selection of encryption modules and implementations, and must implement requirements therein to the extent that it is reasonable and appropriate to do so.

The Security Officer and the Legal Team shall ensure that any encryption module or implementation we use complies with all relevant legal and contractual requirements.

## Specific Algorithm Requirements

In addition to the general requirements outlined above, we have also adopted the following specific requirements:

- **Encryption algorithms:** Encryption methods and tools should utilize only encryption technologies based on standard algorithms approved in FIPS 140-2. The use of proprietary encryption algorithms is not allowed, unless reviewed and approved by the Security Team.
- **Cipher suites:** Cipher suites should be restricted to those specified in Section 3.3.1 of [NIST SP 800-52 Rev. 1](https://csrc.nist.gov/publications/detail/sp/800-52/rev-1/final). Exceptions may be made for compatibility with older clients.
- **Key generation:** Key generation must be seeded from an industry standard random number generator (RNG). Examples are available in [NIST Annex C: Approved Random Number Generators for FIPS PUB 140-2](https://csrc.nist.gov/csrc/media/publications/fips/140/2/final/documents/fips1402annexc.pdf).
- **Symmetric encryption:** Symmetric encryption must provide at least 112 bits of security. The use of the Advanced Encryption Standard (AES) is strongly recommended for symmetric encryption, however 3TDEA is permitted.
- **Asymmetric encryption:** Asymmetric encryption must provide at least 112 bits of security. Public keys must be at least 2048 bits. RSA and/or Elliptic Curve Cryptography (ECC) algorithms are strongly recommended for asymmetric encryption, however DSA is permitted.
- **Digital signatures:** Digital signatures must use RSA or DSA.
- **Hash functions:** Hash functions must comply with [NIST policy on hash functions](http://csrc.nist.gov/groups/ST/hash/policy.html).

# Key Storage and Access

Because of their sensitive nature, encryption keys must be protected as follows:

- encryption keys are considered to be Sensitive/Regulated Information, and access to them must be strictly limited to those who have a "need to know" to perform their job duties;
- encryption keys must be stored within an encrypted key store or an otherwise encrypted form using an approved algorithm; and
- encryption keys that are compromised (e.g., lost or stolen) must be reported immediately to the Security Officer.

# Key Agreement and Authentication

We have implemented the following requirements related to key agreement and authentication:

- key exchanges must use one of the following cryptographic protocols: RSA, Diffie-Hellman, IKE, or Elliptic Curve Diffie-Hellman (ECDH);
- endpoints must be authenticated prior to the exchange or derivation of session keys;
- public keys used to establish trust must be authenticated prior to use (for example, by transmitting keys via a cryptographically signed message or by manual verification of the public key hash);
- all Internet-facing production servers and applications using SSL/TLS must have the certificates signed by a known, trusted provider; and
- non-Internet-facing systems may use self-signed certificates.

# Key Rotation
In order to protect the data we store and transmit, the Security Team shall ensure that encryption keys are rotated as follows:

- at-rest encryption keys must be rotated at least quarterly; and
- SSL/TLS encryption keys must be rotated at least quarterly.