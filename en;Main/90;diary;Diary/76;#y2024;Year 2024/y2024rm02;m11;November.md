---
description: "This page is Zhifeng's Study Diary of November 2024."
long_title: "November - 2024 - Study Diary - Zhifeng"
---

# November

## Music of the Month

1. _We Are the World_

   "We are the ones who make a brighter day, so let's start giving."

2. _明天会更好_

   "让我拥抱你的梦, 让我拥有你真心的面孔."

   Actually, this line is fairly related to my research interest.

## Note

This will be a stressful month in many ways.

It is such a long month. Many things happened this month.

For my personal development, I managed to fulfill my vision of fully customized deployment of my server with user authentication, hopefully, secure enough. I need to enter four passwords to kick off the server, and that number will continue to grow depending on the private sections of my tome. Oh nature, I love my tome.

For my academic journey, although I'm anticipating a dead end, I find out that's the thing I've been looking for the whole time: I want to learn, feel, and explore people's minds and personalities or say strategies through long enough readings. The lengths of academic journals are not something you can find on Instagram or Twitter. I guess, though, the "privileged bias" or condescending sense is still strong for a bunch of papers. But I would say that's interesting enough.

For the tome-writing patterns, I have found an interesting way to document my readings: just store reflections in the directory entry of the week I first started to read and use a pointer mapping its name to that week. I guess this way is both human and computer-friendly enough.

# Friday, Nov. 29th

## _CFlow: Supporting Semantic Flow Analysis of Students' Code in Programming Problems at Scale_ { #cflow }

> Zhang, A. G., Tang, X., Oney, S., & Chen, Y. (2024, July). CFlow: Supporting Semantic Flow Analysis of Students' Code in Programming Problems at Scale. In Proceedings of the Eleventh ACM Conference on Learning@ Scale (pp. 188-199).

We can view the intellectual activity of coding in different ways. I wonder if it's also possible to view coding or transforming math equations as a process of finding solutions in the state space of code pieces or math equations.

Viewing codes as a linear structure of lines might be helpful in terms of using clustering algorithms of strings(?) to group different implementations and misconceptions together in order to help the instructors find the, maybe, say, weak spots in their lectures and teaching materials.

As Hayes and Simon mentioned, I would say the instructors are trying to identify the "deepest, most efficient," the weak spots that explain the most misconceptions, as mentioned in another literature, "super misconception."

How might a system or visualization be able to identify those? I think that might an interesting research question to dig in.

# Wednesday, Nov. 27th

## _Understanding Written Problem Instructions_

> APA: Hayes, J. R., & Simon, H. A. (1974). Understanding written problem instructions. Knowledge and cognition, 167-200.

### Tea Ceremony

It's interesting to see that the game of "Tower of Hanoi", or say the state space, can be disguised in different words. I wonder how different initial heuristics might be triggered at the beginning of trying to solve the game. For example, if the game was delivered in the "Tea ceremony" context, the participants might be taking some level of daily understanding of relationship between people into the initial understanding and heuristic on solving the puzzle compared to the plain game of "Tower of Hanoi".

### Discussion of Understanding

> If our main interest lay in artificial intelligence, then we would want the UNDERSTAND program to understand in the deepest, most efficient, most flexible way possible. (p.197)

That's one of the major concerns for my Connect Four study. What's the most efficient way to classify all legal Connect Four boards into seven types of boards representing the optimal moves or 43-ish types of boards representing the best possible results? For the board size of width 6 and height 6, a simple strategy always leads to drawing, but are there any systematic ways to find such a thing for any board size of Connect Four or any arbitrary game?

For example, if the "Tower of Hanoi" is delivered using a huge graph of valid states and transitions, are there any systematic ways to find that the disk representation of the game is the most efficient or "intuitive for human" way for us to find valid moves and solutions.

> Computers are notoriously hard to program, and humans almost as notoriously hard to educate.

I would say the first one might be a lot easier. Even though computers are very complicated, they are still white boxes, I guess. Plus, you can always reboot them.

### Reflections

I guess it would be impossible for people to use only "black box" testing to determine whether a computer program or a person's understanding or solution on a thing with infinite inputs is correct. Maybe, for example, we can't make sure a program or a person can sum two numbers correctly with only "black box" testing. There always might be a "backdoor-ish" error on some magic numbers. Sometimes, the overflow issue of using a fixed number of bits to represent integers can truly confuse and trip off students like me, at least at the beginning.

# Wednesday, Nov. 13th

## Chat Signature

I think the digital fingerprint concept might help the instantaneous information-sharing process of social deception games like Blood on the Clock Tower. It's currently added under the "utilites" directory. A main effort made into this is not the implementation, but how to compose texts to explain my idea. I'm grateful that my current design allows me to effortlessly embeded various gadgets into texts.

## Cache Simulator

The current topic of CS233 is caching. I understand that we are supposed to get a good understanding of how different coding practices will affect the performance from a hardware stand point, but manually calculating the cache misses can be a little... inconvenient, especially when under time or other pressure. I would hope my future supervisors or bosses will not pick me during a meeting and ask me what's the approximate number of cache miss of some Intel chip of given this program.

```python
class CacheSim:
    def __init__(self, way_size, idx_bits_num, off_bits_num):
        self.way_size = way_size
        self.idx_size = 1 << idx_bits_num
        self.off_size = 1 << off_bits_num
        self.__data = [[] for i in range(self.idx_size)]
        self.__total_access_num = 0
        self.__total_miss_num = 0

    def get_tag_and_idx_from_addr(self, addr):
        return (int(addr / (self.off_size * self.idx_size)), int(addr / self.off_size) % self.idx_size)

    def load_addr(self, addr):
        self.__total_access_num += 1
        tag, idx = self.get_tag_and_idx_from_addr(addr)
        way_list = self.__data[idx]
        for prev_tag_i, prev_tag in enumerate(iter(way_list)):
            if prev_tag == tag:
                way_list.pop(prev_tag_i)
                way_list.insert(0, tag) # Bug here, was `insert(tag, 0)`
                return;
        self.__total_miss_num += 1;
        if len(way_list) >= self.way_size:
            way_list.pop(-1)
        way_list.append(tag)


    def get_access_num(self):
        return self.__total_access_num
    def get_miss_num(self):
        return self.__total_miss_num
```

## Leetcode Daily 2563. Day 829

I'm grateful that the calculation of the final indices of Binary Searches below didn't cause off-by-one errors. I haven't had time to carefully think about those, but they indeed worked. I'm very grateful.

```rust
/// ## Leetcode 2563. Count the Number of Fair Pairs
/// https://leetcode.com/problems/count-the-number-of-fair-pairs/
/// - `Medium`; `Independently Solved`; `y2024m11d14`;
///
/// I guess this might be quicker if we consider the duplication of pairs. Maybe the begin and end indices can be further "pruned".
pub fn count_fair_pairs(mut nums: Vec<i32>, lower: i32, upper: i32) -> i64 {
    // [0,1,4,4,5,7]
    // [1,2,5,5,6,8]
    // [4,5,8,8,9,11]
    // [4,5,8,8,9,11]
    // [5,6,9,9,10,11]
    // [7,8,11,11,12,14]
    nums.sort_unstable();
    let len = nums.len();
    let mut ans_count: usize = 0;
    let mut prev_lower_i = len;
    let mut prev_upper_i = len;
    for num_ref in nums.iter() {
        let curr_lower = lower - num_ref;
        let curr_upper = upper - num_ref;
        let mut begin_i = 0;
        let mut end_i = prev_lower_i;
        while begin_i < end_i {
            let mid_i = (begin_i + end_i) / 2;
            if nums[mid_i] >= curr_lower {
                end_i = mid_i;
            } else {
                begin_i = mid_i + 1;
            }
        }
        let lower_i = begin_i;
        prev_lower_i = lower_i;
        let mut begin_i = prev_lower_i;
        let mut end_i = prev_upper_i;

        while begin_i < end_i {
            let mid_i = (begin_i + end_i) / 2;
            if nums[mid_i] > curr_upper {
                end_i = mid_i;
            } else {
                begin_i = mid_i + 1;
            }
        }
        let upper_i = begin_i;
        prev_upper_i = upper_i;
        ans_count += upper_i - lower_i;
        let num_square = num_ref + num_ref;
        if num_square >= lower && num_square <= upper {
            ans_count -= 1;
        }
    }
    ans_count as i64 / 2
}
```

# Tuesday, November 12th

## Socket and React

I need to take some time to carefully think about how the server should update the React page's states with the web socket...

## Leetcode Daily 2070. Day 827

```rust
/// ## Leetcode 2070. Most Beautiful Item for Each Query
/// https://leetcode.com/problems/most-beautiful-item-for-each-query/
/// - `Medium`; `Independently Solved`; `y2024m11d14`;
///
/// Five minutes before the deadline, I was still finding the bug. So, I copied a solution, submitted it, and solved my bug.
///
/// Reference(even though I didn't read it): https://leetcode.com/problems/most-beautiful-item-for-each-query/solutions/6035442/beats-100-00-for-loop-explained-with-example
///
/// The bug was an off-by-one error in the handling of the Binary Search results. The result is actually an index of the upper bound...?
pub fn maximum_beauty(items: Vec<Vec<i32>>, queries: Vec<i32>) -> Vec<i32> {
    let mut item_vec: Vec<(i32, i32)> = items
        .into_iter()
        .map(|val| -> (i32, i32) {
            let [price_i32, beauty_i32] = val[..] else {
                unreachable!()
            };
            (price_i32, beauty_i32)
        })
        .collect();
    item_vec.sort_unstable();
    let mut item_iter_mut = item_vec.iter_mut();
    let mut beauty_max = item_iter_mut.next().expect("len >= 1").1;

    for (price_i32_mut_ref, beauty_i32_mut_ref) in item_iter_mut {
        beauty_max = beauty_max.max(beauty_i32_mut_ref.clone());
        *beauty_i32_mut_ref = beauty_max;
        // println!("{} {}", price_i32_mut_ref, beauty_i32_mut_ref);
    }

    let mut ans_vec: Vec<i32> = Vec::with_capacity(queries.len());
    let len = item_vec.len();
    for query_price_i32 in queries {
        let mut begin_i = 0;
        let mut end_i = len;

        while begin_i < end_i {
            let mid_i = (begin_i + end_i) / 2;
            let mid_price_i32 = item_vec[mid_i].0;
            // println!("{} {} {}", begin_i, end_i, mid_price_i32);
            if mid_price_i32 <= query_price_i32 {
                begin_i = mid_i + 1;
            } else {
                end_i = mid_i;
            }
        }
        // println!("-- {}", begin_i);
        // if begin_i < len {
        //     println!("ANS: {} {}", item_vec[begin_i].0, query_price_i32);
        // }
        if begin_i > 0 && item_vec[begin_i - 1].0 <= query_price_i32 {
            // Bug here
            ans_vec.push(item_vec[begin_i - 1].1);
        } else {
            ans_vec.push(0);
        }
    }
    ans_vec
}
```

# Sunday, Nov. 10th

I'm grateful that I got the `Execution Time - Everything` correct in the "CS233 Computer Architecture" practice exam on the first attempt. That's the first time I met a "break if i <= 800", i.e., "loop 801 times", case, which creates a lot for fractional cycles.

# Friday, Nov. 8th

## Leetcode Daily 3133, Day 825

This is an interesting problem. It took me a while to realize that I can think about it from the angle of permutations: only zero digits in `x` can be changed to ones. These days, the problems are all related to bit-calculation. I'm indeed very busy these days. These days, I can always come up with an idea when I am just about to open and copy from solutions. I guess this can't last long, but maybe it's a hint of my current situation.

```rust
pub fn min_end(n: i32, mut x: i32) -> i64 {
    let n_i64 = n as i64 - 1;
    let x_i64 = x as i64;
    let mut zero_idxs: [usize; 32] = [0;32];
    let mut zero_len: usize = 0;
    let mut zero_i: usize = 0;
    let mut big_shift_num_i64: i64 = 1;
    while x > 0 {
        if x & 1 == 0 {
            zero_idxs[zero_len] = zero_i;
            big_shift_num_i64 += 1 << zero_i;
            zero_len += 1;
            // println!("{}", zero_i);
        }
        // println!("x: {}", x);
        zero_i += 1;
        x >>= 1;
    }
    let to_big_shift_len_i64: i64 = 1 << zero_len;
    // println!("{:b}, {}, {}, {}", x_i64, to_big_shift_len_i64, (n_i64 / to_big_shift_len_i64 ) * (x_i64 + big_shift_num_i64), big_shift_num_i64);
    let mut ans_i64: i64 = x_i64 + (n_i64 / to_big_shift_len_i64) * (x_i64 + big_shift_num_i64);
    let mut to_add_i64 = n_i64 % to_big_shift_len_i64;
    zero_i = 0;
    while to_add_i64 > 0 {
        if to_add_i64 & 1 == 1{
            ans_i64 += 1 << zero_idxs[zero_i];
            // println!("{}, {}", zero_i, zero_idxs[zero_i]);
        }
        to_add_i64 >>= 1;
        zero_i += 1;
    }
    ans_i64
}
// 5,7,13
```

# Wednesday, Nov. 6th

## Leetcode Daily 3011, Day 823

```rust
/// ## Leetcode 3011. Find if Array Can Be Sorted
/// - `Medium`; `Independently Solved`; `y2024m11d06`;
/// - `0ms`; `2.2mb`;
///
/// I was going to view a solution since I was busy and exhausted. With another glance, I suddenly realized whether the array can be sorted depends on the "connecting" elements.
pub fn can_sort_array(nums: Vec<i32>) -> bool {
    let mut num_iter = nums.iter().cloned();
    let curr_num = num_iter.next().expect("len >= 1");

    let mut prev_bit_count = curr_num.count_ones();
    let mut prev_min = i32::MIN;
    let mut curr_min: i32 = curr_num;
    let mut curr_max: i32 = curr_num;
    for num in num_iter {
        let curr_bit_count = num.count_ones();
        if curr_bit_count == prev_bit_count {
            curr_min = curr_min.min(num);
            curr_max = curr_max.max(num);
            if curr_min < prev_min {
                return false;
            }
        } else {
            if curr_min < prev_min || num < curr_max {
                return false;
            }
            prev_min = curr_max;
            prev_bit_count = curr_bit_count;
            curr_min = num;
            curr_max = num;
        }
    }
    true
}
```

# Monday, Nov. 4th

## Personal Study

### Documenting Courses

I spent some time documenting all the courses I have taken. I think it's very important to say thank you to all the instructors in a fairly more permanent way. And it's also important to make my study life more transparent, though nobody asks.

On the other hand, even though I only had an extremely limited number of "coffee chats" with my peer classmates before, I would say this class list should be able to shorten much of the conversation. In my understanding, "coffee chat" should not be only about what courses you have taken. (Sigh) I guess it would be much harder to understand a person outside those social constructs.

# Saturday. Nov. 2rd

The previous design of my website's left navigation bar doesn't allow users to traverse through the website only using the left navigation bar. Viewing the source code of my `mdtome` website generator, I suddenly felt that I can simply render the left navigation bar twice for the encapsulated nodes: one for the above subtree and one for the current subtree. The execution of the plan was very smooth.
