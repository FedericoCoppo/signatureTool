## Signature Tool
script tool that allow rsa sha256 signature of a file using openssl library.

RSA 2048-bit key
Hashing algorithm used is SHA256
Padding used with the signature is PKCSv1.5

## launch command
  ```
    $ ./GenSignature.sh
  ```

## brief manual
  private key generation
  ```
    $ openssl genpkey -algorithm RSA -out private_key.pem -pkeyopt rsa_keygen_bits:2048
  ```
  public key pop (needed for signature verification)
  ```
    $ openssl rsa -pubout -in private_key.pem -out public_key.pem
  ```
  public key modulus and exponent extraction (i.e needed for signature verification with ASN.1 DER encoding key management algo)
  ```
    $ openssl rsa -pubin -inform PEM -text -noout < public_key.pem
  ```

  
