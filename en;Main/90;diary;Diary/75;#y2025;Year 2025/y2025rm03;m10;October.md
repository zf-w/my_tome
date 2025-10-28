---
description: "October 2025."
long_title: "October 2025 - Diary - Zhifeng"
---

# Monday, October 27th { #y2025m10d27 }

One of the main tasks for today is to visit the "CS423 Operating Systems Design" office hours and see what it is like. Throughout the office hour, the TA has pointed out one critical misunderstanding of mine about the usage of scheduler APIs. I'm grateful that I decided to visit the Office Hour. This is my first time visiting Office Hours in these years. I hope I didn't offend anyone.

## The deadlock in yield { .debugging }

One interesting bug I found today was about the "yield" function implementation for the MP2 of CS423. After I implemented the correct procedure to put a process into the sleeping state, I found that the dispatching thread was blocked forever. I guessed there might be a deadlock somewhere, and I turned out to be correct. Releasing the locks before waking up the dispatching thread and putting the process to sleep is very important. Otherwise, the yield function will be blocked before releasing the lock while the dispatching thread is desperately trying to grab it.

# Sunday, October 26th { #y2025m10d26 }

One main task being scheduled today is working on the "CS421 Programming Languages and Compiler" Machine Problem 7. This homework is mainly about implementing the "unification" algorithm in the type inferencing problem. Designing recursive functions to iter through list and tree data structure is quite interesting. Familiaring with Ocaml, I appreciate the insights of pattern matching in Rust-lang, that pattern matching design indeed provides a sense of clean and organization.

# Wednesday, October 15th

During lunch, I noticed a girl who seemed unsure where to return her tray and left it on the table. I returned it for her, feeling grateful to the person who helped me the first time I visited the restaurant. Later, though, I wondered if I might have been blocking her view of the return cart.

# Tuesday, October 14th

Today's "CS421 Programming Languages and Compilers" lecture was about type derivation theories and algorithms.

Through out today's "CS423 Operating Systems Design" lecture, I have learned and reviewed concepts about page tables and radix trees.

# Saturday, October 11th

I have taken the Sexual Misconduct Prevention Training program for graduate students at UIUC today.

> # What is a "good" relationship?
>
> Our values influence our relationships. Most of us seek out and want "good" relationships - with family, friends, colleagues, and in dating or more intimate relationships and partnerships. But what exactly is a "good" relationship?
>
> - Honesty: being truthful, genuine, and sincere in your words and actions.
> - Individuality: valuing the things that make us unique, including encouraging one another to pursue professional goals, explore personal interests, and spend time with friends.
> - Respect: accepting someone for who they are and what they stand for, including their boundaries.
> - Trust: having confidence in someone; feeling physically and emotionally safe with them.
> - Communication: exchanging thoughts and ideas in an honest and open manner; speaking up for yourself while respecting the right of others to do the same.
> - Maturity: staying calm and thinking clearly in difficult situations; being open-minded and accepting constructive criticism; taking responsibility, and accountability for individual actions.

## Room showing

The apartment office has arranged a room showing for prospective residents. I'm grateful that the staff asked about my preference for footwear before entering the room. I'm thankful for the respectful gesture.

# Friday, October 10th

I finally have some time to review and clean my previous diary entries. I'm always hoping that I can somehow document my journey of learning. On the one hand, I can use this chance to write something, note something, and probably reduce some overthinking. On the other hand, I can probably use this chance to make my journey of learning computer science more transparent, in the hope that it might help the others with a similar interest. Even though I guess my learning journey, or say, work-life balance is not normal, I guess these records can still be interesting for some readers, perhaps future archeologists.

When I was reviewing my old diary entries, I realized that I had already been writing in the very style I'm now hoping to adopt. It's just that I didn't manage to keep the habit going. Now, I have learned more about operating systems, file systems, etc. I think I might be able to maintain the habit this time.
