# signatureTool
script tool that allow rsa sha256 signature of a file using openssl library.

# launch command
$ ./GenSignature.sh

# brief manual
  private key generation:
  $ openssl genpkey -algorithm RSA -out private_key.pem -pkeyopt rsa_keygen_bits:2048
  
  public key pop (needed for signature verification)
  $ openssl rsa -pubout -in private_key.pem -out public_key.pem
  
  public key modulus and exponent display
  $ openssl rsa -pubin -inform PEM -text -noout < public_key.pem

  alternatively:
  $ PUBKEY=`grep -v -- ----- public_key.pem| tr -d '\n'
  $ echo $PUBKEY | base64 -d | openssl asn1parse -inform DER -i
  $ $PUBKEY | base64 -d | openssl asn1parse -inform DER -i -strparse 19
  
