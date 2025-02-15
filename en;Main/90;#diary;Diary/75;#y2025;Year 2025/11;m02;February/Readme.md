---
description: "The second month of 2025."
long_title: "Feb. 2025 - Diary - Zhifeng"
---

# February 13th

For the past several days, I have been mainly working on CS341's MP Shell (including Leetcode daily problems). The experience was great. But it can be a little sad when I can't learn which part went wrong (but, luckily, I guess such things will never happen if you are just developing your own stuff.)

I'm slowly redesigning how I keep track of the mini-problems I solved.

I'm planning to make a "sorry_and_thx" and "worldview" pages.

Several days ago, in County Market, I noticed that some careful people rearranged all the items on the shelf. I deeply appreciate their efforts.

# February 12th

Yeah! Snow!

# February 10th

Today, I have done a lot of clean-ups. I wiped the stove and the kitchen table, shaved my hair, etc.

One interesting bug I have encountered was the End-of-File. When I was reading the documentation, I wondered why there is an extra "s" character before the `size_t` (`ssize_t`). Later, when I was trying to check whether there is such a character inside the read C string from the `getline`, I noticed that the "read length" became the hexadecimal "ffffff....ffff". After further checking documentation about the End-Of-File, I suddenly realized that the weird number is just "-1". So that's what the extra "s" means (or maybe I'm wrong again, and that's not about "signed"). I'm grateful that I, for some reason, tried to print out the "read length."
