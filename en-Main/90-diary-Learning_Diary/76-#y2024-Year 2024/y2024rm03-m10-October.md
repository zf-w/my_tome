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

# Week 5, October

I have been thinking about the procedure of deciding which month a week might belong. I used to use the starting day (Monday) to determine: if that day is in a particular month, that week belongs to that month. Now, I'm using Wednesday to make that decision.

# Wednesday. Oct. 30th

## Calling 'render'

To fulfill my plan of making a Barnes-Hut Tree graph vertex selector, I'm planning to add specifications on the `mdtome`'s render function calls by appending the "extension" names after the "render" original function names. In this way, there is less ambiguity between different modules' rendering function namings. To achieve this design, I also need to modify the client-side codes to make sure the function calls are matched.

The plan worked smoothly.

## The left navigation bar

One problem about encapsulating contents is whether to display the subtree navigation structure when a reader navigates to the root node of that subtree of contents. Previously, I chose to display the subtree, but today, I realized that switching the table of contents might be very confusing. So, I choose to remove this design such that when a reader navigates through the same "depth" of contents above the encapsulated ones, the table of contents will not change.

# Thursday, October 31th

Today is Halloween, but it has nothing to do with me haha. With some spare time, I need to focus and finish my design of using Octree to select nodes and view its information, along with providing necessary controls to allow users to navigate through the graph with traditional edges. Even though my previous design is robust enough, during the process of making new "extensions", I still noticed a bunch of place I can improve. I guess I'm learning, to some extent, too fast. My implementation of Barnes-Hut Tree this June is already "unfamilar," mainly the module naming part. The conceptual design is still fairly robust, and I was be able to get the data I need with only a few additional implementations.

# Tuesday. Oct. 29th

I'm planning to refactor the path parsing of my custom module code blocks. I'm currently using the "language string" as modules naming and fetching, representing the static path of the JavaScript modules.

The plan worked smoothly.

# Sunday. Oct. 28th

I spend my spare time on Sunday learning how to generate keys with OpenSSL and get certificates from Certificate Authority with DNS challenge. It's a review and practice of the knowledge learned from my high-school A Level Computer Science course. That's indeed a good course that balances breath and depth well.

During the key generation process, I misplaced two different versions of private keys from the same set of parameters. I had to learn some more about how to check if the certificate and the private key match.

# Saturday. Oct. 27th

I spend my spare time on Saturday learning various ways to enable "https" with Rust's `actix-web` framework.

# Friday. Oct. 26th

## Leetcode Daily 2458. Day 811

Hooray. Independently solved a hard-level problem.

# Thursday. Oct. 25th

## Relearning AWS

The first time I have encountered "AWS" was about three years ago, when I'm taking Prof. Wade Fagen-Ulmschneider's Coursera "Accelerated Computer Science Fundamentals".

Now, I'm learning how to build deploy a web server with "AWS".

## Leetcode Daily 1233. Day 810

I'm basically reusing one idea used in my own implementation of `mdtome` project to solve this problem. This feels nice.

```rust
use std::collections::HashMap;

struct FolderTreeNode<'src> {
    seg_str_ref: &'src str,
    next_node_idxs_map: HashMap<&'src str, usize>,
    end_here_flag: bool,
}

struct FolderTree<'src> {
    nodes_vec: Vec<FolderTreeNode<'src>>,
}

impl<'src> FolderTree<'src> {
    fn add_folder(&mut self, folder_str_ref: &'src str) {
        let mut folder_seg_str_refs_iter = folder_str_ref.split('/');
        folder_seg_str_refs_iter.next();
        let mut curr_node_i: usize = 0;
        use std::collections::hash_map::Entry;
        let mut nodes_len = self.nodes_vec.len();
        for folder_seg_str_ref in folder_seg_str_refs_iter {
            let curr_node_mut_ref = &mut self.nodes_vec[curr_node_i];
            let next_node_entry = curr_node_mut_ref
                .next_node_idxs_map
                .entry(folder_seg_str_ref);

            let next_node_i = match next_node_entry {
                Entry::Occupied(occupied_entry) => occupied_entry.get().clone(),
                Entry::Vacant(vacant_entry) => {
                    vacant_entry.insert(nodes_len);
                    nodes_len
                }
            };
            if next_node_i == nodes_len {
                self.nodes_vec.push(FolderTreeNode {
                    seg_str_ref: folder_seg_str_ref,
                    next_node_idxs_map: HashMap::new(),
                    end_here_flag: false,
                });
                nodes_len += 1;
            }
            curr_node_i = next_node_i;
        }
        let curr_node_mut_ref = &mut self.nodes_vec[curr_node_i];
        curr_node_mut_ref.end_here_flag = true;
    }

    pub fn new_with_folders(folder_strings: &'src [String]) -> Self {
        let nodes_vec: Vec<FolderTreeNode> = vec![FolderTreeNode {
            seg_str_ref: "",
            next_node_idxs_map: HashMap::new(),
            end_here_flag: false,
        }];
        let mut tree = Self { nodes_vec };
        for folder_string_ref in folder_strings.iter() {
            tree.add_folder(folder_string_ref);
        }
        tree
    }

    fn remove_subfolders_helper(
        &self,
        subroot_i: usize,
        node_path_mut_ref: &mut Vec<usize>,
        ans_vec_mut_ref: &mut Vec<String>,
    ) {
        let curr_node_ref = &self.nodes_vec[subroot_i];
        if curr_node_ref.end_here_flag == true {
            let mut curr_path_string = String::new();
            for node_idx in node_path_mut_ref.iter().cloned() {
                let node_ref = &self.nodes_vec[node_idx];
                curr_path_string.push('/');
                curr_path_string.push_str(node_ref.seg_str_ref);
            }
            curr_path_string.push('/');
            curr_path_string.push_str(curr_node_ref.seg_str_ref);
            ans_vec_mut_ref.push(curr_path_string);
            return;
        }

        node_path_mut_ref.push(subroot_i);
        for next_node_i in curr_node_ref.next_node_idxs_map.values().cloned() {
            self.remove_subfolders_helper(next_node_i, node_path_mut_ref, ans_vec_mut_ref);
        }
        node_path_mut_ref.pop();
    }

    pub fn remove_subfolders(&self) -> Vec<String> {
        let mut node_path_vec: Vec<usize> = Vec::new();
        let mut ans_strings_vec: Vec<String> = Vec::new();
        let curr_node_ref = &self.nodes_vec[0];
        for next_node_i in curr_node_ref.next_node_idxs_map.values().cloned() {
            self.remove_subfolders_helper(next_node_i, &mut node_path_vec, &mut ans_strings_vec);
        }
        ans_strings_vec
    }
}

impl Solution {
    pub fn remove_subfolders(folders: Vec<String>) -> Vec<String> {
        let tree = FolderTree::new_with_folders(&folders);
        tree.remove_subfolders()
    }
}
```

# Wednesday. Oct. 23rd

## Naming Conventions Are Important

The variable names, or more generally, names, family names, given names, are all parts of some data structures, designed to efficiently find stuff, identify persons, or probably even the origin of "y chromosome" or the "mitochondrial DNA" in some culture. If I can design the naming culture, I would like to say that a child's name is their given name plus their mother's and father's given name (sequence depending on their age). Even though the resulting data structure is a less efficient "Union Find" (even not a "y chromosome union-find"), I think it's more respectful to each person's individual value.

## Leetcode Daily 2641. Day 808.

Hooray. No bugs at submission this time, but I made a small bug about doubly borrowing the root.

````rust
//! https://leetcode.com/problems/cousins-in-binary-tree-ii/
use std::rc::Rc;
use std::cell::RefCell;

fn replace_value_in_tree_level_sum_helper(

    level_usize: usize,
    level_sums_vec_mut_ref: &mut Vec<i32>,
    sub_root: Rc<RefCell<TreeNode>>,
) {
    if level_sums_vec_mut_ref.len() == level_usize {
        level_sums_vec_mut_ref.push(0);
    }

    let sub_root_borrow = sub_root.borrow();
    level_sums_vec_mut_ref[level_usize] += sub_root_borrow.val as i32;
    let next_level_usize = level_usize + 1;
    if let Some(left_sub_root_rc) = sub_root_borrow.left.clone() {
        replace_value_in_tree_level_sum_helper(
            next_level_usize,
            level_sums_vec_mut_ref,
            left_sub_root_rc,
        );
    }
    if let Some(right_sub_root_rc) = sub_root_borrow.right.clone() {
        replace_value_in_tree_level_sum_helper(
            next_level_usize,
            level_sums_vec_mut_ref,
            right_sub_root_rc,
        );
    }
}

fn replace_value_in_tree_modify_helper(
    sub_root: Rc<RefCell<TreeNode>>,
    level_i: usize,
    sibling_sum: i32,
    level_sums_vec_ref: &Vec<i32>,
) {
    let curr_cousins_sum = level_sums_vec_ref[level_i] - sibling_sum;
    sub_root.borrow_mut().val = curr_cousins_sum;

    let mut next_sibling_sum = 0;
    let next_level_i = level_i + 1;

    let sub_root_borrow = sub_root.borrow();
    if let Some(left_rc) = &sub_root_borrow.left {
        next_sibling_sum += left_rc.borrow().val;
    }
    if let Some(right_rc) = &sub_root_borrow.right {
        next_sibling_sum += right_rc.borrow().val;
    }

    if let Some(left_rc) = &sub_root_borrow.left {
        replace_value_in_tree_modify_helper(
            Rc::clone(left_rc),
            next_level_i,
            next_sibling_sum,
            level_sums_vec_ref,
        );
    }
    if let Some(right_rc) = &sub_root_borrow.right {
        replace_value_in_tree_modify_helper(
            Rc::clone(right_rc),
            next_level_i,
            next_sibling_sum,
            level_sums_vec_ref,
        );
    }
}

impl Solution {
    pub fn replace_value_in_tree(root: Option<Rc<RefCell<TreeNode>>>) -> Option<Rc<RefCell<TreeNode>>> {
        let root_rc = root?;
        let mut level_sums_vec: Vec<i32> = Vec::new();
        let root_val = root_rc.borrow().val.clone();
        replace_value_in_tree_level_sum_helper(0, &mut level_sums_vec, Rc::clone(&root_rc));

        // Can't use `replace_value_in_tree_modify_helper(Rc::clone(&root_rc), 0, root_rc.borrow().val, &level_sums_vec);`
        // It seems the borrowed ref doesn't get dropped immediately.
        // This works.
        //
        // ```rust
        // let get_val = || -> i32 {
        //     root_rc.borrow().val.clone()
        // };
        // replace_value_in_tree_modify_helper(Rc::clone(&root_rc), 0, get_val(), &level_sums_vec);
        // ```
        replace_value_in_tree_modify_helper(Rc::clone(&root_rc), 0, root_val, &level_sums_vec);

        Some(root_rc)
    }
}
````

# Tuesday. Oct. 22nd

## Leetcode Daily 2583. Day 807.

Today's leetcode daily. I made one "off-by-one" mistake since I didn't notice that `k` was one-indexed.

```rust
//! https://leetcode.com/problems/kth-largest-sum-in-a-binary-tree/
fn kth_largest_level_sum_helper(
    level_usize: usize,
    level_sums_vec_mut_ref: &mut Vec<i64>,
    sub_root: Rc<RefCell<TreeNode>>,
) {
    if level_sums_vec_mut_ref.len() == level_usize {
        level_sums_vec_mut_ref.push(0);
    }

    let sub_root_borrow = sub_root.borrow();
    level_sums_vec_mut_ref[level_usize] += sub_root_borrow.val as i64;
    let next_level_usize = level_usize + 1;
    if let Some(left_sub_root_rc) = sub_root_borrow.left.clone() {
        kth_largest_level_sum_helper(next_level_usize, level_sums_vec_mut_ref, left_sub_root_rc);
    }
    if let Some(right_sub_root_rc) = sub_root_borrow.right.clone() {
        kth_largest_level_sum_helper(next_level_usize, level_sums_vec_mut_ref, right_sub_root_rc);
    }
}

use std::rc::Rc;
use std::cell::RefCell;
impl Solution {
    pub fn kth_largest_level_sum(root: Option<Rc<RefCell<TreeNode>>>, k: i32) -> i64 {
        let root_rc = if let Some(root_rc) = root {
            root_rc
        } else {
            return -1;
        };
        let mut level_sums_vec: Vec<i64> = Vec::new();
        kth_largest_level_sum_helper(0, &mut level_sums_vec, root_rc);
        let k_usize = k as usize;
        let level_sums_len = level_sums_vec.len();
        if k_usize > level_sums_len { // Made one `k_usize >= level_sums_len` mistake here. `k` is one-indexed in this question.
            return -1;
        }
        level_sums_vec.sort_unstable();

        level_sums_vec[level_sums_len - k_usize]
    }
}
```

# Monday. Oct. 21st

## Leetcode Daily 1593. Day 806.

Today's Leetcode daily. I made two major bugs.

```rust
//! https://leetcode.com/problems/split-a-string-into-the-max-number-of-unique-substrings/
fn max_unique_split_helper<'src>(
    level: usize,
    s_str_bytes_ref: &'src [u8],
    mp_mut_ref: &mut std::collections::HashSet<&'src [u8]>,
    ans_len_mut_ref: &mut usize,
) {
    let len = s_str_bytes_ref.len();
    let next_level = level + 1;
    for i in 1..len { // Second bug here: `i == len` represents ending, instead of `i == len - 1`, both off-by-one hahaha.
        let curr_seg_str_bytes_ref = &s_str_bytes_ref[..i];
        if mp_mut_ref.contains(curr_seg_str_bytes_ref) {
            continue;
        }
        // println!("{} {}", next_level, unsafe {
        //         String::from_utf8_unchecked(curr_seg_str_bytes_ref.to_vec())
        //     });

        mp_mut_ref.insert(curr_seg_str_bytes_ref);
        max_unique_split_helper(
            next_level,
            &s_str_bytes_ref[i..], // First bug, an additional `+1` here.
            mp_mut_ref,
            ans_len_mut_ref,
        );
        mp_mut_ref.remove(curr_seg_str_bytes_ref);
    }

    if !mp_mut_ref.contains(s_str_bytes_ref) { // At first, this part was inside the loop with an `if`. I later realized that it would be more computer-friendly if it's outside the loop.
        *ans_len_mut_ref = (*ans_len_mut_ref).max(next_level);
    }
}

impl Solution {
    pub fn max_unique_split(s: String) -> i32 {
    let mut ans_len: usize = 1;
    let mut mp: std::collections::HashSet<&[u8]> = std::collections::HashSet::new();
    max_unique_split_helper(0, s.as_bytes(), &mut mp, &mut ans_len);
    ans_len as i32
    }
}
```
