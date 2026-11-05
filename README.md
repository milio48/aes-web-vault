# AES Web Vault 🔒

A lightweight, zero-dependency, client-side web application for securely encrypting and decrypting sensitive text (like environment variables, passwords, or secret notes) using the native Web Crypto API.

## ⚡ Features
- **Zero Dependencies:** No external libraries (CryptoJS, Forge, etc.). Uses 100% Vanilla JS and the browser's native `window.crypto.subtle`.
- **Military-Grade Security:** Uses AES-GCM (256-bit) with PBKDF2 (100,000 iterations) for key derivation.
- **Dynamic Salt & IV:** Every encryption generates a unique Salt and Initialization Vector, making pattern analysis impossible.
- **Client-Side Only:** No backend, no API calls. Your data never leaves your browser.
- **Single File:** Everything is bundled in one `index.html` file.

## 🚀 Live Demo
Try it here: [https://milio48.github.io/aes-web-vault](https://milio48.github.io/aes-web-vault)

## 🛠️ How to Use
1. Open the application.
2. Enter a strong **Password / Secret Key**.
3. Paste your text in the **Input Data** box.
4. Click **Enkripsi ➔** to get the Base64 cipher, or **Dekripsi ➔** to read an encrypted cipher.
5. Keep your password safe. If lost, the encrypted data cannot be recovered.

## 📝 License
MIT License
