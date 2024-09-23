---
description: "二〇二四年九月的第三周"
long_title: "二零二四年九月第三周日记 - 之枫"
---

# 九月十六号周一

## 每日一题

今天的[每日一题](https://leetcode.com/problems/minimum-time-difference/)蛮有趣的. 我一下子有点掉进一个一个问题逐渐增大的"Dynamic Programming"思维陷阱. 看了下答案, 其实大概排序一下, 再特殊看一下两头的就好了哈哈哈.

## 回宿舍

在宿舍的大门下碰到两个正在出来的消防员. 笑死, 我打这行字的时候打成了程序员. 我懵了一下, 我有点想象不出出来两个程序员是什么样子的哈哈. 然后我让了一下, 他俩先后出来, 两人都谢了我让道. 但是我只和第一个说了"You are welcome." 然后"Have a good day"也是朝着第一个人说的, 实在不好意思.

## 考试

我在考试的路上看见一只蝉好像翻了, 在那里扑腾. 我想等我考完试回来再看看能不能把它弄到草丛里去. 我考完试回来, 纠结了一下子, 担心或许它已经死了过去也是横生烦恼, 但是不过去就永远不知道了. 虽然过去了可能也找不到了. 然后我过去了发现它确实不动了. 我拿鞋尖把它顶到路边的草边, 不知道能不能好些. 起码少了一些被踩扁的可能. 我感觉我明确的感觉到考试与生命的流逝的关系.

然后我去买东西的路上看见了一只螳螂在路中间不知道干啥. 回来的时候旁边有个割草机, 我走的远了一点可能没看到它, 感觉也挺危险的. 希望它没事.

## 重新安装 Docker

Docker 的安装工具没有一个图形化的选项可以选择到底装到哪里. 查了半天才找到原来可以用命令行自定义安装位置.

## 吸血纸

我不太喜欢那种塑料泡沫底座, 上面糊上保鲜膜的肉的原因就在于有吸血纸. 它很快就会产生腐烂的气味. 为了不影响清洁工和垃圾车或者垃圾站的工人, 这种我都是剪碎了冲厕所. 不知道会不会产生别的问题. 但是我看它确实没有像一些别的商品一样大字写着不要冲厕所. 今天终于把之前几天的炒肉的吸血纸送走了.

# 九月十七号周二

今天又是很忙的一天.

## CS233

今天的 Lab 好像找出一个老师的 Bug, 还挺有趣的. 但是纠结了很长时间, 导致下午又额外花了大概一个小时去解决剩下的内容.

## Express Advising

今天第一次使用院里的 Express Advising 功能, 还挺有趣的. 上完 Lab 之后又去教学楼排了四十分钟队继续做 Lab. 有趣的是, 我在这段时间做的内容, 另外两个同学大概想赌一把, 就直接提交了然后对了, 没看到我做的工作. 我到了讨论的空间之后又提了一下子. 和指导老师大概聊的还蛮顺利.

## 每日一题

准确的说其实是明天的每日一题. 最近时间紧张, 都没什么时间仔细想. 但是我想`cmp_num`部分还蛮有趣的. 我这样设计应该能对计算机更体贴一些. 虽然题目确实大概放水了, 这个数字应该存不了一百位十进制数哈哈.

```rust
//! Learned from https://leetcode.com/problems/largest-number/solutions/5802128/sort-strings-w-r-t-the-proper-ordering

use std::cmp::Ordering;

fn cmp_num(a: &i32, b: &i32) -> Ordering {
    if *a == 0 || *b == 0 {
        return a.cmp(b);
    }
    let a_first = *a as u64 * 10u64.pow(b.ilog10() + 1);
    let b_first = *b as u64 * 10u64.pow(a.ilog10() + 1);
    (a_first + *b as u64).cmp(&(b_first + *a as u64))
}

const ZERO_U8_BASE: u8 = '0' as u8;

fn digit_to_char(digit: i32) -> char {
    (ZERO_U8_BASE + digit as u8) as char
}

pub fn largest_number(mut nums: Vec<i32>) -> String {
    if nums
        .iter()
        .fold(true, |acc, elem_ref| -> bool { acc && *elem_ref == 0 })
    {
        return "0".to_string();
    }

    nums.sort_unstable_by(cmp_num);
    let mut ans_string = String::new();
    for mut num in nums {
        if num == 0 {
            ans_string.push('0');
        }
        while num > 0 {
            ans_string.push(digit_to_char(num % 10));
            num /= 10;
        }
    }
    ans_string.chars().rev().collect()
}

```

## 听音乐

最近尝试了一下用"Spotify", 因为我发现它上面有千百惠的"走过咖啡屋". 感觉好像它的推歌会更准确一点, 或许是错觉.

## 小虫子

发现厨房的茶几上有一只小虫子. 按照以往的惯例, 我选择拿一双筷子去试图带它到窗边吹走. 但是它会飞, 然后好像一头撞进了我正在洗的碗里. 可怜的小虫子.

# 九月十八号周三

今天就是上课, 然后研究一下使用"Docker"去协调前端后端以及数据库的关系, 感觉效果十分不错.

# 九月二十号周五

## 个人开发

今天我试图完成我之前设想的小模块全屏思路. 或许这样可以使得可视化的效果好一些.

我写出了一些有趣的 bug. 由于最近我个人的主题是一致性, 我计划把所有变量命名都按照我从 Rust 里提炼出的思路. 比如说对于一个可以变的"Mutable Reference", 它的后缀应该是"balabala_mut_ref". 然后我不小心把给`Three.WebGLRenderer`的`{canvas:canvas}`改成了`{canvas_mut_ref: canvas_mut_ref}`. 然后各种东西就画不出来了哈哈哈.

我当时有一点担心这个全屏的各个 HTML Element 的坐标会各种错位, 从而导致原本的"Multi Scene Single Canvas"设计出错. 确实有一段时间我发现全屏了之后整个"canvas"就变黑了. 后来发现有几个问题, 一方面是我没有把"Renderer"按照全屏的长宽去重新设置, 也没有设置"TestScissor". 虽然这个"Scissor"好像我并没有太理解具体是为什么, 但是确实在官方文档里之前好像提到过.

还有一点好玩的点是, 我本来想到, 哎呀画透明的东西对于计算机来说是个麻烦事, 不如就不让"Renderer"去允许画透明的东西了. 然后发现全屏之后就会有个大黑片把正常的"root canvas"的渲染挡住. 调查一番发现确实只有可以全屏才能方便的通过画一个空场景来"清空"某个 "canvas" 的内容.

# 九月二十一号周六

今天大概主要是作业吧. 早上我读了 IS309 的讨论里别的同学的帖子. 我想到, 或许网络的发达导致的光盘和硬件角度的人之间的分享和交换的消失确实改变了人们之间的交互和社会的结构, 或许.

# 九月二十二号周日

今天还是作业.

[(Encrypted)](#CFBMIDCDAFANPKKLLNABAAAIOCIAHECPGMKCEIEOPOFHOFNAGLCEOACFBMLKOHBMAMIHGLIHGJPOEOHPLNHABBBIDAEFFFMMBMKOBMGHIOKBCPDCBPHOLJPHACGHPBEBLOBCBNFKDGLLFJEHJIBDDLNAIIGDKKEFAGFFBMKNBBADLNPLBODGGNCOHGHILOJMGJJKJDIHANCOJFOJNNIAPCMLHHGABCEOCEOENIGPNGENNANHNCJOCBOEJJLMPEDFMFEFPCLADKBJCDNNOJGBIPJFAEDKIMFIOKPLPBIBBHNHGOBPGEBOIOKBKJAGIOPHHEODFCOKOJIKGOGOEANFBJGLINELFMMBJNFPFPOLDBPDIDKBCHJOCHDCPAFKAKAONMFNDJHPPGDALJND)

## 蛾子

我晚上躺在地板上的时候, 发现墙上有个黑色的东西. 我仔细一看发现是一只蛾子. 我想, 我大概不能放任不管, 因为虽然我屋里有很多垃圾, 但是都是拆开仔细清洗过的, 加上之前发现过蜜蜂和苍蝇的尸体, 大概它也会饿死在屋子里. 这不大好.

于是我拿了个山泉水的瓶子去扣住它, 指望着它能进去瓶子然后回头我放生. 没想到它一点没动, 直接就进入瓶子了. 然后我试图到窗边去放生. 由于窗户有一段时间没开了, 因为之前发现的蜜蜂尸体, 耗费了一点气力才打开. 希望我没有损害窗户的结构.

但是它并没有飞走, 反而飞回了屋子里. 一方面也是我不敢把瓶子伸出窗户, 我担心有人觉得我对楼下高空抛物或者投毒倒不知名的液体之类. 经过一番斗争它停在了墙角. 我找到了一根筷子, 把瓶子挪到它前面, 然后拿筷子动了一下子, 它就不见了.

本来我以为它是飞走了或者飞到屋子的别处去了. 没想到后来盖盖子的时候看到原来它真的飞进瓶子里了. 看来, 虽然是无意识的, 但是它大概也做出了正确的选择吧.

最后, 我和室友[(Encrypted)](#IAAEFADEJCIKJMNHEELPDKHHCICHDLCIBINPOCFOGBIBJLOGDOCJCIMDHOIPLEGMPLDPJCDPLC)一起去楼下把蛾子放生了, 还录了像哈哈.
