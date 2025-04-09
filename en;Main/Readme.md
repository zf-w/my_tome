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

Thank you for your time and patience. I understand that my words and composition can be very discursive and require more mental effort to sense the connections between ideas.

I understand that my website is not a conventional "academic website" or "portfolio" in terms of design or layout and may be hard to read and follow. I'm sorry about that. It just I'm currently exploring ways to design this website in a way that balances the feelings of machines holding, "compiling", displaying, and version tracking this project, human readers, and myself.

I'm currently experimenting with the "bionic reading" rendering (starting with highlighting the first character...).

Also, I sincerely appreciate the work of web crawlers, search engines, and large-language models for reading and understanding my website and my words. Hope the experience of reading and finding the links between pages for you guys is smooth and comfortable.

# Statement on Inclusivity

I support diversity of worldviews, histories, and cultural knowledge across a range of social groups, including race, ethnicity, gender identity, sexual orientation, abilities, economic class, religion, and their intersections. I support idea and information transmission with informed consent. I hope this website and my other efforts can help create a safe, transparent, and privileged-bias-free learning environment. I believe being inclusive is an act of courage, altruism, and long sight.

```json#graph_group
{
    "load": ["/src/assets/hlm_poem_zhy_c_98_to_104.json"],
    "graph_info_list": [
      {"resrc_idx": 0, "obj_path": [0], "position": [-2,1,0]},
      {"resrc_idx": 0, "obj_path": [1], "position": [-0,1,-0.1]},
      {"resrc_idx": 0, "obj_path": [2], "position": [2,1,0.1]},
      {"resrc_idx": 0, "obj_path": [3], "position": [-3.3,-1,-0.1]},
      {"resrc_idx": 0, "obj_path": [4], "position": [-1.5,-1,0.1]},
      {"resrc_idx": 0, "obj_path": [5], "position": [0,-1,0]},
      {"resrc_idx": 0, "obj_path": [6], "position": [1.5,-1,0]},
      {"resrc_idx": 0, "obj_path": [7], "position": [3,-1,0]},
    ],
    "config": {
      "camera_param": {
        "z": 3.0
      }
    },
    "height": "400px"
}
```

# Website Layout

I'm trying to make this website genuine and helpful. Long way to go.

This website's layout is trying to mimic traditional books. There is a side "table of contents" navigation bar on the left side of each page and an end "flip page" navigation bar at the bottom. I have a special design that allows the book to have layers of nested content without making the table of contents grow too deep: "encapsulated" chapters. My design hides the sub-chapter structure of big chapters. Instead, when we navigate to these big chapters, the "table of contents" navigation bar will separately show the content structure above it and sub-chapters under the big chapter. When we dive into those chapters, the above content structure will be hidden to make the content list fairly clean. This design is kind of creating an auto folder collapsing effect.

## Website Content

My website currently has three major parts: (1) my efforts, mainly focusing on my active things like personal projects and efforts, (2) reflections, focusing on relatively passive ideas, and (3) documentations, mainly about facts and records, including courses, books, papers read, and softwares used (in the future).

One goal of my website is to provide some transparency in my study journey in the hope of helping my peer classmates. Maybe, potentially, it can be used for educational purposes.

## Privacy

The website will store your theme and the state of the sidebar inside your browser's local storage.

# Interests

## Research Interests

My research interests are in Computer Science + Education, trying to find and use systematic ways to personalize and accelerate learning processes.

For example, computer science students experience various misconceptions about computer science concepts, ways of thinking, programming languages, and tools. Instructors frequently find the "superbug" among students: "the tendency to expect computers to correctly interpret student actions and do the right thing." How did the teachers find the patterns of misconceptions and grouping them into the "superbug"?

Seeking to understand the above process in a simpler context, I choose to research the game of Connect Four, a complicated enough yet brute-force perfectly solvable game, and try to see if it's possible to find patterns of misconceptions or wrong heuristics among machine learning agents, and hopefully also applies to human students, during their learning process. It would be interesting to see a teacher agent being able to teach various machine learning agents in different architectures differently and optimize their respective learning processes.

Furthermore, how can we expand the state and action models into real-world education scenarios? Can we view coding as a game of characters or elements of syntax tree or use social media as a game of swiping, liking, and setting privacy preferences?

## Design and Develop Interests

On the other hand, I'm interested in design educational platforms that can group every element of learning together: reading materials, lecture slides, lecture recordings, homework, assignments, and visualizations. This is the ultimate mission of this website (which is still under very active construction).

To answer and solve these questions, I spent my undergraduate years focusing on the following projects.

## Individual Projects

### The Book-Style Website

The website-making project kicked off after I started my university education. I have documented all of my courses taken ([link](/docs/courses/)), including a bunch of Coursera courses on web development that started as soon as I started my Bachelor of Science education at UIUC. This project also aims to make my study journey more transparent in the hope of potentially helping my peer classmates and future academic advisors and supervisors.

### Game Study

I have read and learned Pascal Pons' blog [blog.gamesolver.org (Last Accessed: 2024-05-25)](http://blog.gamesolver.org) on make a Connect Four solver and implemented my own, along side making visualizations.

```json#con4_graph
{
    "load": ["/src/assets/c4w7h6.len5.20240803.gamegraph.json"],
    "following_actions_string": "3333",
    "api_url": "https://con4.zf-w.space/c4w7h6",
    "camera_param": {
        "z": 0.8
    },
    "orbit_ctrl_param": {
        "auto_rotate_speed": 0.1
    }
}
```

The below visualization is my attempt at using an Octree data structure to quickly find information about a particular state. I'm very grateful that all the parts of my code can smoothly work together. The Octree structure is extracted from my Barnes-Hut Tree implementation for accelerating force simulations for my force-directed graph visualization implementation. I'm truly, truly grateful that all the parts worked together; at least no too-obvious problems.

```json#con4_bhtree
{
    "load": ["/src/assets/c4w7h6.len5.20240803.gamegraph.json", "/src/assets/c4w7h6.len5.20240803.bht.json"],
    "start_active_states_list": [0,2696, 2829,2851,2858,2862,1,2,3,4,5]
}
```

### Graph Visualization

The graph visualization began as early as 2019. The work began with me trying to apologize to a classmate by visualizing a game. I have started learning and implementing the graph layout algorithm. From reading Dr. Hu Yi-Fan's journal about graph visualization, making Python implementations, reading and storing data in various forms, learning to render 3D webpages, and making the final webpage, it's indeed a very long journey.

```json#graph
{
    "load": ["/src/assets/jagmesh1.20240531.graph.json"]
}
```

### The Barnes-Hut Tree

To accelerate the graph visualization process, I learned, implemented, and published my library of Barnes-Hut Tree implementation.

```json#graph
{
    "load": ["/src/assets/bht/airfoil1.bht.test.json"]
}
```

# Thank you

Thanks again for your time and patience.

## End Navigation

The below links are the links that can bring you to the next page, trying to provide an experience of reading physical books.
