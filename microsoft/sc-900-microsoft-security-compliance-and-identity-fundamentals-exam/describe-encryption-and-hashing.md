# Describe encryption and hashing

Let’s break this into ADHD-friendly chunks with simple explanations, analogies, and tricks to retain it.

***

#### **Big Idea: What Are Encryption and Hashing?**

* **Encryption**: Scrambles data so only someone with the right key can unscramble it.
* **Hashing**: Creates a unique "digital fingerprint" for data that cannot be reversed.

***

#### **Encryption: Locking Up Data**

1. **How It Works**:
   * Data is **encrypted** (locked) using a secret key.
   * To use or read it, you need to **decrypt** (unlock) it with the correct key.
2. **Types of Encryption**:
   * **Symmetric Encryption**: One key does both locking and unlocking.
     * Analogy: A house key that locks and unlocks the same door.
   * **Asymmetric Encryption**: Uses two keys—a **public** key (locks) and a **private** key (unlocks).
     * Analogy: A mailbox—anyone can put mail in (public key), but only you can open it with your key (private key).
3. **Use Cases**:
   * **Data at Rest**: Protects stored data (e.g., databases, hard drives).
   * **Data in Transit**: Protects data being sent (e.g., HTTPS for websites).
   * **Data in Use**: Protects data in temporary storage (e.g., RAM).

<figure><img src="../../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

***

#### **Hashing: Fingerprinting Data**

1. **How It Works**:
   * Hashing takes any data and produces a fixed-length value (a "hash").
   * The same input always gives the same hash, but it can’t be turned back into the original data.
2. **Use Case**:
   * **Password Storage**: Instead of storing your actual password, systems store its hash. When you log in, the system hashes your input and checks if it matches the stored hash.
3. **Salting**: Adds random data (a "salt") to passwords before hashing to create unique hashes, even for the same password.

***

#### **Key Differences**

| **Feature**     | **Encryption**                           | **Hashing**                          |
| --------------- | ---------------------------------------- | ------------------------------------ |
| **Purpose**     | Protect data so it can be decrypted.     | Create a unique identifier for data. |
| **Reversible?** | Yes (with the key).                      | No, irreversible.                    |
| **Uses**        | Data protection (e.g., files, websites). | Authentication (e.g., passwords).    |

***

#### **How to Remember This**

1. **Visualize It**:
   * Encryption = A locked box + key.
   * Hashing = A fingerprint—unique but can’t be reversed.
2. **Chunk It**:
   * Learn encryption today, hashing tomorrow.
3. **Mnemonics**:
   * **E = Encryption = Encrypt & Decrypt.**
   * **H = Hashing = Hard to Reverse.**
4. **Explain It**:
   * Teach a friend or yourself (out loud) with analogies!

***

#### **Key Takeaway**

* **Encryption** = Protect data by locking it; reversible with the right key.
* **Hashing** = Create a unique, irreversible fingerprint for data. Both are critical for cybersecurity!

<figure><img src="../../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>
