---
description: "Thank you for visiting my website."
long_title: "Main Page - Zhifeng"
---

```json#fun_galaxy
{
    "galaxy_param":{
        "branches":4
    },
    "camera_param": {
        "position": {
            "x": 0,
            "y": -2,
            "z": 2
        }
    }
}
```

# Thank you for visiting Zhifeng's website

Hi! I'm **Zhifeng Wang**, currently a class of 2025 undergraduate student single-majoring in Information Science + Data Science at the School of Information Science at the University of Illinois Urbana Champaign.

# About My Website

The website's design resembles a book. The table of contents should be open by default, and you can use the top left button to toggle the table of contents menu.

For the table of contents menu, you can click on the name of each "chapter" to go to the designated webpage.

I'm not a big fan of collapsable menus since too many layers of nested folders can be a little messy. To encapsulate contents, making it easier for readers and me to focus on a "subpart" of the book, the chapter names with a <svg width="14" height="14" viewBox="0 0 12 12" xmlns="http://www.w3.org/2000/svg"><path d="m 6 0 L 0 10 L 12 10 Z" fill="currentColor"/></svg> are the links indicating those contents are grouped. When you enter those "**subparts**", the contents "above" that level will disappear in the table of contents menu, but you can always go back by clicking the chapter name of the "parent" content (**always on the top and has a separation line under it**).

At the end of the page, there is another navigation bar to allow us to jump to the next or previous page, decided by a pre-order traversal of the content tree. This sometimes gets tricky when an encapsulated page node starts a subtree of contents that is not included in the table of contents. When we get those pages, a third link will let us go deeper into the subtree of contents.

# Interests

- AI, Machine Learning, LLM, Strongly Solving Games
- "Intelligence" Visualization in Data Visualization (if there is such a thing).
- Human Computer Interaction, Computer Science + Education

I'm interested in the topic of "learning", both in AIs and humans. How do AI learn from data and experiences and solve problems? How do different AI's structure design and random initial state affect their intuitions of decision makings and learning processes? How do data being abstracted and represented differently affect learning progress?

For these problems, the boundary between AI and human learning becomes somewhat blurry. How do humans learn from inputs and experiences? How do different personal experiences affect people's problem-solving intuitions or heuristics? How can we systematically test, improve, and personalize learning experiences? How can we adjust textbooks and course designs based on students' responses? Those are indeed very interesting questions for me.

Around the problem about how AI and human learn, I'm also interested in topics like how to visualize something like intelligence, intuition, heuristics, and calculation of best decisions. For games with clear-defined states, I guess graphs are a way to represent the game structure and players' strategies. One of my major individual research/project is about visualizing graphs.

On the other less theoretical hand, I'm interested in designing systems that help me express, accumulate, and deliver my ideas. That's where the website comes from.

## Individual Projects

The three individual projects below are closely intertwined to basically just visualize game graphs on the web. They took me five years, and I consider those efforts as after-school-full-time.

### This Book-styled Website

I have been trying to design a personal website that will allow me to constantly add content, reflections, and interactive gadgets like visualizations.

I wish the website could be designed in a way that is flexible (allowing me to constantly add new custom components like the graph visualizations), transparent (allowing me to control almost every aspect from the server to the client), content-focused (compared to focusing on layout and animations (important but should be secondary)), and enabling human-friendly writing experience (compared to computer-friendly). I guess it's inevitable for designers and programmers to constantly re-work their stuff, but I do sincerely hope there can be less re-work. I think one of the essenses of computer science would be try to avoid repeat works.

### Game Study

Games are, to some extent, abstractions of the real world. I'm interested in the intelligence hidden behind the game-solving and learning process. I have currently made a perfect Connect Four solver that calculates the both-player-playing-optimally results and how soon they will reach that terminal result. Below is a visualization gadget of Connect Four game, drawing the states connections within 5-moves starting from the root-empty-board game state. And here is the **[link](/projects/game/)** to my reflections (to another part of my website).

```json#con4_graph
{
    "load": ["/src/assets/c4w7h6.len5.20240803.gamegraph.json"],
    "following_actions_string": "3333",
    "api_url": "https://www.zf-w.space/api/c4w7h6/solve",
    "camera_param": {
        "z": 0.8
    },
    "orbit_ctrl_param": {
        "auto_rotate_speed": 0.1
    }
}
```

```json#con4_bhtree
{
    "load": ["/src/assets/c4w7h6.len5.20240803.gamegraph.json", "/src/assets/c4w7h6.len5.20240803.bht.json"],
    "start_active_states_list": [0,2696, 2829,2851,2858,2862,1,2,3,4,5]
}
```

The above visualization is my attempt at using an Octree data structure to quickly find information about a particular state. I'm very grateful that all the parts of my code can smoothly work together. The Octree structure is extracted from my Barnes-Hut Tree implementation for accelerating force simulations for my force-directed graph visualization implementation. I'm truly, truly grateful that all the parts worked together; at least no too-obvious problems.

### Graph Visualization

Visualizing networks, or graphs, is also a long project that I have been working on. Since 2019, I have started learning and implementing the graph layout algorithm. I was hoping to visualize a small fingertip game. From reading Dr. Hu's journal about graph visualization, making Python implementations, reading and storing data in various forms, learning to render 3D webpages, and making the final webpage, it's indeed a very long journey.

```json#graph
{
    "load": ["/src/assets/bht/Airfoil1.bht.test.json"]
}
```

## End Navigation

The below links are the links that can bring you to the next page, trying to provide an experience of reading physical books.
