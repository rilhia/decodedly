![Main Header Logo](images/decodedly.jpeg)
# Decodedly — Spy-Craft Edition

*Public Transmission → Hidden Intelligence*

---

## What Is This?

Decodedly is a browser-based steganography tool inspired by the classic espionage concept of the newspaper code.

In traditional spy tradecraft, a secret agent might extract a hidden message from a mundane public text by applying a unique key. Decodedly recreates this mechanic using a variation of the Vigenère cipher, with one deliberate design choice: both the cover text and the hidden message are real, readable, meaningful content. You are not encrypting gibberish into gibberish. You are hiding something real inside something real.

No installation. No server. No data leaves your browser.

---

## How It Works

Decodedly uses a character-level substitution cipher. Each character in the hidden message is encoded using the corresponding character in the cover text and a generated key. The key is derived mathematically from the relationship between the two inputs.

The cover text must be longer than the hidden message. Only the first portion of the cover text (up to the length of the hidden message) is used in the encoding process.

All characters in the printable ASCII range (32 to 126) are supported.

---

## Using the App

### Hiding a Message

1. Paste your **Public Cover Text** into the first field. This is the innocent-looking text your message will be hidden inside. A news article, a blog post, a press release — anything will do, as long as it is longer than your secret.
2. Type your **Hidden Message** into the second field.
3. Click **Generate Key**.
4. Share the generated key, or copy the shareable URL which has the key embedded in it.

Your contact will need the cover text and the key to decode the message.

### Revealing a Message

1. Paste the **Public Cover Text** into the first field.
2. Paste the **Secret Key** into the key field (or open the shareable URL, which loads the key automatically).
3. Click **Decode**.
4. The hidden message will appear in the Hidden Message field.

### Custom Encoding

If you already have a key and want to encode a message manually, you can use the **Encode (Custom)** button. This takes your hidden message and key and produces the corresponding cover text output.

---

## Shareable Links

When you generate a key, Decodedly automatically produces a shareable URL. The key is base64-encoded and appended as a query parameter. Anyone opening that URL will have the key loaded automatically. They just need to paste in the cover text to reveal the message.

---

## Constraints

- The cover text must be longer than the hidden message.
- Only printable ASCII characters (space through tilde) are supported. Characters outside this range are stripped silently.
- The key length matches the hidden message length exactly. There is no key stretching for the generate function, though the decode and custom encode functions will repeat a shorter key if needed.

---

## Running It

This is a single HTML file with no dependencies and no build step. Download it, open it in a browser, and it works.

```bash
git clone https://github.com/rilhia/decodedly.git
cd decodedly
open decodedly.html
```

Or open the file directly by double-clicking it.

---

## Limitations and Honest Notes

This is a fun project, not a hardened encryption tool. The Vigenère cipher has known weaknesses and this implementation should not be used for anything that requires serious cryptographic security. If you need real encryption, use real encryption.

What this is good for: hiding messages in plain sight, sharing private notes in a way that looks entirely innocent, and generally enjoying the aesthetic of Cold War tradecraft without leaving your browser.

---

## Licence

MIT. Use it, modify it, fork it. Attribution appreciated but not required.
