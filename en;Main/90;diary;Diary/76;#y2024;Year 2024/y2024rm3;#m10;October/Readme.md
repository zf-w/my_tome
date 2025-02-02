---
description: "This page is Zhifeng's Study Diary of October 2024."
long_title: "My October - 2024 - Study Diary - Zhifeng"
---

# October 2024

## Personal Study

### Using Octree to Pinpoint Nodes

I have been planning and dreaming about how to reversely get node information from the 3D graph for a long time. I'm not a fan of using my mouse to click on those tiny dots on the point and use 3D library's raycasting methods to find the node. Also, since I'm using points to render the 3D scene, I'm not sure how easily I can get the node index from the 3D library. I choose to use the Octree to find the state information of a dot. It's generally fast (I believe `O(log(number of nodes))`), fairly easy to implement solely by myself (and the interface), and I can reuse my previous implementation of `Barnes-Hut Tree`.

### Authentication

One theme of my personal study for October is web authentication. Authentication is an important and interesting topic. I have learned a bit of authentication with `Express.js`, `MongoDB`, and `JavaScript`. It's time to try to implement and experiment with authentication functionalities on my own.

Thinking about authentication without those high-level abstractions is quite intriguing: all the byte manipulations, encryption-decryption, and hash algorithms on both the client side and the server side. I feel pretty gracious that two implementations of the same algorithm in different programming languages actually function the same. This experience deeply resonates with my current learning of CS233 of UIUC: Computer Architecture. Computers are based on the conventions of register usage among developers, at least in the old times.

Even though this miracle completely resulted in conventions, rules, and orders of computer programming, I still feel gracious and surprised that there truly exists such a field that makes multiple layers of developers sync in a fairly accurate way. I wonder if that is also a somewhat social construct. How is it possible that such a large number of people (or not a lot for the core implementations) actually think the same thing? As I'm writing this, I feel more and more surprised that my design (atop of hash algorithms and encryption algorithms of others) actually worked.

### Style Customization

I render this website mainly using my own static website generator. How to control the layout, style, and basic elements is important for making a website in two languages. I do not prefer to add multiple `if`'s before every title. How to make the developer's (which is...just...me) composing and developing more comfortable is another major concern of my `mdtome` project.
