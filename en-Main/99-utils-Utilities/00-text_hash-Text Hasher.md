---
description: "A textual message hashing utility tool for creating 'digital fingerprints' using the browser's built-in SHA-3 hash algorithm."
long_title: "Message Hasher- Util - Zhifeng"
---

# SHA-3 Text Hasher

```json#y2026_m03_sha3.y2026_m03_sha3
{}
```

# Usage

You can just type in or paste texts into the textbox above and copy the hash value "fingerprint" from the topmost box.

# Idea

You can think of this as some kind of blender, breaking your texts "fruits" into "juice". The funny blender promises that you will get completely identical cups of "juice" if you put in the same "fruits" in the same order, and you will not get similar "juice" even if there are only subtle differences in the fruit. In other words, it guarantees that there is no way to rebuild or even find what "fruits" you have put into the blender based on the "juice."

More magically, no matter how many "fruits" you put into the blender, you will always get the same amount of juice. (a little bit irrelevant but interesting)

# Daily Examples

## Apology Utility

Suppose you have accidentally said something that might be potentially offensive to a particular group; you want to apologize but also don't want to remind them about the specific offensive point if they haven't thought about that.

You can use the above tool to create the "digital fingerprint" of your apologizing message and send it to the group first. If, unfortunately, they indeed find that offensive point, you can show them your previous written apology message and prove that you are genuinely sorry about that immediately after the words coming out.

I guess, in almost all cases that I can think of, just directly apologize to the group might be a more effective and more straightforward solution. But who knows.

## Rock, Paper, and Scissor with Email

If Alice and Bob try to play "Rock, Paper, and Scissor" online only using text messages or mailing, whoever first sends the game move message, i.e., "I play Rock", will always lose the game because the other player learns their move. Entirely counting on whether both players are trying to send the message simultaneously might also not be ideal.

With the hasher above, the players can hash their message with some "secret" texts, e.g., "this is Alice 7m9a9e95, and Bob will never know I typed this before my actual action: Rock." get the hash value "fingerprint," and send that to the other player.

After both players receive their opponents' game move "fingerprint", they can reveal their game move text message and check if their opponent's move message's "fingerprint" matches with the previously-sent game move "fingerprint."

Assuming it's tough or almost impossible to find three secret messages respectively representing "Rock", "Paper", and "Scissor" but having the same "fingerprint", this method might enable people to play "Rock, Paper, and Scissor" "online", e.g., with paper mail.

In addition, people can also pick three different values representing "Rock", "Paper", and "Scissor" to make finding a "collision" harder at least in a short period of time, for example, "In this game, we will use 'hwuiqjinxin' to represent 'Rock'."

# Transparency and Implementation

I'm experimenting with using WASM on webpages. Instead of using the "crypto" library in browsers, I'm trying to learn the implementation details of these Secure Hash Algorithms. The implementation might not be completely secure or correct. I will not transmit any data to remote servers, but still, the more caution the better, especially when entering sensitive information. This page should be able to run without an Internet connection.

# Note

I'm sorry if you find this content confusing. Feel free to let me know what can be improved.
