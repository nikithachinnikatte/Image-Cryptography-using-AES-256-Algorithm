# Image Cryptography using AES-256

This project implements a secure image encryption system using the **AES-256 encryption algorithm in CTR (Counter) mode**. The goal of the project is to demonstrate how strong cryptographic techniques can be applied to protect digital images from unauthorized access.

The system encrypts each RGB channel of an image separately and then reconstructs the encrypted image. The encryption strength is evaluated using security metrics such as **Entropy, Mean Squared Error (MSE), and Number of Pixels Change Rate (NPCR)**.

---

## Project Objective

The main objective of this project is to build and evaluate an image encryption system using the AES-256 symmetric encryption algorithm.

The project focuses on:

- Encrypting image data using **AES-256 in CTR mode**
- Applying encryption separately to **RGB channels**
- Evaluating the security of the encrypted image
- Analyzing the randomness of the encrypted output
- Reconstructing the original image through decryption

---

## Technologies Used

- Python  
- NumPy    
- PyCryptodome  
- Matplotlib  

---

## How the System Works

The implementation follows the steps below:

### 1. Image Loading
An RGB image is selected and loaded into the program using Python. The image is converted into a NumPy array for processing.

### 2. Channel Separation
The RGB image is divided into three individual channels:
- Red
- Green
- Blue

Each channel is encrypted independently.

### 3. Key and Nonce Generation
For each channel, the program generates:
- A **256-bit AES encryption key**
- An **8-byte nonce**

These values are randomly generated to ensure strong encryption.

### 4. Encryption
Each channel is converted into bytes and encrypted using **AES-256 in CTR mode**.

CTR mode works by generating a keystream using a counter and nonce, which is XORed with the plaintext data to produce encrypted output.

### 5. Decryption
Using the same key and nonce, the encrypted data is decrypted to restore the original image data.

### 6. Image Reconstruction
The decrypted Red, Green, and Blue channels are combined again to reconstruct the final image.

---

## Security Evaluation Metrics

To evaluate the strength of encryption, the following metrics are used:

### Entropy
Entropy measures the randomness of the encrypted image.

- Ideal value for an 8-bit image ≈ **8**
- A higher entropy value indicates stronger encryption.

### Mean Squared Error (MSE)
MSE measures the difference between the original image and the decrypted image.

Lower values indicate accurate reconstruction.

### NPCR (Number of Pixels Change Rate)

NPCR measures how sensitive the encryption algorithm is to small changes in the original image.

For strong encryption:
- **NPCR should be greater than 99%**

---

## Histogram Analysis

Histograms are generated for both the original and encrypted image channels.

- Original images show **distinct pixel distribution patterns**
- Encrypted images show **uniform distributions**

This indicates that the encrypted image does not reveal any information about the original image.

---

## Expected Output

After running the program, the following outputs are generated:

- **Encrypted Image**  
  Appears as random noise with no visible patterns.

- **Decrypted Image**  
  Nearly identical to the original image.

- **Histogram Plots**  
  Used to analyze pixel distribution.

---

