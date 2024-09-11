---
description: "About the design of My Book."
long_title: "Markdown Book Project Reflections - Zhifeng"
---

# Markdown Book

Since the freshman year of university, I have been thinking about ways to demonstrate my college life, personality, and thoughts. Compared to a technology problem, building a website is more like a life-long question about what's our most-valued things, how to present it, and how to sustainably build upon previous works. There are too many fancy different frameworks comming out every day. How to sustainably build new stuffs upon the old ones is an important question to consider.

Different people value different things the most. Those things are likely to be able to present in photos, audios, videos. These formats have already captured most of the human experiences. But if you want to convey a piece of cognitive learning behavior, maybe the only way to deliver that is through games or other interactive stuff. That's also a reason why I want to learn web design.

It's indeed a long journey. I started to learn and iterate my website design from my freshman year, 2021 Fall. I remember I made a small demo of a tiny discussion forum, hosted it with GitHub pages, and let my classmates access it with a QR code. It didn't have a backend. All the posts are on the user's devices, but still, it's my first web development experience.

I started to learn web development with a bunch of Coursera Courses about HTML, CSS, Javascript, and Angular. Later, aiming to display and demonstrate my network/graph visualizations, I took the ThreeJS course by Bruno Simon. Inspired by the idea and convenience of React-Three-Fiber, I learned React via its well-designed official website. Two years from 2021, in Fall 2023, I learned NextJS. Inspired by the style and idea of the Rust book, I finally made this website.

Now, August 2024, I finally managed to make my own static website renderer with vanilla HTML, CSS, and JavaScript.

# Inspirations

The design of this website is inspired by the [Rust Book](https://rust-book.cs.brown.edu/) and IS445, CS307, and various course and documentation websites. Using Markdown to write web contents in a human friendly way (both reader and writer) is the key consideration of this design.

# Design: Tech Part

After several drafts of my personal website, here are some of the key points of the technology part of my design, mainly about balancing sustainability and fanciness, code and text content, etc. I have a general pattern of building personal websites: think about it, implement it, and start over. So, I guess the important part would be how I can make more reusable components and finally settle in some design that I can constantly add new both tech contents, like visualizations, and text contents.

## Balancing Tech & Visualizations and Texts

I want my website to be a platform for visualizing various ideas and text-based reflections and thoughts. From my previous experiences of creating demos, I find it pretty hard to combine fancy visualizations, maybe 3D visualizations, with detailed explanations and reflections.

## Flexibility and Transparency

I want my website to painlessly add my future new visualizations in various forms and gadgets on the website and be easily adaptable to potential future tech or web frameworks. I hope that when I have new ideas to visualize and embed into the websites with reflections, I won't need to worry too much about the layout, the theme, or how to embed them into the previous works. Such that I can focus on creating exciting new content instead of how to combine and align them with my earlier works.

## Content driven

One of my considerations about how to build my personal website is that it should be content-driven instead of showing off fancy technologies, animations, and layouts. I agree that there are many impressive personal websites demonstrating their builders' excellent control of elements in 2D with CSS and 3D with ThreeJS and shaders. However, I would also like to focus on reflections on various things, like writing and reading reflections. I feel chasing the optimal combination of new technologies and layouts is seemingly endless to me. I feel I might somehow lose focus in some way during that process. Like, yes, fancy effects and animations can reflect on my skills (which I don't have). But I want to focus more on my personality and my reflections.

In addition, the content creation process should be more human-friendly instead of machine-friendly. Thinking back, before the current version of my website, I was always typing paragraphs between a bunch of HTML tags, which is not, in my opinion, human-friendly enough.

# Design

Learned from IS310 and INFO303, I find it's also important to balance between machine-friendly and human-friendly. To achieve this and the goal of content-driven, I choose to use file structures and Markdown files as intermediate representations of my website. Then, I used the features of the Markdown design to embed the information of my custom web components into the Markdown file. Therefore, I can render them into a static sustainable website.

Furthermore, learned from INFO303, it's important to consider the process of transforming writing styles between different modals. With the web, the audience might jump between pages. I might also directly share a web page in the middle with someone. I'm still thinking about the content structure design. I'm planning to mimic the Barnes-Hut tree, at least from my understanding. There would be a linear section that holds my thoughts corresponding to the time, as well as a hierarchical section that archives the contents with topics.

## Recent Updates

For April and May of 2024, the main design problem would be the design and architecture of pages of two language. Previously, I was writting the content of two different language in the same Markdown file, using weird custom separator to distinguish the parts of content. But this design is not that natural and not following the native Markdown syntax.

From the angle of my writing experience, separating the content of different languages into different Markdown files is more natural. I realized that I don't need the exact same structure between the two language parts. I guess only a few audiences might try to cross-read between the contents. The process of switching the architecture is relatively simple because of my previous relatively atomic design. The first step of the program would be scanning through the directives and building a tree of web pages. Previously, I scanned one set of files and then separated the contents into two sets of webpage trees. Now, with the content already separated, constructing a single webpage tree is indeed more natural.
