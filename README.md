# ios-ssl-pinning

## SSL(Secure Socket Layer)
- Cryptographic protocol.
- Provides communication security over computer network.

## SSL Pinning
- Process of associating a host with its certificate or public key.
- https was secure but failed to prevent man in the middle attacks.
- Used to protect the app from Man-In-The-Middle(MITM) attack.

## SSL pinning Methods
- Embedding the Certificate
- Embedding the Public key

## Root, Leaf and Intermediate certificates
- Root certificate: 
    + Topmost certificate in the certificate hierarchy act as `Trust Anchor`.
    + It is used by the trusted certificate authority.
    + It is self-signed.
    + It is the foundation of trust for the entire certificate chain.
    + Pre installed in operating systems, browsers and devices.
    + Certifies immidiate certificate.
    
- Intermediate certificates:
    + Issued by the root certificate.
    + Inherits the trust from the root certificate.
    + Create a chain of trust between root certificate and end-user(leaf) certificates.
    + Help distribute the root's' trust without exposing its private key.
    + Issue and sign other intermediate or leaf certificates.
    + Limit the exposure of root certificate.
    
- Leaf certificates:
    + Final certificates in the chain.
    + Issued to end users, servers or devices.
    + Issued by intermediate certificate authority.
    + Contains information specific to entity - domain name, organization details.
    + Authenticate the identity of the entity(website or individual).
    + Facilitate secure communication(SSL/TLS encryption).

## Default Trust Evaluator
- Managed by Security framework.
- Relies on System's `Trusted Root Certificate Store`(pre installed on iOS devices)
- Default trust evaluator is overridden when SSL pinning is implemented.
