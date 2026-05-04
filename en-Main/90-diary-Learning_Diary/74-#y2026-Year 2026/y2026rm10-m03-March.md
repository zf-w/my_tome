---
description: "March 2026."
long_title: "March 2026 - Diary - Zhifeng"
---

# Tuesday, March 31st

I'm learning how to clean limescale in boiling pans with Large Language Models.

Today's Fortune Cookie: "A friend's advice is invaluable."

# Sunday, March 29th

Today's Fortune Cookie: "Travel often to see the world".

I'm learning how to implement SHA-3 (Secure Hash Algorithm 3) with Large Language Models. I'm also recycling plastic bottles.

One of the bugs for today was treating one 8-bit Unsigned Integer as 32-bit Unsigned Integer.

# Saturday, March 28th

I have been working on designing my large number division function.

# Friday, March 27th

- Change power calculation to "inplace" instead of using heap memory allocation.
- Study random number generation crate "getrandom" and find the part of code for getting safe random numbers from operating systems.

# Thursday, March 26th

Continue to think about the "inplace" design and naming problems.

# Wednesday, March 25th

I'm trying to use passing an array's mutable reference as arguments, instead of letting functions allocate in heap memory. Before implementation, I spent some time thinking about what might be the best way to name these arguments to remind me of their required relative length for the function to work normally. Just after naming the argument, I made such mistakes I anticipated and planned to avoid. I thought the length for the multiplication array was sufficient if it was twice the length of the "modulus". I forgot that the "base" might be long and the "divisor" needs to be as long as the "base"'s length to perform the remainder operation.

# Sunday, March 22th

When working on the "SQL-injection" homework for "CS461", I suddenly found out that I forgot to finishing probing every character of the database version string. I guess I became somewhat too excited and forgot to complete that.

# Thursday, March 19th

Today's main interesting bugs are:

- When right-shifting a byte array, I need to start from the top bytes; otherwise, if the shift amount is not large enough, the procedure might overwrite some bytes before shifting those.

- When calculating remainders, my current approach is to shift the divisor inside its array. However, when writing test cases, I didn't realize the final remainder result is likely smaller than the calculation needed, resulting in overflow when right-shifting the byte array.

# Tuesday, March 17th

I have been reading "Crypto 101", learning concepts like Length Extension Attacks for hash algorithm designs involving exposing internal states.

I have been reading example literature review documents.

I have recycled my previous three paper bags for my McDonald's purchases and receipts.

I'm grateful for the thank-you note on one of the receipts from 2025.

# Saturday, March 14th

- I have encountered several interesting bugs today. A 32-bit Unsigned Integer consists of four 8-bit Unsigned Integers, and I have only added the first byte into the result. I had to examine the hash states to finally find this issue.

- My current "index-related" variable naming habit is to add the name of the structure it is "indexing" as a prefix, for example, "prime_arr_idx". However, when finally returning the data, I guess the Integrated Development Environment suggested the index variable instead of the actual structure I planned to return, and I was typing a little bit too fast.

- At first, I didn't know that TOTP (Time-based One Time Password) key uses Base32 encoding to represent the key. I thought it was just the UTF-8 bytes of the key texts. After I wrapped the Base32 decoding function around the HMAC (Hash-Based Message Authentication Code), the TOTP results didn't match the expected ones. After carefully examining the intermediate results, I found mismatches start from the private key bytes. It turned out that I forgot to remove the previous UTF-8 encoding wrapper, and, instead of decoding the text string, the Base32 decoded the UTF-8 bytes.

# Friday, March 13th

Today, I have been reading through the source code of "sha1", "sha2" series, and "sha3" series, and trying to implement the core part of "sha1". I have encountered two major bugs. The first bug was about a typo in the code for a mechanism handling the first to the twentieth rounds. I guess it's relatively easy to make a typo when there are a lot of single-character variables. I guess short variable naming helps make expressions containing a lot of bitwise and arithmetic operations shorter. The second bug was about the endian for the digest byte representation.

It's also quite interesting to read the marcos for turning hexidecimal strings into constant byte arrays.

I have also encountered integer overflow bugs when I was solving the daily problem. The overflow bug led to weird binary search behaviors, because some positive numbers overflowed and turned negative and flipped comparisons.

# Thursday, March 12th

Today is a sunny day, but the temperature drops a lot. I caught a suspicious runny nose on the way to the midterm and had a bit of an awkward exam. I guess I should have brought some tissues with me (although I'm still unable to use them under exam conditions).

I have further studied the source code of one Rust implementation of the "md5" algorithm. It's quite exciting to see how each operation shifts and changes the state. While reading the source code for the Rust md5 crate implementation, I noticed that each of the four 32-bit states seems to be shifted back with a single modification after every four rounds of operations, and the process can be simplified to reduce the number of "swaps".

During the "reverse-engineering", the first bug I encountered was about the padding implementation. I felt quite satisfied when I realized that the one "bit" padding design can help distinguish between a single zero byte and many zero bytes, along with the final eight-length padding.

# Wednesday, March 11th

I'm grateful that I decided to double-check the receipt and notify the cashier about the forgotten payment for the drink.

# Tuesday, March 10th

I learned something new about setting up SSH config files: it turns out the "Host" field needs to match, not "HostName".

I've been reading through the source code for the MD5 (Message Digest 5) algorithm, which has been quite fascinating.

I've also been learning how to use the `tar` command to compress files from the command line.

# Friday, March 6th

**Champaign**. The temperature is getting warmer. In the morning, I spent some time polishing a web interface, learning that I can use a "div" with "flex" to push one other element to the bottom of its container.

I recycled four paper cartons, paper boxes, and plastic bottles. I'm grateful.

I have studied a bit about Cross-Site Request Forgery. I guess "iframe" is indeed a dangerous thing.

# Wednesday, March 4th

**Champaign**. Today is a foggy day. The main task I have been working on today was the CS461 MP2 CP2. It's quite interesting to think about how to pass multiple filters and perform XSS. My previous learning of Base64 encoding and decoding leaves me with some critical intuition for solving the problem.

One of the SQL-injection problems is about finding the correct plaintext to generate a desirable MD5 hash digest. I have always wanted to try to design something to find reverse hashes for creating interesting usernames. From a high-level point of view, the most difficult part of this problem would be to find a fairly less-demanding SQL-injection string. I have spent a lot of time looking for things generating the traditional "1=1" thing from the course slides. Though not fruitful, adding an additional piece of code to parse the numbers and allow "X=X" is also quite interesting.
