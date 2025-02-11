---
description: "The second month of 2025."
long_title: "Feb. 2025 - Diary - Zhifeng"
---

# February 10th

Today, I have done a lot of clean-ups. I wiped the stove and the kitchen table, shaved my hair, etc.

One interesting bug I have encountered was the End-of-File. When I was reading the documentation, I wondered why there is an extra "s" character before the `size_t` (`ssize_t`). Later, when I was trying to check whether there is such a character inside the read C string from the `getline`, I noticed that the "read length" became the hexadecimal "ffffff....ffff". After further checking documentation about the End-Of-File, I suddenly realized that the weird number is just "-1". So that's what the extra "s" means (or maybe I'm wrong again, and that's not about "signed"). I'm grateful that I, for some reason, tried to print out the "read length."
