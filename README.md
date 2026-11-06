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

## 🛠️ How to Use (Web UI)
1. Open the application.
2. Enter a strong **Password / Secret Key**.
3. Paste your text in the **Input Data** box.
4. Click **Encrypt ➔** to get the Base64 cipher, or **Decrypt ➔** to read an encrypted cipher.
5. Keep your password safe. If lost, the encrypted data cannot be recovered.

## 💻 CLI Alternative (Linux / VPS)
If you are working on a headless server (like AWS EC2, Tencent Cloud VPS, or NAT VPS) and need to quickly encrypt/decrypt data without a browser, you can use OpenSSL. It is built-in to almost all Linux distributions.

*(Note: OpenSSL CLI uses AES-256-CBC, which is slightly different from the Web UI's GCM, but equally secure for text storage).*

### 1. Interactive Mode (Recommended)
This method prompts you to enter the password invisibly. **It prevents your password from being saved in your `.bash_history`.**

**Encrypt:**
```bash
echo -n "Your secret data" | openssl enc -aes-256-cbc -pbkdf2 -iter 100000 -a -salt

```

**Decrypt:**

```bash
echo -n "U2FsdGVkX1..." | openssl enc -d -aes-256-cbc -pbkdf2 -iter 100000 -a -salt

```

### 2. Inline Mode (Fast / Automation)

Use this if you need to script the process and do not mind the password being recorded in the terminal history.

**Encrypt:**

```bash
echo -n "Your secret data" | openssl enc -aes-256-cbc -pbkdf2 -iter 100000 -a -salt -pass pass:"your_super_secret_password"

```

**Decrypt:**

```bash
echo -n "U2FsdGVkX1..." | openssl enc -d -aes-256-cbc -pbkdf2 -iter 100000 -a -salt -pass pass:"your_super_secret_password"

```

## 📝 License

MIT License
