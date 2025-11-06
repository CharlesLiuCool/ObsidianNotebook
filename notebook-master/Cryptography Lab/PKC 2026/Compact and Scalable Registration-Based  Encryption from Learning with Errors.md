>*High Level Overview*
>Makes post-quantum register based encryption (RBE) more practical by reducing ciphertext size by an order magnitude (down to around 220 MB from few GB), while demonstrating superior scalability.
>
>Takes advantage of new primitive called *decomposable laconic encryption (dLE)* inspired by multi-recipient encryption (mPKE) techniques.

### **Paper Put in Context**

Early RBE relied heavily on the *non-black-box* use of cryptographic primitives, such as indistinguishability obfuscation or the garbled circuit tree technique. The estimated size of ciphertext from these constructions were *terabyte range*, totally impractical.

`Glaeser et al.` produced the first concrete, *highly efficient* RBE construction using pairing. It employs a black-box approach, size of the ciphertext is only $914$-bytes, although it has the problem of *small identity space*.

`Fiore et al.` solved Glaeser's problem with cuckoo hashing.

`Döttoling et al.` proposed an efficient, black-box construction of RBE based on LWE, the *first post-quantum black-box* approach. The ciphertext was $4.4$GB for $2^{10}$ users, far from practical.

`Fiore et al.` improved on this, reducing the size of ciphertexts. However:
- Ciphertext still in gigabytes
- Only achieves compactness against selective adversaries
- Maximum number of registered users must be fixed in advance

### **This Work**

