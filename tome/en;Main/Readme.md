---
description: "Thank you for visiting my website."
long_title: "Main Page - Zhifeng"
---

```fun_galaxy
{
    "galaxy_param":{
        "branches":4
    }
}
```

# Thank you for visiting Zhifeng's website

I'm **Zhifeng Wang**, currently an incoming senior year undergraduate student single-majoring in Information Science + Data Science at the School of information science at the University of Illinois Urbana Champaign.

## Interests

- AI, Machine Learning, LLM, Strongly Solving Games
- "Intelligence" Visualization in Data Visualization (if there is such a thing).
- HCI, Computer Science + Education

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

```con4_graph
{
    "load": ["/src/assets/c4w7h6.len5.20240803.gamegraph.json"],
    "following_actions_string": "3333",
    "api_url": "http://www.zf-w.space/api/c4w7h6/solve",
    "camera_param": {
        "z": 0.8
    },
    "orbit_ctrl_param": {
        "auto_rotate_speed": 0.1
    }
}
```

A part of my initial goal is to design interactive gadgets to help me better understand the concepts Victor Allis is talking about. The interactive playground below is a reconstruction of Diagram 3.5 in Victor's paper, demonstrating the idea of "Odd and Even Threats." In the case below, the second player can not play the second column because the first player can win immediately with a threat in "b3". Sadly, the second player has no way to refute this threat in "b3." As soon as the fifth column is full, the second player will be forced to play in the second column. That's the idea of "zugzwang."

### Graph Visualization

Visualizing networks, or graphs, is also a long project that I have been working on. Since 2019, I have started learning and implementing the graph layout algorithm. I was hoping to visualize a small fingertip game. From reading Dr. Hu's journal about graph visualization, making Python implementations, reading and storing data in various forms, learning to render 3D webpages, and making the final webpage, it's indeed a very long journey.

```graph
{
    "load": ["/src/assets/bht/Airfoil1.bht.test.json"]
}
```

# About this Website

The website's architecture resembles the classical design of books. I think the book design elegantly captures both the advantages of allowing a linearly natural reading experience and tree-like encapsulation for quick information look up.

There are two navigation bars: the side one and the page end one. The side one is on the left side of the page and is open by default. You can use the top-left corner button to toggle it on and off. After the first load of the page, the page will store the sidebar's state in the browser's "local storage" to hide the bar if it was closed before the navigation to other pages.

At the end of the page, there is another navigation bar to allow us to jump to the next or previous page, decided by a pre-order traversal of the content tree. This sometimes gets tricky when an encapsulated page node starts a subtree of contents that is not included in the table of contents. When we get those pages, a third link will let us go deeper into the subtree of contents.
