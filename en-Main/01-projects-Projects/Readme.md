---
description: "Zhifeng's Projects"
long_title: "My Projects - Zhifeng"
---

# My Projects

## Markdown Book Website: Full Stack Web Development

- ([Markdown Book Chapter Link](/projects/mdtome/))

My Markdown Book project is about rendering Markdown files into a structured website with custom components like visualizations and gadgets.

This project is about how to organize my works, thoughts, and reflections into a website on a daily basis. This project began in the fall of 2021. I have learned and used various tools, libraries, frameworks, and design patterns, including HTML, CSS, JavaScript, TypeScript, Angular.js, React.js, Three.js, Next.js, and Rust-Lang.

The challenges are about designing a pattern of organizing my projects, thoughts, and introspections that enable some expandable website structure. Implementation challenges are mainly about how to efficiently store and handle the file system folders and turn those relationships and encapsulations into website structures.

## Game Study: Connect Four Solving

I have reproduced and replicated the results of Pascal Pons' blog post about strongly solving Connect-Four, implemented it in the Rust programming language, and deployed it on a server.

I have also designed a visualization of its partial game graphs.

```json#con4_graph
{
    "load": ["/src/assets/c4w7h6.len5.20240803.gamegraph.json"],
    "following_actions_string": "47573",
    "api_url": "https://con4.zf-w.space/c4w7h6",
    "camera_param": {
        "z": 2.0
    },
    "orbit_ctrl_param": {
        "auto_rotate_speed": 0.1
    }
}
```

## Graph Viz: Multi-level Force Directed Graph Layout

This is the longest project of mine. The idea started in Fall 2019. I wanted to visualize the structure of a small finger-tip game with a small number of possible states. The journey was also long, including reading Dr. Hu's paper about "Efficient, high-quality force-directed graph drawing", implementing the layout algorithm separately with Python, C++, and Rust in 2019, 2023, and 2024, and making the corresponding frontend and website to display and archive the results and visualizations.

## Implementing Barnes-Hut Tree

The Barnes Hut Tree data structure is a key to accelerate the graph visualization algorithm by quickly and fairly approximate calculating N-body forces. This is a very interesting interdisciplinary data structure. The data structure is about both "structure" and "calculation". Here is a link to the documentation site [link](https://docs.rs/zhifeng_impl_barnes_hut_tree/).

```json#graph
{
    "load": ["/src/assets/bht/airfoil1.bht.test.json"]
}
```

# Mini Projects:

## Make a Cyber Rose website for Hailuo

- [Link to rose website](https://uiuc.hailuoxinli.com/)

The website or webpage is mainly for Valentine's Day of 2024. It's a funny website displaying a interactive and shader-animated 3D rose. I was also learning how to use a server state between threads, and that's how the counting of number of visits was achieved. The counting resets with every reboot of the server. I temporarily set the initial counting to be the number I manually memorized and updated around Valentine's Day.

## To be archived

- Read Network Visualization data into Blender

- Apply Graph Algorithms on 3D models in Blender

- One plus One game Visualization

- Use Network Visualization to make art fonts & Images

- INFO303 Visualization of Reinforcement Learning Agent Learning Tree Maze

- INFO303 Maze Art Font with Visualization of Depth First Search

- Three.js practices

```json#fun_galaxy
{
    "galaxy_param": {
        "branches":3
    }
}
```

- 3D Print Fractals
