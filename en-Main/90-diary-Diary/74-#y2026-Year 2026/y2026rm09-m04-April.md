---
description: "April 2026."
long_title: "April 2026 - Diary - Zhifeng"
---

# Friday, April 17th

Today's main problem-solving was about the out-dir file marking. In my "mdtome" project, I employed a tree data structure to keep track of, during the website generation stage, which files in the "out" or "destination" directory are valid. When redesigning the "encapsulation" structure, instead of the previous desgin of combining two navigation menu in the gate node webpage(which is the root of the "encapsulated" content) I chose to divide the gate node webpage into two, one as a "leaf" ".html" of the parent tree, and one as the "index" of the "encapsulated" tree.

However, this change breaks the previous "out" directory file marking. Previously, the marking would concatenate the "URL slugs" with one final "index.html" at the end. For example, "/foo/bar" will mark the "/foo/bar/index.html". But now, I also need to mark the "/foo/bar.html" for these "encapsulation root" pages. I need to change the handling logic of the last "URL Slug".

Adding some depth tracking or flagging the last "URL slug" might need to change one of my "prefix tree" implementations and add an extra "if". I decided to add a "previous URL slug", stalling the previous iteration logic by one and handling the last one manually. It seems this logic can solve the problem.
