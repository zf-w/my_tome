---
description: "February 2026."
long_title: "February 2026 - Diary - Zhifeng"
---

# Thursday, Feb. 19

I guess writing a diary is somewhat about temporal locality: if you don't log your memories constantly, some of them might get overwritten.

# Monday, Feb. 16th

I have incrementally cleaned two areas of the floor. I noticed that the design of floor pieces could be aligned with the area a person can sweep in the crouching state. Maybe this kind of floor design can be called "ergonomic floor design." I have also swept and mopped a dusty area on the windowsill.

# Sunday, Feb. 15th

I went to confirm the recyclable plastic bag drop-off bin. What's a little bit embarrassing is that the same staff from yesterday's "ice-cream incident" was on duty, and I had to ask him again about the recycling bin. Fortunately, this time things went pretty smoothly. I'm grateful. I hope I was not too interrupting. Considering reducing my use of tin foil caps, I went to dine in instead of take-away. It went smoothly.

# Saturday, Feb. 14th

When I was shopping at Target, I noticed that there was an abandoned ice cream next to a self-checkout machine. I guess somebody suddenly decided to not purchase that during check-out. After I had finished my check-out, I notified a staff member that there was an ice cream left there. Somehow, the staff misunderstood me and thought I was talking about a fire alarm that went off. I'm sorry about that. I guess that was due to the word "unattended" in my sentence? Maybe normally the dot product of that word's vector with fire alarm's is larger than ice cream's. After my further attempt at clarification, he followed me to the ice cream and found that it had already melted. I said I'm sorry and left.

# Tuesday, Feb. 10

There were some puddles of water on the way to County Market (Niemann). People are all willing to let the other side go first. I'm grateful for that.

# Saturday, Feb. 7th

Working on wiping the stove top, cleaning living room table, and cooking steak.

# Thursday, Feb. 5th

I was thinking about using a bad "number of items" to offset the stack address in a desirable way.

# Wednesday, Feb. 4th

In the evening, I spent some time working on the MP1 Application Security of CS461. In general, the process was quite smooth and rewarding. My code triggered a Segment Fault for Question 1.2.2. After some investigation, I realized that "gets" puts an "end of string" at the end of the string, turning the following jump memory address into an incorrect address. The interesting story is, I guess, I didn't correctly construct addresses with "little endian", triggering the first Segment Fault. While I was trying to figure out the cause of that, I commented out a padding of 4-byte data to let the jump memory address fall into the "$ebp" register, but that led to the "end of string" overwriting the jump address byte.

When thinking about 1.2.2, I realized my have made a mistake in 1.1.1.
