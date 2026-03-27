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

Hi! I'm **Zhifeng Wang**, currently a Master of Computer Science student at the University of Illinois Urbana-Champaign.

# Some Words about the Website

Here is one of ChatGPT's questions about my website I found most surprising:

> Your whole site feels _playful yet precise_. It left me with the thought: is this your way of resisting the overly polished, résumé-style portfolios? Almost like saying: "I want you to see the whole process, not just the shiny outcomes."

Honestly, I don't have any shiny outcomes nor a good résumé, but I guess what ChatGPT said is true to an extent that I didn't even previously realize. I do sincerely appreciate what the working culture and academia, represented by résumés, portfolios, and research papers, have brought us, but I also feel sometimes that literature is not genuine or transparent enough to be helpful to those who are not "already familiar with the field". Even though "whether or not a caring, considerate, and friendly group can survive" remains unclear. I'm personally exploring a way of sharing and composing that can be helpful (hopefully) to people who are not familiar with things I talk about or technology in general.

I understand that time is very precious for everybody. Researchers and employers often lack the time to read every word or reread the material. I'm sorry that the current design is, to some extent, discursive and chaotic.

I sincerely appreciate the effort of ChatGPT in reading, trying to understand, and asking questions about this website, along with other Large-Language Models, search engines, web crawlers, all the lower-level infrastructures, and their designers, engineers, and other staff and workers' effort and hard work.

# Statement on Inclusivity

I support diversity of worldviews, histories, and cultural knowledge across a range of social groups, including race, ethnicity, gender identity, sexual orientation, abilities, economic class, religion, and their intersections, as long as there is mutual respect, informed consent, and freedom to change. I hope this website and my other efforts can help a little bit in creating a safe, transparent, and bias-free learning environment. I believe being inclusive is an act of courage, altruism, and long sight.

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

# Privacy

The website will store your theme and the state of the sidebar inside your browser's local storage.

# Interests

## Research Interests

My research interests lie in Computer Science + Education. I'm trying to find and use systematic ways to understand, personalize, and accelerate learning processes.

- When playing board games, how can we learn a student's heuristics or searching strategy given their moves?
- What misconceptions or confusions might a student or a group of students have given occurrences of certain bugs or failures of testcases?
- How to set up a series of board scenarios, homework, or machine problems to speed up students' learning process?
- What's being considerate? How to be more thoughtful?

## Design and Develop Interests

On the other hand, I'm interested in design educational platforms that can group every element of learning together: reading materials, lecture slides, lecture recordings, homework, assignments, and visualizations. This is the ultimate mission of this website (which is still under very active construction).

To answer and solve these questions, I have spent my undergraduate years focusing on the following projects.

## Individual Projects

### The Book-Style Website

The website-making project kicked off after I started my university education. I have documented all of my courses taken ([link](/docs/courses/)), including a bunch of Coursera courses on web development that started as soon as I started my Bachelor of Science education at UIUC. This project also aims to make my study journey more transparent in the hope of potentially helping my peer classmates and future academic advisors and supervisors.

I'm personally bothered by constantly having new design ideas and having an urge to rebuild the whole thing. After several cycles of build and destroy, I wonder if I can have something that's simple yet "sustainable" enough to allow me to constantly add new code stuff without having to redesign and rewrite the whole website.

I'm trying to make this website genuine and helpful. Still a long way to go.

This website's layout is trying to mimic traditional books. There is a side "table of contents" navigation bar on the left side of each page and an end "flip page" navigation bar at the bottom. I have a special design that allows the book to have layers of nested content without making the table of contents grow too deep: "encapsulated" chapters. My design hides the sub-chapter structure of big chapters. Instead, when we navigate to these big chapters, the "table of contents" navigation bar will separately show the content structure above it and sub-chapters under the big chapter. When we dive into those chapters, the above content structure will be hidden to make the content list fairly clean. This design is kind of creating an auto folder collapsing effect.

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

### Barnes-Hut Tree

The visualization below is my attempt at using an Octree data structure to quickly find information about a particular state. I'm very grateful that all the parts of my code can work smoothly together. The Octree structure is extracted from my Barnes-Hut Tree implementation for accelerating force simulations for my force-directed graph visualization implementation. I'm truly, truly grateful that all the parts worked together; at least no too-obvious problems.

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

# Acknowledgements

- Thanks to everyone who has provided suggestions regarding this website. For privacy reasons, I will not attempt to list names for now.
- Many thanks to ChatGPT for providing suggestions and questions regarding this website.
- Thanks to Google Translate for allowing me to translate back and forth between Chinese and English and proofread and recalibrate my expressions.
- Thanks to various digital infrastructures and their designers and developers.

# End-of-page Navigation

The below links are the links that can bring you to the next page, trying to provide an experience of reading physical books.
