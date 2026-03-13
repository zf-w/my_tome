---
description: "March 2026."
long_title: "March 2026 - Diary - Zhifeng"
---

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
