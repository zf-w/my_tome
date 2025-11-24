---
description: "November 2025."
long_title: "November 2025 - Diary - Zhifeng"
---

# November Reading

| Publish Year | Title                                                                             | One-line Note                                                                 |
| ------------ | --------------------------------------------------------------------------------- | ----------------------------------------------------------------------------- |
| y2016        | Context Encoders: Feature Learning by Inpainting                                  | Using encoder, decoder, and adversarial loss to fill missing parts of images. |
| y2016        | Man is to Computer Programmer as Woman is to Homemaker? Debiasing Word Embeddings | Debiasing gender biases in vector word embeddings.                            |

# Daily Learning

## Sunday, November 24th { #y2025m11d24 }

The major learning task for today was the MP10 for CS421 Programming Languages and Compilers. The Machine Problem was about writing code to evaluate a parse tree into values, "executing the code". I'm grateful to see and touch on the rules of evaluating different expressions. I think the way to evaluate recursive functions is the most interesting one: we must reinsert the function identifier into the function expression code into the environment every time we try to evaluate the recursive function application call.

I have cleaned the counter and stove top. I'm thankful to these food and plastic packages and their designers and manufacturers for supporting my way of life and my roommates' way of life.

## Saturday, November 23rd { #y2025m11d23 }

I'm thankful to the local bus showing a "Have a good break" message on its head LED display.

## Tuesday, November 18th

One of the major task for today was to complete MP9 PicoML Parser for CS421 Programming Languages and Compiler. I was going to give up since last Thursday, but I still decided to give it a try. After I have carefully reviewed the autograder feedbacks, I found that the problem I was struggling thinking it through with wasn't included in the test cases, and the existing testcases can be almost perfectly passed by my solution.

## Monday, Novemeber 17th

One of the major task for today was to finish the main coding part of the MP3 Memory Fault Profiler of CS423. The most challenging bug I have encountered was "mutex_lock_uninterruptible implicitly defined". I have tried to reordered my include sequences and what not, but these changes didn't work. In the end, I pasted the source code of the mutex lock into the corresponding source file on my machine, and the bug was then fixed.

## Thursday, November 13th

One of the biggest challenges in my recent learning would be the disambiguating parsing part from CS421 Programming Languages and Compilers. In my current understanding, disambiguating the parsing process is about carefully designing the grammar tree to ensure clarity. For example, when parsing "1 \* 2 \* 3", by ensuring that a "\*" operator can only have an immediate "\*" subtree on its left, we can ensure the multiplication operator's left-associative property. Now, I'm struggling with how to parse things like `2 * if x = true then 1 else -1 + 3`. I'm currently forbidding the end expression of a multiplier's right "if" statement to include lower precedence operators to avoid shift-reduce conflicts. But I guess that is not the desired behavior...

## Thursday, November 6th

Today's learning was mainly focusing on parsing algorithms and page table mechanisms in virtualized systems.

I'm thinking about the best ways to document past assignments in my learning journey. Reviewing CS341 and CS225, I noticed there were indeed many week-long thoughtful and playful assignments. I'm grateful to the instructors for developing these well-designed Machine Problems that helped solidify our learning.

## Tuesday, November 4th

One main theme for today was reviewing CS440 Quiz 5 (Neural Networks and Word To Vector) and reading "_Context Encoders: Feature Learning by Inpainting_" and "_Man is to Computer Programmer as Woman is to Homemaker? Debiasing Word Embeddings_". I'm grateful for Prof. Fleck’s efforts in highlighting issues of humanity, justice, and fairness within the field of computer science.
