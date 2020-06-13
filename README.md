<a href="https://orgid.tech"><img src="https://github.com/windingtree/branding/raw/master/org.id/svg/org.id-logo.svg" height="50" alt="ORG.ID"></a>

## ORG.JSON Schema

ORG.JSON is a data format used for describing organizations and organizational units. It is a part of [ORG.ID DID standard](https://orgid.tech).

[Complete ORG.JSON vocabulary](./vocabulary.md).

## Usage

## NPM package

```sh
npm i @windingtree/org.json-schema
```

```javascript
const orgJsonSchema = require('@windingtree/org.json-schema');
```

## JSON Schema Specification

```bash
npm run build
```

This will generate a JSON Schema specification file in the `dist` directory.

## Examples

### Legal Entity

```json
{
    "@context": [
        "https://www.w3.org/ns/did/v1",
        "https://windingtree.com/ns/orgid/v1"
    ],
    "id": "did:orgid:0xB4Caa470E33A4cE899C16e6C7E125eA03956e95D",
    "created": "2019-01-01T13:10:02.251Z",
    "updated": "2019-06-03T13:20:06.398Z",
    "publicKey": [
        {
            "id": "did:orgid:0xB4Caa470E33A4cE899C16e6C7E125eA03956e95D#keys-1",
            "type": "RsaVerificationKey2018",
            "controller": "did:orgid:0xB4Caa470E33A4cE899C16e6C7E125eA03956e95D",
            "publicKeyPem": "-----BEGIN PUBLIC KEY...END PUBLIC KEY-----\r\n",
            "note": "Hardware Key 1"
        },
        {
            "id": "did:orgid:0xB4Caa470E33A4cE899C16e6C7E125eA03956e95D#keys-3",
            "type": "Ieee2410VerificationKey2018",
            "controller": "did:orgid:0xB4Caa470E33A4cE899C16e6C7E125eA03956e95D",
            "publicKeyPem": "-----BEGIN PUBLIC KEY...END PUBLIC KEY-----\r\n",
            "note": "PKI #12345"
        }
    ],
    "service": [
        {
            "id": "did:orgid:0xB4Caa470E33A4cE899C16e6C7E125eA03956e95D#oidc",
            "type": "ORG.ID Authentication",
            "serviceEndpoint": "https://example.com/orgid-auth/"
        }
    ],
    "trust": {
        "assertions": [
            {
                "type": "dns",
                "claim": "test.com",
                "proof": "TXT"
            },
            {
                "type": "domain",
                "claim": "test2.com",
                "proof": "http://test2.com/orgid.txt"
            },
            {
                "type": "domain",
                "claim": "test3.com",
                "proof": "http://test3.com/orgid.txt"
            },
            {
                "type": "post",
                "claim": "twitter.com/jack",
                "proof": "https://twitter.com/jack/status/123456789/"
            }
        ],
        "credentials": [
            {
                "@context": [
                    "https://www.w3.org/2018/credentials/v1",
                    "https://www.w3.org/2018/credentials/examples/v1"
                ],
                "id": "did:orgid:0xf4234470E33A4cE899C16e6C7E125eA039564321#credential-129438",
                "type": [
                    "VerifiableCredential",
                    "FranchiseCredential"
                ],
                "issuanceDate": "2010-01-01T19:53:24Z",
                "credentialSubject": {
                    "id": "did:orgid:0xB4Caa470E33A4cE899C16e6C7E125eA03956e95D",
                    "franchiseLicense": {
                        "brand": "Hilton Garden Inn",
                        "validUntil": "2020-01-01T19:53:24Z"
                    }
                },
                "proof": {
                    "type": "RsaSignature2018",
                    "created": "2017-06-18T21:19:10Z",
                    "proofPurpose": "assertionMethod",
                    "verificationMethod": "did:orgid:0xf4234470E33A4cE899C16e6C7E125eA039564321#key-454312",
                    "jws": "eyJhbGciOiJSUzI1NiIsImI2NCI6ZmFsc2UsImNyaXQiOlsiYjY0Il19..."
                }
            }
        ]
    },
    "legalEntity": {
        "legalName": "Acme, Corp.",
        "alternativeName": "Acme",
        "legalIdentifier": "US12345567",
        "identifiers": [
            {
                "type": "IATA",
                "value": "123456"
            },
            {
                "type": "Trade License",
                "value": "98765431"
            }
        ],
        "legalType": "GmBH",
        "registeredAddress": {
            "country": "CZ",
            "subdivision": "71",
            "locality": "Jihlava",
            "postalCode": "71354",
            "streetAddress": "3150 Main St.",
            "premise": "STE 100"
        },
        "locations": [
            {
                "name": "Main Office",
                "description": "This is our main office",
                "address": {
                    "country": "CZ",
                    "subdivision": "71",
                    "locality": "Jihlava",
                    "postalCode": "71354",
                    "streetAddress": "3150 Main St.",
                    "premise": "STE 100",
                    "gps": "50.087070,14.417210",
                    "geocodes": [
                        {
                            "type": "olc",
                            "value": "3CQ9+F2 Prague"
                        },
                        {
                            "type": "what3words",
                            "value": "printers.torn.images"
                        }
                    ]
                },
                "openingHours": [
                    {
                        "weekDay": "mon,tue,wed",
                        "hours": "9:00-18:00"
                    },
                    {
                        "weekDay": "fri",
                        "hours": "10:00-16:00"
                    }
                ],
                "contacts": [
                    {
                        "function": "Reception",
                        "name": "John Smith",
                        "phone": "+1234567890",
                        "email": "email@spam.com",
                        "messengers": [
                            {
                                "type": "whatsapp",
                                "value": "+1234567890"
                            },
                            {
                                "type": "whatsapp",
                                "value": "+1234567890"
                            },
                            {
                                "type": "telegram",
                                "value": "acme.ny.reception"
                            },
                            {
                                "type": "viber",
                                "value": "+1234567890"
                            },
                            {
                                "type": "wechat",
                                "value": "acme.ny.reception"
                            },
                            {
                                "type": "messenger",
                                "value": "acme.ny.reception"
                            },
                            {
                                "type": "line",
                                "value": "acme.ny.reception"
                            },
                            {
                                "type": "kik",
                                "value": "acme.ny.reception"
                            }
                        ]
                    }
                ]
            }
        ],
        "contacts": [
            {
                "function": "Customer Service",
                "name": "John Smith",
                "phone": "+1234567890",
                "email": "email@spam.com"
            },
            {
                "function": "Sales",
                "name": "Jenna Smith",
                "phone": "+1234567890",
                "email": "email@spam.com"
            },
            {
                "function": "Press",
                "phone": "+1234567890",
                "email": "email@spam.com"
            }
        ]
    }
}
```

### Organizational Unit

```json
{
    "@context": [
        "https://www.w3.org/ns/did/v1",
        "https://windingtree.com/ns/orgid/v1"
    ],
    "id": "did:orgid:0xB4Caa470E33A4cE899C16e6C7E125eA03956e95D",
    "created": "2019-01-01T13:10:02.251Z",
    "updated": "2019-06-03T13:20:06.398Z",
    "publicKey": [
        {
            "id": "did:orgid:0xB4Caa470E33A4cE899C16e6C7E125eA03956e95D#keys-1",
            "type": "RsaVerificationKey2018",
            "controller": "did:orgid:0xB4Caa470E33A4cE899C16e6C7E125eA03956e95D",
            "publicKeyPem": "-----BEGIN PUBLIC KEY...END PUBLIC KEY-----\r\n",
            "note": "Hardware Key 1"
        },
        {
            "id": "did:orgid:0xB4Caa470E33A4cE899C16e6C7E125eA03956e95D#keys-2",
            "type": "Ieee2410VerificationKey2018",
            "controller": "did:orgid:0xB4Caa470E33A4cE899C16e6C7E125eA03956e95D",
            "publicKeyPem": "-----BEGIN PUBLIC KEY...END PUBLIC KEY-----\r\n",
            "note": "PKI #12345"
        }
    ],
    "service": [
        {
            "id": "did:orgid:0xB4Caa470E33A4cE899C16e6C7E125eA03956e95D#oidc",
            "type": "erevmax-suite-apt-0.3.1a",
            "serviceEndpoint": "https://example.com/orgid-auth/"
        }
    ],
    "trust": {
        "assertions": [
            {
                "type": "domain",
                "claim": "test.com",
                "proof": "dns"
            },
            {
                "type": "twitter",
                "claim": "jack",
                "proof": "https://twitter.com/status/123456789/"
            },
            {
                "type": "facebook",
                "claim": "MyBusinessPage",
                "proof": "https://www.facebook.com/MyBusinessPage/photos/a.672157592834538/2030288447021439/"
            },
            {
                "type": "instagram",
                "claim": "myinstagramusername",
                "proof": "https://instagram.com/p/123456789/"
            }
        ],
        "credentials": [
            {
                "@context": [
                    "https://www.w3.org/2018/credentials/v1",
                    "https://www.w3.org/2018/credentials/examples/v1"
                ],
                "id": "did:orgid:0xf4234470E33A4cE899C16e6C7E125eA039564321#credential-129438",
                "type": [
                    "VerifiableCredential",
                    "FranchiseCredential"
                ],
                "issuanceDate": "2010-01-01T19:73:24Z",
                "credentialSubject": {
                    "id": "did:orgid:0xB4Caa470E33A4cE899C16e6C7E125eA03956e95D",
                    "franchiseLicense": {
                        "brand": "Hilton Garden Inn",
                        "validUntil": "2020-01-01T19:73:24Z"
                    }
                },
                "proof": {
                    "type": "RsaSignature2018",
                    "created": "2017-06-18T21:19:10Z",
                    "proofPurpose": "assertionMethod",
                    "verificationMethod": "did:orgid:0xf4234470E33A4cE899C16e6C7E125eA039564321#key-454312",
                    "jws": "eyJhbGciOiJSUzI1NiIsImI2NCI6ZmFsc2UsImNyaXQiOlsiYjY0Il19..."
                }
            }
        ]
    },
    "organizationalUnit": {
        "name": "Grand Budapest Hotel",
        "type": [
            "hotel",
            "boutique"
        ],
        "description": "Grand Budapest Hotel is total lorem ipsum",
        "longDescription": "Until recently, the prevailing view assumed lorem ipsum was born as a nonsense text. “It's not Latin, though it looks like it, and it actually says nothing,” Before & After magazine answered a curious reader, “Its ‘words’ loosely approximate the frequency with which letters occur in English, which is why at a glance it looks pretty real.”\nAs Cicero would put it, “Um, not so fast.”\nThe placeholder text, beginning with the line “Lorem ipsum dolor sit amet, consectetur adipiscing elit”, looks like Latin because in its youth, centuries ago, it was Latin.",
        "address": {
            "country": "CZ",
            "subdivision": "71",
            "locality": "Jihlava",
            "postalCode": "71354",
            "streetAddress": "3150 Main St.",
            "premise": "STE 100",
            "gps": "50.087070,14.417210",
            "geocodes": [
                {
                    "type": "olc",
                    "value": "3CQ9+F2 Prague"
                },
                {
                    "type": "what3words",
                    "value": "printers.torn.images"
                }
            ]
        },
        "openingHours": [
            {
                "weekDay": "mon,tue,wed",
                "hours": "9:00-18:00"
            },
            {
                "weekDay": "fri",
                "hours": "10:00-16:00"
            }
        ],
        "contacts": [
            {
                "function": "Reception",
                "phone": "+1234567890",
                "email": "email@spam.com"
            }
        ],
        "media": {
            "logo": "https://imagehosting/hotel.jpg",
            "images": [
                {
                    "description": "Hotel Lobby",
                    "uri": "https://imagehosting/123456789.jpg",
                    "thumbnail": "https://imagehosting/123456789-thumbnail.jpg"
                }
            ],
            "videos": [
                {
                    "description": "Hotel Tour",
                    "uri": "https://videohosting/hotel-tour.mp4",
                    "cover": "https://imagehosting/hotel-tour-cover.jpg",
                    "thumbnail": "https://imagehosting/hotel-tour-cover-thumbnail.jpg"
                }
            ],
            "documents": [
                {
                    "description": "Hotel Presentation",
                    "uri": "https://filehosting/hotel-presentation.pdf"
                }
            ]
        }
    }
}
```

## ORG.ID Ecosystem

![ORG.ID Ecosystem](https://github.com/windingtree/org.id/raw/master/assets/org.id-ecosystem.png)

- [Winding Tree DAO](https://github.com/windingtree/dao) controls ORG.ID Registry smart contract and some Directories (including their rules)
- [ORG.ID Registry](https://github.com/windingtree/org.id) contains records of all organizations and organizational units
- **ORG.JSON Schema (you are here)**
- [ORG.ID Resolver](https://github.com/windingtree/org.id-resolver) is an application for resolving ORG.ID data in [W3C DID](https://w3c.github.io/did-core/) format
- [ORG.ID Directories](https://github.com/windingtree/org.id-directories) are curated lists of organizations
- [Arbor](https://arbor.fm) can be used to look up an ORG.ID, and also to create and manage your own ORG.ID
