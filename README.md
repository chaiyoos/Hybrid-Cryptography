# Hybrid-Cryptography

In the proposed project, half breed encryption is utilized where records are scrambled by blowfish combined with
document part, and SRNN (modified RSA) is utilized for the secured correspondence amongst clients and the servers


Secure Cloud File Storage with Hybrid Cryptography
In cloud computing, data is shared across various clients, servers, and individuals, making data security a significant concern. Intruders may easily access and compromise the data. Symmetric key cryptography is efficient but faces challenges in secure key exchange, as both the sender and receiver use the same key. Ensuring the security of this shared key, without exposing it to unauthorized parties, is a significant challenge. Asymmetric key cryptography addresses this issue by using a pair of keys: a public key for encryption and a private key for decryption. To enhance data protection, a hybrid encryption approach is proposed, combining Blowfish encryption with file partitioning and a modified RSA algorithm known as SRNN for secure communication between users and servers.

Blowfish Algorithm

Blowfish is a symmetric block cipher utilizing a Feistel network with 16 rounds of encryption and decryption. It employs a 64-bit block size and a variable key length of up to 448 bits. The algorithm uses 18 sub-arrays called P-boxes and four S-boxes, each with 256 entries. It consists of two main phases: Key Expansion, which generates several sub-keys, and Data Encryption, which involves 16-round networks. Each round includes a key-dependent permutation and a data-dependent substitution.

Encryption with Blowfish

Blowfish encryption involves sixteen cycles of the round function and a final output operation using round keys and S-box values. The generation of round keys and initialization of S-boxes are crucial steps in the key schedule.

SRNN Algorithm

The SRNN algorithm, a variant of RSA, is a public key cryptography method. It involves extremely large numbers with two prime factors and incorporates short-range natural numbers in the key pair. One key (public) is used for encryption and the other (private) for decryption, enhancing security. The key generation process includes:

Generating two large random primes, ( p ) and ( q ).
Calculating ( n = pq ) and ( \phi = (p-1)(q-1) ).
Choosing an integer ( e ) such that ( 1 < e < \phi ) and gcd(( e, \phi )) = 1.
Finding ( d ) such that ( ed \equiv 1 \mod \phi ).
Selecting short-range natural numbers ( u ) and ( a ) such that ( u < \phi-1 ) and ( u < a < \phi ).
Computing ( ua ) and defining the public key as (( n, e, ua )) and the private key as (( d, a, u )). ( p, q, ) and ( \phi ) remain confidential.
Encryption Process

Obtain the recipient's public key (( n, e, ua )).
Represent the plaintext message as a positive integer ( M ).
Compute the ciphertext ( C = (M \cdot ua)^e \mod n ).
Send ( C ) to the recipient.
Decryption Process

Use the recipient's private key (( d, a, u )).
Calculate ( M = (v \cdot C)^d \mod n ), where ( v = u^{\phi-a} \mod n ).
Extract the plaintext from ( M ).
This hybrid cryptographic approach ensures robust and secure data storage in cloud environments.
