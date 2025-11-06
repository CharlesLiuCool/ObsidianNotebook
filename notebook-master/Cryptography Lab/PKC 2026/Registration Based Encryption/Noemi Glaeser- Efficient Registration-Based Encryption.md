>*Link:* 
>CMU Crypto Seminar
>https://www.youtube.com/watch?v=iOC_1sOUuSg

>*Main Point:*
>Glaeser discusses the first practically efficient RBE construction, which uses a common reference string (CRS) and is pairing-based.

### **Secure Communication**

The motivated behind registration-based encryption is *secure communication*.

If two parties are trying to communicate, and there's an eavesdropper, you solve it with the decades old technique: *Public Key Encryption!*

But how do you know the other parties' public key?
- LAN Party (meet up in person)
- Delegate to secure third party

### **Public Key Infrastructure**

![[Noemi Glaeser- Efficient Registration-Based Encryption 2025-11-03 20.17.43.excalidraw|center|700]]

### **Identity Based Encryption (IBE)**

![[Noemi Glaeser- Efficient Registration-Based Encryption 2025-11-04 22.35.49.excalidraw|center|800]]

Anyone with the master secret key, *msk*, can:
- Recompute `sk` for any party and decrypt its ciphertext
- Generate `sk` in a faulty way (e.g. fails to decrypt ciphertexts containing some banned words)

### **Registration-Based Encryption (RBE)**

>*Motivation (Escrow Problem)*:
>Can we encrypt to an id without a super powerful third party?

Work by `[GHMR18]`:
![[Noemi Glaeser- Efficient Registration-Based Encryption 2025-11-03 20.21.43.excalidraw|center|800]]

### **Properties of RBE**

- *Completeness*: Assuming honest setup, for an honestly registered user id\*,
$$\text{Dec}(\text{sk},\text{u} \subseteq \text{aux}', \text{Enc}(\text{pp},\text{id}^*, m)) = m$$
regardless of arbitrarily potentially malicious registrations between Enc and Dec.

What that means is when everyone behaves honestly, even when some malicious parties register in between, encryption/decryption should function as expected.

- *Security*: A PPT adversary can't distinguish between encryptions of two messages made to id\* (CPA-security), even if all other users are corrupted.

- *Verifiability* `[GV20]`: Combat malicious key curator (KC) by adding proofs of membership/non-membership.
### **RBE from iO `[GHMR18]`**

### **Efficient RBE**

Group users into buckets

![[Noemi Glaeser- Efficient Registration-Based Encryption 2025-11-03 20.45.38.excalidraw]]