---
description: "Zhifeng's Diary of his Markdown Tome Project"
long_title: "Project Diary - Markdown Tome - Zhifeng"
---

# Project Diary

- **Sept 2024**: Updated the "Multi Scene One Canvas" design, enabling fullscreen.
- **Aug 2024**: The program started to work. I managed to switch my website to the new design.
- **June 2024**: I started to "clean room" and rebuild the idea using Rust-Lang.
- **November 2023**: I started to use Next.js to build my own "mdbook" rendering program.
- **September 2023**: I was inspired by Rust's official "mdbook" design and started to think about designing my own.

## September 2024

I implemented my idea of enabling fullscreen for my custom components. Drawing multiple scenes with a single "root" canvas is indeed a very interesting and, to some extent, elegant approach to incorporating 3D scenes with a human-friendly text-reading experience.

The implementation can still be quite challenging. In general, we need to be careful with the CSS "z-index", the clean-up of removed scenes (especially for Single Page Applications), "canvas" transparency, creating a new temporary "root canvas" inside the "fullscreen-ed" root element, and handling the listeners of "fullscreen change". Speaking of the "fullscreen change", I think it's quite unusual to see "fullscreen change" instead of "fullscreen on" plus "fullscreen off". The "fullscreen change" means we need to handle and detect the previous fullscreen state.
