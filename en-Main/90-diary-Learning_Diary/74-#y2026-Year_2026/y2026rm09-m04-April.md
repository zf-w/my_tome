---
description: "April 2026."
long_title: "April 2026 - Diary - Zhifeng"
---

# Thursday, April 30th

I'm grateful that the professor and a classmate said some kind words about my project presentation. I need more practice for sure. I talk to computers more than I talk to humans.

# Wednesday, April 29th

I have been trying to understand the Mitnick Transmission Control Protocol (TCP) spoof technique for a few hours. One misconception I encountered was about the Internet Protocol (IP) address-based authentication. I thought this technique was about dropping all packets from unauthorized IP addresses. I'm grateful that I decided to chat with LLMs before writing code that simply tries a lot of potential acknowledgment sequence numbers. After some search and chat, I realized that the attacker can still make a TCP first handshake synchronization and get the server's Syn-Ack packet.

From last semester's CS423, I learned that one of the major sources of bugs inside operating systems is from programmers' copying and pasting, copying code from a seemingly similar context, and solving seemingly similar problems. Even though I have experienced this a lot, it is still interesting to see this issue happen. The exact thought even flashed in my mind, but I still forgot to change the "client" into "server" in a function name when I was copying code from the server's part of the implementation several lines above, leading to the attacker-in-the-middle client sending the true client's request back to itself.

# Friday, April 24th

The main project development challenge for today is about loading custom "apps" in my "mdtome" Markdown rendering program.

## Designing

Previously, I have been using a JavaScript Object Notation (JSON) file to define all the custom "apps" and their dependency relations. Time has passed like a wild donkey. The JSON definition started to be a little bit less maintainable, and the previous "app" naming format is a little bit less than ideal.

I have been using "app names" to define their relative files in addition to, well, the name. For example, application "foo_bar_hello_world" would be expected to live in "/src/foo/bar/hello/world.js". After some field practices, I feel that the design has some room for improvement.

First, I feel like the meaning of these directories becomes hard to remember after some time. My internal states have changed, and I guess I'm not always able to recall my naming intuitions. Also, sometimes I would like to use names with underscores in them, but using underscores as separators makes this hard to happen. Furthermore, Git (at least for the VSCode sidebar) only displays the last segment, the name of the file, and that is not helping me figure out which file is for which "app".

So I decided to use the "temporal locality focused" naming convention, using only the first two segments as an indicator of relative path. For example, now "y2026_m04_foo_bar"'s file would be living in "/src/y2026/m04/foo_bar.js". I guess this would indeed be more natural for me.

# Tuesday, April 21st

The main learning for today was about Transmission Control Protocol and Address Resolution Protocol.

I'm grateful that the four previously hatched Canadian goose goslings on the creek bank are doing well after the recent temperature drop.

# Sunday, April 19th

Today's main problem-solving was about redesigning the page customization design. Previously, to keep all the relevant Hyper Text Markup Language parts in one file, I chose to store all HTML parts in a list of strings, where each string represents a line of HTML. I do feel it's a bit unnatural and is preventing me from utilizing Integrated Development Environments.

I have redesigned the design, storing these customization HTML parts in some other files. The redesigning process is quite pleasant. I'm grateful that the Rust programming language has "Option::ok_or" and "Result::ok" design to make error handling tidier.

The main problem I encountered was still about the URL segment handling. Since, in the current design, a series of URL segments can represent either ".html" or "index.html" files, some older designs needed to be updated accordingly.

# Friday, April 17th

Today's main problem-solving was about the out-dir file marking. In my "mdtome" project, I employed a tree data structure to keep track of, during the website generation stage, which files in the "out" or "destination" directory are valid. When redesigning the "encapsulation" structure, instead of the previous desgin of combining two navigation menu in the gate node webpage(which is the root of the "encapsulated" content) I chose to divide the gate node webpage into two, one as a "leaf" ".html" of the parent tree, and one as the "index" of the "encapsulated" tree.

However, this change breaks the previous "out" directory file marking. Previously, the marking would concatenate the "URL slugs" with one final "index.html" at the end. For example, "/foo/bar" will mark the "/foo/bar/index.html". But now, I also need to mark the "/foo/bar.html" for these "encapsulation root" pages. I need to change the handling logic of the last "URL Slug".

Adding some depth tracking or flagging the last "URL slug" might need to change one of my "prefix tree" implementations and add an extra "if". I decided to add a "previous URL slug", stalling the previous iteration logic by one and handling the last one manually. It seems this logic can solve the problem.
