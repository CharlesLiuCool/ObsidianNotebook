### **Preface iii **

I Introduction and Classical Cryptography 1
1 Introduction and Classical Ciphers 3
1.1 Cryptography and Modern Cryptography . . . . . . . . . . . 3
1.2 The Setting of Private-Key Encryption . . . . . . . . . . . . 4
1.3 Historical Ciphers and Their Cryptanalysis . . . . . . . . . . 9
1.4 The Basic Principles of Modern Cryptography . . . . . . . . 18
1.4.1 Principle 1 – Formulation of Exact Definitions . . . . 18
1.4.2 Principle 2 – Reliance on Precise Assumptions . . . . 24
1.4.3 Principle 3 – Rigorous Proofs of Security . . . . . . . 26
References and Additional Reading . . . . . . . . . . . . . . . . . 27
Exercises . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 27

## **2 Perfectly-Secret Encryption 29**
2.1 Definitions and Basic Properties . . . . . . . . . . . . . . . . 29
2.2 The One-Time Pad (Vernam’s Cipher) . . . . . . . . . . . . 34
2.3 Limitations of Perfect Secrecy . . . . . . . . . . . . . . . . . 37
2.4 \* Shannon’s Theorem . . . . . . . . . . . . . . . . . . . . . . 38
2.5 Summary . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 40
References and Additional Reading . . . . . . . . . . . . . . . . . 41
Exercises . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 41

# **II Private-Key (Symmetric) Cryptography 45**

## **3 Private-Key Encryption and Pseudorandomness 47**
3.1 A Computational Approach to Cryptography . . . . . . . . . 47
3.1.1 The Basic Idea of Computational Security . . . . . . . 48
3.1.2 Efficient Algorithms and Negligible Success . . . . . . 54
3.1.3 Proofs by Reduction . . . . . . . . . . . . . . . . . . . 58
3.2 A Definition of Computationally-Secure Encryption . . . . . 59
3.2.1 A Definition of Security for Encryption . . . . . . . . 60
3.2.2 \* Properties of the Definition . . . . . . . . . . . . . . 64
3.3 Pseudorandomness . . . . . . . . . . . . . . . . . . . . . . . . 68
3.4 Constructing Secure Encryption Schemes . . . . . . . . . . . 72
3.4.1 A Secure Fixed-Length Encryption Scheme . . . . . . 72
3.4.2 Handling Variable-Length Messages . . . . . . . . . . 75
3.4.3 Stream Ciphers and Multiple Encryptions . . . . . . . 76
3.5 Security under Chosen-Plaintext Attacks (CPA) . . . . . . . 81
3.6 Constructing CPA-Secure Encryption Schemes . . . . . . . . 85
3.6.1 Pseudorandom Functions . . . . . . . . . . . . . . . . 85
3.6.2 CPA-Secure Encryption Schemes from Pseudorandom
Functions . . . . . . . . . . . . . . . . . . . . . . . . . 88
3.6.3 Pseudorandom Permutations and Block Ciphers . . . 93
3.6.4 Modes of Operation . . . . . . . . . . . . . . . . . . . 95
3.7 Security Against Chosen-Ciphertext Attacks (CCA) . . . . . 100
References and Additional Reading . . . . . . . . . . . . . . . . . 102
Exercises . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 103

## **4 Message Authentication Codes and Collision-Resistant Hash**
Functions 107
4.1 Secure Communication and Message Integrity . . . . . . . . 107
4.2 Encryption and Message Authentication . . . . . . . . . . . . 108
4.3 Message Authentication Codes – Definitions . . . . . . . . . 109
4.4 Constructing Secure Message Authentication Codes . . . . . 113
4.5 CBC-MAC . . . . . . . . . . . . . . . . . . . . . . . . . . . . 119
4.6 Collision-Resistant Hash Functions . . . . . . . . . . . . . . . 121
4.6.1 Defining Collision Resistance . . . . . . . . . . . . . . 122
4.6.2 Weaker Notions of Security for Hash Functions . . . . 124
4.6.3 A Generic “Birthday” Attack . . . . . . . . . . . . . . 125
4.6.4 The Merkle-Damg˚ard Transform . . . . . . . . . . . . 127
4.6.5 Collision-Resistant Hash Functions in Practice . . . . 129
4.7 * NMAC and HMAC . . . . . . . . . . . . . . . . . . . . . . 132
4.7.1 Nested MAC (NMAC) . . . . . . . . . . . . . . . . . . 132
4.7.2 HMAC . . . . . . . . . . . . . . . . . . . . . . . . . . 135
4.8 * Achieving Chosen-Ciphertext Secure Encryption . . . . . . 137
4.9 * Obtaining Privacy and Message Authentication . . . . . . 141
References and Additional Reading . . . . . . . . . . . . . . . . . 147
Exercises . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 148
5 Pseudorandom Objects in Practice: Block Ciphers 151
5.1 Substitution-Permutation Networks . . . . . . . . . . . . . . 154
5.2 Feistel Networks . . . . . . . . . . . . . . . . . . . . . . . . . 160
5.3 DES – The Data Encryption Standard . . . . . . . . . . . . 162
5.3.1 The Design of DES . . . . . . . . . . . . . . . . . . . . 162
5.3.2 Attacks on Reduced-Round Variants of DES . . . . . 165
5.3.3 The Security of DES . . . . . . . . . . . . . . . . . . . 168
5.4 Increasing the Key Size for Block Ciphers . . . . . . . . . . . 170
5.5 AES – The Advanced Encryption Standard . . . . . . . . . . 173
5.6 Differential and Linear Cryptanalysis – A Brief Look . . . . 176
5.7 Stream Ciphers from Block Ciphers . . . . . . . . . . . . . . 177
Additional Reading and References . . . . . . . . . . . . . . . . . 178
Exercises . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 179
6 * Theoretical Constructions of Pseudorandom Objects 181
6.1 One Way Functions . . . . . . . . . . . . . . . . . . . . . . . 182
6.1.1 Definitions . . . . . . . . . . . . . . . . . . . . . . . . 182
6.1.2 Candidates . . . . . . . . . . . . . . . . . . . . . . . . 185
6.1.3 Hard-Core Predicates . . . . . . . . . . . . . . . . . . 186
6.2 Overview of Constructions . . . . . . . . . . . . . . . . . . . 188
6.3 Hard-Core Predicates from Every One-Way Function . . . . 190
6.3.1 The Most Simplistic Case . . . . . . . . . . . . . . . . 190
6.3.2 A More Involved Case . . . . . . . . . . . . . . . . . . 191
6.3.3 The Full Proof . . . . . . . . . . . . . . . . . . . . . . 194
6.4 Constructions of Pseudorandom Generators . . . . . . . . . . 201
6.4.1 Pseudorandom Generators with Minimal Expansion . 201
6.4.2 Increasing the Expansion Factor . . . . . . . . . . . . 203
6.5 Constructions of Pseudorandom Functions . . . . . . . . . . 208
6.6 Constructions of Pseudorandom Permutations . . . . . . . . 212
6.7 Private-Key Cryptography – Necessary and Sufficient Assump-
tions . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 214
6.8 A Digression – Computational Indistinguishability . . . . . . 220
6.8.1 Pseudorandomness and Pseudorandom Generators . . 221
6.8.2 Multiple Samples . . . . . . . . . . . . . . . . . . . . . 222
References and Additional Reading . . . . . . . . . . . . . . . . . 225
Exercises . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 226
III Public-Key (Asymmetric) Cryptography 229
7 Number Theory and Cryptographic Hardness Assumptions 231
7.1 Preliminaries and Basic Group Theory . . . . . . . . . . . . 233
7.1.1 Primes and Divisibility . . . . . . . . . . . . . . . . . . 233
7.1.2 Modular Arithmetic . . . . . . . . . . . . . . . . . . . 235
7.1.3 Groups . . . . . . . . . . . . . . . . . . . . . . . . . . 237
7.1.4 The Group Z∗
N and the Chinese Remainder Theorem . 241
7.1.5 Using the Chinese Remainder Theorem . . . . . . . . 245
7.2 Primes, Factoring, and RSA . . . . . . . . . . . . . . . . . . 248
7.2.1 Generating Random Primes . . . . . . . . . . . . . . . 249
7.2.2 \* Primality Testing . . . . . . . . . . . . . . . . . . . . 252
7.2.3 The Factoring Assumption . . . . . . . . . . . . . . . 257
7.2.4 The RSA Assumption . . . . . . . . . . . . . . . . . . 258
7.3 Assumptions in Cyclic Groups . . . . . . . . . . . . . . . . . 260
7.3.1 Cyclic Groups and Generators . . . . . . . . . . . . . 260
7.3.2 The Discrete Logarithm and Diffie-Hellman Assump-
tions . . . . . . . . . . . . . . . . . . . . . . . . . . . . 263
7.3.3 Working in (Subgroups of) Z∗
p . . . . . . . . . . . . . . 267
7.3.4 * Elliptic Curve Groups . . . . . . . . . . . . . . . . . 268
7.4 Applications of Number-Theoretic Assumptions in Cryptogra-
phy . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 273
7.4.1 One-Way Functions and Permutations . . . . . . . . . 273
7.4.2 Constructing Collision-Resistant Hash Functions . . . 276
References and Additional Reading . . . . . . . . . . . . . . . . . 279
Exercises . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 280
8 * Factoring and Computing Discrete Logarithms 283
8.1 Algorithms for Factoring . . . . . . . . . . . . . . . . . . . . 283
8.1.1 Pollard’s p − 1 Method . . . . . . . . . . . . . . . . . . 284
8.1.2 Pollard’s Rho Method . . . . . . . . . . . . . . . . . . 286
8.1.3 The Quadratic Sieve Algorithm . . . . . . . . . . . . . 288
8.2 Algorithms for Computing Discrete Logarithms . . . . . . . 291
8.2.1 The Baby-Step/Giant-Step Algorithm . . . . . . . . . 293
8.2.2 The Pohlig-Hellman Algorithm . . . . . . . . . . . . . 294
8.2.3 The Discrete Logarithm Problem in ZN . . . . . . . . 296
8.2.4 The Index Calculus Method . . . . . . . . . . . . . . . 297
References and Additional Reading . . . . . . . . . . . . . . . . . 299
Exercises . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 299
9 Private-Key Management and the Public-Key Revolution 301
9.1 Limitations of Private-Key Cryptography . . . . . . . . . . . 301
9.1.1 The Key-Management Problem . . . . . . . . . . . . . 301
9.1.2 A Partial Solution – Key Distribution Centers . . . . 303
9.2 The Public-Key Revolution . . . . . . . . . . . . . . . . . . . 306
9.3 Diffie-Hellman Key Exchange . . . . . . . . . . . . . . . . . . 309
References and Additional Reading . . . . . . . . . . . . . . . . . 315
Exercises . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 315
10 Public-Key Encryption 317
10.1 Public-Key Encryption – An Overview . . . . . . . . . . . . 317
10.2 Definitions . . . . . . . . . . . . . . . . . . . . . . . . . . . . 320
10.2.1 Security against Chosen-Plaintext Attacks . . . . . . . 322
10.2.2 Security for Multiple Encryptions . . . . . . . . . . . . 325
10.3 Hybrid Encryption . . . . . . . . . . . . . . . . . . . . . . . . 330
10.4 RSA Encryption . . . . . . . . . . . . . . . . . . . . . . . . . 338
10.4.1 “Textbook RSA” and its Insecurity . . . . . . . . . . . 338
10.4.2 Attacks on RSA . . . . . . . . . . . . . . . . . . . . . 341
10.4.3 Padded RSA . . . . . . . . . . . . . . . . . . . . . . . 344
10.5 The El Gamal Encryption Scheme . . . . . . . . . . . . . . . 345
10.6 Chosen-Ciphertext Attacks . . . . . . . . . . . . . . . . . . . 351
10.7 * Trapdoor Permutations and Public-Key Encryption . . . . 355
10.7.1 Trapdoor Permutations . . . . . . . . . . . . . . . . . 356
10.7.2 Public-Key Encryption from Trapdoor Permutations . 356
References and Additional Reading . . . . . . . . . . . . . . . . . 360
Exercises . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 361
11 * Additional Public-Key Encryption Schemes 363
11.1 The Goldwasser-Micali Encryption Scheme . . . . . . . . . . 364
11.1.1 Quadratic Residues Modulo a Prime . . . . . . . . . . 364
11.1.2 Quadratic Residues Modulo a Composite . . . . . . . 366
11.1.3 The Quadratic Residuosity Assumption . . . . . . . . 370
11.1.4 The Goldwasser-Micali Encryption Scheme . . . . . . 371
11.2 The Rabin Encryption Scheme . . . . . . . . . . . . . . . . . 374
11.2.1 Computing Modular Square Roots . . . . . . . . . . . 375
11.2.2 A Trapdoor Permutation based on Factoring . . . . . 379
11.2.3 The Rabin Encryption Scheme . . . . . . . . . . . . . 383
11.3 The Paillier Encryption Scheme . . . . . . . . . . . . . . . . 385
11.3.1 The Structure of Z∗
N 2 . . . . . . . . . . . . . . . . . . 386
11.3.2 The Paillier Encryption Scheme . . . . . . . . . . . . . 388
11.3.3 Homomorphic Encryption . . . . . . . . . . . . . . . . 393
References and Additional Reading . . . . . . . . . . . . . . . . . 394
Exercises . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 395
12 Digital Signature Schemes 399
12.1 Digital Signatures – An Overview . . . . . . . . . . . . . . . 399
12.2 Definitions . . . . . . . . . . . . . . . . . . . . . . . . . . . . 401
12.3 RSA Signatures . . . . . . . . . . . . . . . . . . . . . . . . . 404
12.3.1 “Textbook RSA” and its Insecurity . . . . . . . . . . . 404
12.3.2 Hashed RSA . . . . . . . . . . . . . . . . . . . . . . . 406
12.4 The “Hash-and-Sign” Paradigm . . . . . . . . . . . . . . . . 407
12.5 Lamport’s One-Time Signature Scheme . . . . . . . . . . . . 409
12.6 * Signatures from Collision-Resistant Hashing . . . . . . . . 413
12.6.1 “Chain-Based” Signatures . . . . . . . . . . . . . . . . 414
12.6.2 “Tree-Based” Signatures . . . . . . . . . . . . . . . . . 417
12.7 Certificates and Public-Key Infrastructures . . . . . . . . . . 421
References and Additional Reading . . . . . . . . . . . . . . . . . 428
Exercises . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 429
13 Public-Key Cryptosystems in the Random Oracle Model 431
13.1 The Random Oracle Methodology . . . . . . . . . . . . . . . 432
13.1.1 The Random Oracle Model in Detail . . . . . . . . . . 433
13.1.2 Is the Random Oracle Methodology Sound? . . . . . . 438
13.2 Public-Key Encryption in the Random Oracle Model . . . . 441
13.2.1 Security against Chosen-Plaintext Attacks . . . . . . . 441
13.2.2 Security Against Chosen-Ciphertext Attacks . . . . . 445
13.2.3 OAEP . . . . . . . . . . . . . . . . . . . . . . . . . . . 450
13.3 RSA Signatures in the Random Oracle Model . . . . . . . . 452
References and Additional Reading . . . . . . . . . . . . . . . . . 456