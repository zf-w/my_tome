---
description: "About the design of My Website."
long_title: "My Markdown Tome Project - Zhifeng"
---

# Markdown Tome: rendering websites from Markdown files

I was looking for a way to store and display my designs and visualizations accumulatively. After learning Next.js's idea of server-side rendering and the Rust [Rust Book](https://rust-book.cs.brown.edu/)'s content alignment and interactive code blocks, I feel I can render and combine markdown content files and my previous Three.js components into static webpages.

I love the idea of embedding visualizations in texts, sparing me for the trouble of writing "help" or "information" pages. I can then add my custom stuff in Markdown (without new syntaxs) like this:

```fun_galaxy
{
    "galaxy_param":{
        "branches":2,
        "inside_color": "#0000ff",
        "outside_color":"#fcbacb"
    }
}
```

# What did I do

- Designed a way to compose and describe custom components in Markdown and render them.
- Designed a way to represent website structure and encapsulation relationship with folder structures and naming patterns.
- Designed a way to represent custom components and manage CSS and JavaScript file dependencies.
- Implemented multiple prefix tree structures to express and handle the relationships between Markdown files, CSS files, and JavaScript files, Markdown file folder, source folder and output folder.
- Implemented a procedure to render navigation bars with a management of the encapsulated contents.
- Implemented a procedure to turn Markdown files in folder structures into webpages along with dependency files like CSS and JavaScript files.

# Diary

- **Sept 2024**: Updated the "Multi Scene One Canvas" design, enabling fullscreen.
- **Aug 2024**: The program started to work. I managed to switch my website to the new design.
- **June 2024**: I started to "clean room" and rebuild the idea using Rust-Lang.
- **November 2023**: I started to use Next.js to build my own "mdbook" rendering program.
- **September 2023**: I was inspired by Rust's official "mdbook" design and started to think about designing my own.

# Design Problems

- Goals:

  - How can we compose texts, visualizations, and other coding gadgets natrually without hardcoding everything everytime?
  - Is there an intrinsic way to accumulate codes, texts, and thoughts without having to refactor and rewrite everything every time?
  - How can we encapsulate large groups of content after they get too big, say 10 subtopics nested together.

- Website Structure:

  - How to design a folder structure pattern that naturally represent urls, page titles, and relative relations between webpages that allows us to render a menu bar and a next-page bar?
  - How to design the folder structure that allows us to get the url and title information without reading the file contents, letting us to skip reading and rendering up-to-date files?
  - What data structure can we use to represent the folder structures efficiently and allow us to quickly get the URL and title of respective Markdown files representing webpages?

- Webpage Render:
  - How can we naturally represent custom elements with Markdown's original syntax?
  - How can we handle the dependent files, codes, and stylesheets?

# Designs and Reflections

## Markdown Book

Inspired by the Rust-Lang "mdbook" projects and various course websites like "STAT107", "CS124, 128, 225, 307", I feel that rendering website from Markdown files is very promising. I used to make weird "help" pages for my visualizations, but I found that is not effective or flexible. With Markdown and embeded custom elements, I can write about reflections, directions, and descripitions along custom elements like 3D graph visualization or board games.

## From folders to website

I think maybe I don't need to use some configuration files to map files in folders to a URL and map URLs into a file path in the "public" folder. In that way, I might need to keep track of both the configuration file and the folder structures. Then, I thought maybe I can cut the third leg there and just use folder structures and folder-file names to represent website structure and necessary metadata for webpages.

## Using Prefix Tree to track Pages

Using prefix tree, we can efficiently represent the file structure and the relative file relationships for navigation.

## Custom Extensions

Inside Markdown files, I use code blocks to define my custom extensions, using the language name to define extension names.
