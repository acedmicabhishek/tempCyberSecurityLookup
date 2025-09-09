# MODULE 6: Network Security

## Authentication
Authentication is the process of verifying the identity of a user, process, or device. It is a critical component of network security, as it ensures that only authorized individuals can access network resources. Common authentication methods include:
-   **Passwords:** The most common authentication method, but also the weakest.
-   **Two-Factor Authentication (2FA):** Requires the user to provide two different authentication factors to verify themselves.
-   **Biometrics:** Uses unique physical characteristics, such as fingerprints or facial features, to identify a user.

## Basics of Public Key and Private Key Cryptography
Cryptography is the practice and study of techniques for secure communication in the presence of third parties called adversaries.
-   **Private Key Cryptography (Symmetric Cryptography):** Uses a single key to both encrypt and decrypt data. The key must be kept secret and shared between the sender and receiver.
-   **Public Key Cryptography (Asymmetric Cryptography):** Uses a pair of keys: a public key and a private key. The public key can be shared with anyone, while the private key must be kept secret. Data encrypted with the public key can only be decrypted with the corresponding private key.

## Digital Signatures and Certificates
-   **Digital Signatures:** A mathematical scheme for verifying the authenticity of digital messages or documents. A valid digital signature gives a recipient very strong reason to believe that the message was created by a known sender (authentication), that the sender cannot deny having sent the message (non-repudiation), and that the message was not altered in transit (integrity).
-   **Digital Certificates:** An electronic document used to prove the ownership of a public key. The certificate includes information about the key, information about the identity of its owner (called the subject), and the digital signature of an entity that has verified the certificate's contents (called the issuer).

## Firewalls
A firewall is a network security system that monitors and controls incoming and outgoing network traffic based on predetermined security rules. A firewall typically establishes a barrier between a trusted internal network and an untrusted external network, such as the Internet. Firewalls can be hardware, software, or both.