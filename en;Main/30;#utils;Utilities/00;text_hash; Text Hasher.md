---
description: "A textual message hashing utility tool for creating 'digital fingerprints' using the browser's built-in SHA-384 hash algorithm."
long_title: "Message Hasher- Util - Zhifeng"
---

# SHA-384 Text Hasher

```json#util_security_strhash
{}
```

# Usage

You can just type in or paste texts into the textbox above and copy the hash value "fingerprint" from the topmost box.

# Example Use Cases

## Apologizing Tool

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

The above component uses the SHA-384 from the Secure Hash Algorithm 2 family.

The following code will be run in your browser to generate the hash value "fingerprint." I'm simply using the implementation embedded in the browser, i.e., I'm not building the wheel from scratch, so it should be reliable.

```js
async function make_sha_2_384_hash_string_from_msg(msg_string) {
  const SHA_384_NAME = "SHA-384";
  const msg_u8_arr = new TextEncoder().encode(msg_string); // Turn texts into UTF-8 bytes
  const plain_hashed_arr_buf = await window.crypto.subtle.digest(
    SHA_384_NAME,
    msg_u8_arr
  ); // Generate the hash value
  const ans_hex_string = make_hex_string(new Uint8Array(plain_hashed_arr_buf)); // convert the hash value bytes into a hexidecimal string

  return ans_hex_string;
}
```

Furthermore, I'm not sending anything back to the server, but I guess it's important to emphasize that IP address should be considered as "Personally Identifiable Information," and my server (including a bunch of infrastructures and services) will receive that information.

Most importantly, I guess at least my instructors, classmates, and friends can always find me in person and check the source code.
