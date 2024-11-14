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

Thanks again for visiting my website!

# Website Layout

This website's layout is trying to mimic traditional books. There is a side "table of contents" navigation bar on the left side of each page and an end "flip page" navigation bar at the bottom. I have a special design that allows the book to have layers of nested content without making the table of contents grow too deep: "encapsulated" chapters. My design hides the sub-chapter structure of big chapters. Instead, when we navigate to these big chapters, the "table of contents" navigation bar will separately show the content structure above it and sub-chapters under the big chapter. When we dive into those chapters, the above content structure will be hidden to make the content list fairly clean. This design is kind of creating an auto folder collapsing effect.

# Website Content

My website currently has three major parts: (1) my efforts, mainly focusing on my active things like personal projects and efforts, (2) reflections, focusing on relatively passive ideas, and (3) documentations, mainly about facts and records, including courses, books, papers read, and softwares used (in the future).

One goal of my website is to provide some transparency in my study journey in the hope of helping my peer classmates. Maybe, potentially, it can be used for educational purposes.

# Interests

- Computer Science + Education
- Artificial Intelligence
- "Intelligence" Visualization in Data Visualization.

How to be more considerate, how to communicate, how to learn and teach, and how to make decisions are some of my ultimate interests. Sometimes, thinking about these problems without a more formal, normative way of thinking can be difficult. I want to cut through these questions from the angle of AI and machine learning theories. For example, how to teach can be a very board question, but how to optimize a Connect Four "teacher" agent to quickly teach a machine learning agent can be a fairly narrow research problem. An even narrower question might be, what's the minimal information needed to instantly, i.e., without searching, solve the Connect Four game (of a particular board size). I guess we have to find the optimal and fastest solution before teaching students...

## Individual Projects

My current individual and independent projects mainly focus on a small step of approaching the above problem: how can I visualize the Connect Four game along with every state's information and see if I can get any insights on patterns.

Then, there are three parallel directions: making a text-visualization friendly and "sustainably growable," i.e., I can constantly add new gadgets and vizs to it, solve Connect Four using traditional methods, and graph visualization.

### The Book-Style Website

The website-making project kicked off after I started my university education. I have documented all of my courses taken ([link](/docs/courses/)), including a bunch of Coursera courses on web development that started as soon as I started my Bachelor of Science education at UIUC. This project also aims to make my study journey more transparent in the hope of potentially helping my peer classmates and future academic advisors (if there is, just in case of dereferencing some `nullptr`).

### Game Study

The Connect Four solving project started in the fall semester of my junior year in college. Below are two of my visualizations of some of the opening board states.

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

The below visualization is my attempt at using an Octree data structure to quickly find information about a particular state. I'm very grateful that all the parts of my code can smoothly work together. The Octree structure is extracted from my Barnes-Hut Tree implementation for accelerating force simulations for my force-directed graph visualization implementation. I'm truly, truly grateful that all the parts worked together; at least no too-obvious problems.

```json#con4_bhtree
{
    "load": ["/src/assets/c4w7h6.len5.20240803.gamegraph.json", "/src/assets/c4w7h6.len5.20240803.bht.json"],
    "start_active_states_list": [0,2696, 2829,2851,2858,2862,1,2,3,4,5]
}
```

### Graph Visualization

The graph visualization began as early as 2019. The work began with me trying to apologize to a classmate by visualizing a game. I have started learning and implementing the graph layout algorithm. From reading Dr. Hu's journal about graph visualization, making Python implementations, reading and storing data in various forms, learning to render 3D webpages, and making the final webpage, it's indeed a very long journey.

```json#graph
{
    "load": ["/src/assets/bht/Airfoil1.bht.test.json"]
}
```

# Thank you

Thanks again for your time and patience.

## End Navigation

The below links are the links that can bring you to the next page, trying to provide an experience of reading physical books.
