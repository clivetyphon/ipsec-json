document source | Clive Gross
------------------|----------------
Request for Comments: RFC number  |  author affiliation
subseries ID subseries number |  more author info
RFC relation:RFC number  |   x
Category: category | month year

# Title

## Abstract
Bla

## Status of this Memo
This Internet-Draft is submitted in full conformance with the provisions of BCP 78 and BCP 79. Internet-Drafts are working documents of the Internet Engineering Task Force (IETF). Note that other groups may also distribute working documents as Internet-Drafts. The list of current Internet-Drafts is at http://datatracker.ietf.org/drafts/current. Internet-Drafts are draft documents valid for a maximum of six months and may be updated, replaced, or obsoleted by other documents at any time. It is inappropriate to use Internet- Drafts as reference material or to cite them other than as "work in progress."

## Copyright Notice
Copyright (c) 2017 IETF Trust and the persons identified as the document authors. All rights reserved. This document is subject to BCP 78 and the IETF Trust's Legal Provisions Relating to IETF Documents (http://trustee.ietf.org/license-info) in effect on the date of publication of this document. Please review these documents carefully, as they describe your rights and restrictions with respect to this document. Code Components extracted from this document must include Simplified BSD License text as described in Section 4.e of the Trust Legal Provisions and are provided without warranty as described in the Simplified BSD License.

## Table of Contents
Bla

## Introduction
IPsec JSON is a specification for describing IPsec VPN connection profiles, cipher suites and associated network configurations in JSON [RFC4627].

IPsec is notoriously difficult to configure and test, particularly cross-vendor interoperability. IPsec JSON is designed to provide a common, unambiguous language that can be transformed programmatically into vendor-specific device configurations.

## Conventions used in this Document
The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED", "MAY", and "OPTIONAL" in this document are to be interpreted as described in [RFC2119]. The grammatical rules in this document are to be interpreted as described in [RFC5234]. 

## Document Structure
Bla

### Top Level
Bla

### Connection Object

“Connection objects” appear in an IPsec JSON document to represent IPsec connection profiles.

A Connection object MUST contain at least the following top-level members:

 - name: The unique name of the connection profile. The value of the name member MUST be a string.
 - keyexchange: A Key Exchange object representing the ISAKMP key exchange or equivalent configuration.
 - ipsec: An IPsec object representing the IPsec protocol configuration.
 - network: A Network object representing the network configuration of the IPsec connection profile.

```
{
  "name": ""
  "keyexchange": {},
  "ipsec": {},
  "network": {}
}
```

### Cipher Suite Object

“Cipher Suite objects” appear in an IPsec JSON document to represent the combination of encryption, authentication, integrity and perfect forward secrecy algorithms required in a Security Association.

A Cipher Suite object MUST contain at least the following top-level members:

 - bla

In addition, a Cipher Suite object MAY contain any of these top-level members:

 - encryption
 - pseudo-random-function
 - integrity
 - dh-group

### Key Exchange Object
Bla

### IPsec Object

## Encryption algorithms

An encryption algorithm string MAY be any of these values:

 -`3des`: 168 bit 3DES-EDE-CBC
 -`cast128`: 128 bit CAST-CBC
 -`blowfish128 or blowfish`: 128 bit Blowfish-CBC
 -`blowfish192`: 192 bit Blowfish-CBC
 -`blowfish256`: 256 bit Blowfish-CBC
 -`null`: Null encryption
 -`aes128 or aes`: 128 bit AES-CBC
 -`aes192`: 192 bit AES-CBC
 -`aes256`: 256 bit AES-CBC
 -`aes128ctr`: 128 bit AES-COUNTER
 -`aes192ctr`: 192 bit AES-COUNTER
 -`aes256ctr`: 256 bit AES-COUNTER
 -`aes128ccm8 or aes128ccm64`: 128 bit AES-CCM with 64 bit ICV
 -`aes192ccm8 or aes192ccm64`: 192 bit AES-CCM with 64 bit ICV
 -`aes256ccm8 or aes256ccm64`: 256 bit AES-CCM with 64 bit ICV
 -`aes128ccm12 or aes128ccm96`: 128 bit AES-CCM with 96 bit ICV
 -`aes192ccm12 or aes192ccm96`: 192 bit AES-CCM with 96 bit ICV
 -`aes256ccm12 or aes256ccm96`: 256 bit AES-CCM with 96 bit ICV
 -`aes128ccm16 or aes128ccm128`: 128 bit AES-CCM with 128 bit ICV
 -`aes192ccm16 or aes192ccm128`: 192 bit AES-CCM with 128 bit ICV
 -`aes256ccm16 or aes256ccm128`: 256 bit AES-CCM with 128 bit ICV
 -`aes128gcm8 or aes128gcm64`: 128 bit AES-GCM with 64 bit ICV
 -`aes192gcm8 or aes192gcm64`: 192 bit AES-GCM with 64 bit ICV
 -`aes256gcm8 or aes256gcm64`: 256 bit AES-GCM with 64 bit ICV
 -`aes128gcm12 or aes128gcm96`: 128 bit AES-GCM with 96 bit ICV
 -`aes192gcm12 or aes192gcm96`: 192 bit AES-GCM with 96 bit ICV
 -`aes256gcm12 or aes256gcm96`: 256 bit AES-GCM with 96 bit ICV
 -`aes128gcm16 or aes128gcm128`: 128 bit AES-GCM with 128 bit ICV
 -`aes192gcm16 or aes192gcm128`: 192 bit AES-GCM with 128 bit ICV
 -`aes256gcm16 or aes256gcm128`: 256 bit AES-GCM with 128 bit ICV
 -`aes128gmac`: Null encryption with 128 bit AES-GMAC
 -`aes192gmac`: Null encryption with 192 bit AES-GMAC
 -`aes256gmac`: Null encryption with 256 bit AES-GMAC
 -`camellia128 or camellia`: 128 bit Camellia-CBC
 -`camellia192`: 192 bit Camellia-CBC
 -`camellia256`: 256 bit Camellia-CBC
 -`camellia128ctr`: 128 bit Camellia-COUNTER
 -`camellia192ctr`: 192 bit Camellia-COUNTER
 -`camellia256ctr`: 256 bit Camellia-COUNTER
 -`camellia128ccm8 or camellia128ccm64`: 128 bit Camellia-CCM with 64 bit ICV
 -`camellia192ccm8 or camellia192ccm64`: 192 bit Camellia-CCM with 64 bit ICV
 -`camellia256ccm8 or camellia256ccm64`: 256 bit Camellia-CCM with 64 bit ICV
 -`camellia128ccm12or camellia128ccm96`: 128 bit Camellia-CCM with 96 bit ICV
 -`camellia192ccm12or camellia192ccm96`: 192 bit Camellia-CCM with 96 bit ICV
 -`camellia256ccm12or camellia256ccm96`: 256 bit Camellia-CCM with 96 bit ICV
 -`camellia128ccm16or camellia128ccm128`: 128 bit Camellia-CCM with 128 bit ICV
 -`camellia192ccm16or camellia192ccm128`: 192 bit Camellia-CCM with 128 bit ICV
 -`camellia256ccm16or camellia256ccm128`: 256 bit Camellia-CCM with 128 bit ICV
 -`chacha20poly1305`: 256 bit ChaCha20/Poly1305 with 128 bit ICV

## Security Considerations
Bla

## Examples
Bla

## References

### Normative References
Bla

### Informative References
Bla

## Appendix A. Bla
Bla
