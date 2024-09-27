---
description: "二〇二四年九月的第四周"
long_title: "二零二四年九月第四周日记 - 之枫"
---

# 九月二十三号周一

[(Encrypted)](#ODAAEPCJIEAJCKEANDLOKCPHAFKCOPLPHJJCMMMJNGJJDCLLFBHEEMIGOHGHNGBLHEGJOOKFLOMACDJFMKMFNKJLJKAANMOONDKEOAMMNLDLHHGDHHAHDAPEHBEFGBCPIKLBOAGDPLHDBGCLHPAPBMBBAFAEOLHCMFGOEBDEHCNJEDKELPLOJBEMHNPJPPKPMDCDNJCINNHMAMDNKGKIELMLHBHECCJCMKAKCODANCAJKJOJGEIMOGILNPELDKHIEAGDAAGFBNNCHNGKKKFDDCJKJFMBDOLINBJFIGEEDJCINCOEAHOOIHPAFABIAMKDEEADBGHFMEAIOPKHLJPLJAPHENGBGLIEGNHMKDODLHMDMGOJGNABOLNIMGKKMJBEOBDHCHGDOGANLNJKGHKKKFFLJIHNPNMMHEJOKLMNDMNIIDAICHEHMKNOFDLONMDNKLJCDPDMKFFPHCCDANMCDJBHEMFHNPBNPLOIONMKNILECFBOJHJCNCCBDOFNAJEPKAPOEENLACFNJGJFPHOIKLLBHFAMPJKPLJDFPNJGDEDMCINIJGCHBLDCOGINBGJGJEHIGHKHKNIDJPDMBJABMMPNAFNDAKBIDLCEOMOOHAHAKECMPGALOB)

## 垃圾房

其实从上周我就感觉到好像从垃圾通道丢下去的东西卡在中间了, 因为掉落的时间听起来不太对. 今天果然满了. 我想我需要尝试一下从地面直接去一层对应的位置处理.

## IS390 的 Trouble Brewing 游戏

我感觉要是再不说话, 老师就要不高兴了. 所以我大概分析了一点. 希望不会太搞笑.

# 九月二十四号周二

## 梦

早上我好像梦见在人朝分的"I"字形教学楼的西部的那种东西向的办公室里和老师和同学在做一种奇怪的在木板模子上刷糖浆的工作. 时间大约是傍晚, 夕阳很好, 让人感觉有暖洋洋的. 有点像我在真实世界里, 早早到了学校, 提前买好了煎饼在楼道的尽头吃, 面对着一扇能看到东方的窗户, 看着清晨的朝阳的感觉. 楼道尽头的三扇窗户带来了地面的清新的清晨的空气, 和楼道里相对混着消毒水的味道产生了一种对比. 那不光是景色很好, 而更多是一种"没有选择"的感觉, 没有选择, 就意味着不需要思考怎么进步, 怎么调整. 可以相对的脑子空空, 我只管把手里的煎饼吃干净不要掉渣子到地上就好了.

## 垃圾房

我今天上课下楼时带着昨天计划扔的四个瓶子来到一层的垃圾房. 我觉得这个经历就像是某种隐喻. 尽管我之前也试图去过垃圾房, 但是似乎从没有仔细地看过从楼上下来的两根管道. 和我以前猜想的差不多, 好像其实回收和不回收大概也只是我一厢情愿. 或许有人会把两者分开, 但是起码就结构上来说, 没有结构能让分开这两者变得方便. 或许这可能是个进入社会的隐喻吧. 虽然其实楼上的垃圾房也没有多干净, 不过起码暂时没有苍蝇.

我把四个瓶子摆在墙边就去上课了.

## 整理"learn_cs"

我发觉, 随着积累的文件越来越多, 似乎"Rust Analyzer"有点子力不从心. 鉴于我本来也没有计划像正常的库一样用旧的题目里的代码, 我想我没有必要把它们包含在"src"文件夹里. 于是我就把"problems"挪到了项目的最外层.

感觉已经很久没有仔细看每日一题了. 今天是"hard", 但是我很快就想到了思路. 虽然还有一堆待办的事情, 但是我还是花时间把每日一题自己思考了. 有一个有趣的 bug, 就是我提前把一个 index 加了 1, 加上我使用的是"uncheck"去读取数组内部的 element, 而且一开始我使用的是"fix-sized array", 于是程序就把越界的地方也能解读出东西哈哈哈. 当我把`Node`里的`next_node_idxs_arr`加上`Box`从而使它储存在"heap"时, 就直接"Segment Fault"了.

另外, 我一开始觉得在"Stack"里使用"Fix-sized Array"会使得`Vec`在扩展的时候变慢, 没想到反而应该是更快的 (虽然就一个样本, 但是好像快了一倍). 或许是"Heap"分配空间比较耗时吧.

```rust
struct Node {
    next_node_idxs_arr: [Option<usize>; 26], // 这里
    end_here_count: usize,
}

impl Node {
    pub fn new() -> Self {
        Node {
            next_node_idxs_arr: [None; 26],
            end_here_count: 0,
        }
    }
}

const LOWER_A_U8: u8 = 'a' as u8;

struct PrefixTree {
    nodes: Vec<Node>,
}

fn char_to_idx(c: char) -> usize {
    (c as u8 - LOWER_A_U8) as usize
}

impl PrefixTree {
    pub fn new() -> Self {
        let mut nodes: Vec<Node> = Vec::with_capacity(10);
        nodes.push(Node::new());
        Self { nodes }
    }

    pub fn insert(&mut self, char_iter: impl Iterator<Item = char>) {
        let mut curr_node_i: usize = 0;
        let mut next_node_i: usize = self.nodes.len();
        // print!("Insert ");
        for next_child_i in char_iter.map(char_to_idx) {
            // print!("->{}", next_child_i);
            let curr_node_mut_ref = unsafe { self.nodes.get_unchecked_mut(curr_node_i) };
            curr_node_mut_ref.end_here_count += 1;
            let curr_node_next_i_mut_ref = unsafe {
                curr_node_mut_ref
                    .next_node_idxs_arr
                    .get_unchecked_mut(next_child_i)
            };
            if let Some(next_node_i) = curr_node_next_i_mut_ref.clone() {
                curr_node_i = next_node_i;
            } else {
                *curr_node_next_i_mut_ref = Some(next_node_i);
                self.nodes.push(Node::new());
                curr_node_i = next_node_i;
                next_node_i += 1; // 原来这个东西在上一行前面哈哈哈

            }
        }
        // print!("->{}", curr_node_i);
        let curr_node_mut_ref = unsafe { self.nodes.get_unchecked_mut(curr_node_i) };
        curr_node_mut_ref.end_here_count += 1;
        // println!("");
    }

    pub fn calc_score(&mut self, char_iter: impl Iterator<Item = char>) -> i32 {
        let mut curr_node_i: usize = 0;
        // print!("Calc ");
        let mut ans_score: usize = 0;
        for next_child_i in char_iter.map(char_to_idx) {
            // print!("->{}", next_child_i);
            let curr_node_ref = unsafe { self.nodes.get_unchecked(curr_node_i) };
            ans_score += curr_node_ref.end_here_count;
            let curr_node_next_i_ref =
                unsafe { curr_node_ref.next_node_idxs_arr.get_unchecked(next_child_i) };
            if let Some(next_node_i) = curr_node_next_i_ref.clone() {
                curr_node_i = next_node_i;
            } else {
                unreachable!("Defined by the problem.");
            }
        }
        let curr_node_ref = unsafe { self.nodes.get_unchecked(curr_node_i) };
        ans_score += curr_node_ref.end_here_count;
        // println!("");
        ans_score as i32
    }
}

impl Solution {
    pub fn sum_prefix_scores(words: Vec<String>) -> Vec<i32> {
        let mut words_len = words.len();
        let mut prefix_tree = PrefixTree::new();
        for word_ref in words.iter() {
            prefix_tree.insert(word_ref.chars());
        }
        let mut ans_scores_vec: Vec<i32> = Vec::with_capacity(words_len);
        for word in words.into_iter() {
            ans_scores_vec.push(prefix_tree.calc_score(word.chars()) - words_len as i32);
        }
        ans_scores_vec
    }
}
```

# 九月二十五号周三

今天早上醒来就 08:59 了, 索性不去上课, 抓紧时间写作业吧.

## IS309 的有趣小作业

作业大致是要写一个生物电脑.

> It's just another regular morning for Miss Safraye. At 5:59am, She wakes up, disables the alarm, puts a new, fully-charged carbohydrate battery into the clock, and charges the old batteries. The heartbeat cycle of this new alarm is pretty precise, precisely 60 beats per minute, she thought. She opens the wardrobe." Today is Sept 25th. Which one should I wear for today..." She quickly runs a hash function in her mind. "That's it, dress number 0xa3." After she finishes dressing up, she walks up to her newly brought housing robot, Lemon negative 3. She doesn't trust those new technologies: a blood spike when she was asleep could ruin everything. She plugs in a vein from the wall into the robot. The sound of heart cycles starts inside the robot. "Good morning, Miss Safraye. How was your sleep?" says the robot. "Good, code 200 good," she replies. "That's good to hear. So, still the usual combination for your breakfast?" the robot asks. "Yes, and don't forget when you finish cleaning up later, don't randomly put the dishes like a mad person." Safraye returns " You need to imagine the dish rack is a cycled queue, and you put the most recently used dish to the end of a queue. So that we can regularly and equally use all the dishes." "Yes, sure, sorry, Miss Safraye. I won't forget this time!" "You indeed need to think more in the way humans think, the natural way of thinking."

## CS233

今天上课的最后一题遇到了一点困难哈哈. 主要是`$ra`没有存. 当时, 或许现在,感觉对于"Stack"的理解有点不透彻哈哈.

```mips
    # Allocate space for the previous level of Saved Temporaries

    sub $sp, $sp, 16

    # Save the previous level of Saved Temporaries

    sw $s0, 0($sp)
    sw $s1, 4($sp)
    sw $s2, 8($sp)
    sw $s3, 12($sp)

    # Save the current PC return addr

    move $s0, $ra           # Copy $ra to $s5

    # $s0 stores the current $ra
    # $s1 stores `y`, since $a2 might be touched after calling `bar`
    # $s2 stores the addr of `A[x]`
    # $s3 stores `temp` and later inplaced multiplication of `temp` and `baz`

    move $s1, $a2           # Copy `y` to $s4

    # Calculate the addr of `A[x]`

    mul $s2, $a1, 4         # Multiply the index by 4
    add $s2, $s2, $a0       # Add the addr offset to the addr of `A`, and we need this addr later for saving the result.

    # Load `A[x]`

    lw $t0, 0($s2)         # Load `A[x]` to temporary register $t0, since we don't need to use `A[x]` after calling `bar(A[x])`

    # Call `bar`s and calculate

    move $a0, $t0           # Setting up the argument register to be $s2: `A[x]`
    jal bar                 # Calling bar, note that $ra changes here
    move $s3, $v0           # Move $v0 to $s3. $s3 = `temp`

    move $a0, $s1           # Setting up the argument register to be $s1: the cloned `y`
    jal bar                 # Calling bar, note that $ra changes here
    mul $s3, $s3, $v0       # $s3 = $s3 * bar_returned = temp * bar_returned

    # Save result to `A[x]`

    sw $s3, 0($s2)          # Save word $s3 ( `temp * baz` ) to `A[x]`

    # Restore $ra

    move $ra, $s0

    # Restore the previous level of Saved Temporaries

    lw $s0, 0($sp)
    lw $s1, 4($sp)
    lw $s2, 8($sp)
    lw $s3, 12($sp)

    # Release the current Stack

    add $sp, $sp, 16

    jr $ra
```

## 链接的 icon

我发现我有很多的互联网链接在桌面, 而它们的图标都是一样的, 感觉不太美观. 于是我就去一些网站找它们的"favicon.ico"顶替. 有一些这种图标是以"png"或者别的形式存在的, 我以前用过线上的转换, 这次我问了下"GPT", 然后安装了"Image Magick", 感觉还蛮方便的. 桌面也更自然了些.
