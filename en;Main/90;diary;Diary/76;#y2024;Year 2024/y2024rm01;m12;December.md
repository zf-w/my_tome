---
description: "This page is Zhifeng's Study Diary of December 2024."
long_title: "December - 2024 - Study Diary - Zhifeng"
---

# December 2024

An important and confusing month. I should be able to finish most of my graduate study applications by this month.

# Sunday, Dec. 22nd, 2024

## Personal Project Dev

Building a web server for Connect Four generally needs

1. Setting up a configuration loading logic: listening to which port and accepting which domains.

2. Setting up Connect 4 openning table loading logic.

3. Setting up the endpoint.

# Saturday, Dec. 21st, 2024

## Personal Project Dev

Working on separating the Connect Four solver from the static file serving server.

# Friday, Dec. 20th, 2024

## Thank you, Shop Assistants

I was paying on a self-service machine of Target Campustown branch. After paying with my apple pay, I forgot that I need to enter my security pin on the machine. I usual procedure is to use my left hand to cover the number pad and use my right hand to enter the pin, but, this time, the bag fell off the counter, the blueberry box cracked open, and the blueberries came out. While I was panicking, busy picking up the scattered blueberries on the floor, and thinking about my mistake separating those blueberries, which potentially are siblings from the same bush, forever and violating my memory safety concerns, one shop assistant helped me to clean the floor, picked up my peanut butter jar for me and swepted some of the berries away, and another shop assistant asked me whether I want to take a new box of berries. She was so kind to me and I heard she said she "don't take no as an answer." But I don't want to waste a whole box of berries just because of my mistake and recklessness. So I insisted that I can still rinse these.

I deeply appreciate the two shop assistants' kindness and patience.

# Monday, Dec. 16th, 2024

## Reading _The Cambridge Handbook of Computing Education Research Summarized in 75 minutes_ { #the_cmabridge_handbook_of_cs_ed_summarized }

> Lewis, C. M., Bell, T., Blikstein, P., Carter, A. S., Falkner, K., Fincher, S. A., ... & Yadav, A. (2020, February). The Cambridge Handbook of Computing Education Research Summarized in 75 minutes. In Proceedings of the 51st ACM Technical Symposium on Computer Science Education (pp. 323-324).

This is indeed an interesting way to link to all the sub-chapter-ish papers. I'm going to read through all the chapters to learn about the community and field in more depth.

# Thursday, Dec. 12th

## Reading _Harnessing Student Solutions to Support Learning at Scale_ { #harnessing_student_solutions_to_support_learning_at_scale }

> Wang, X. (2020). Harnessing Student Solutions to Support Learning at Scale (Doctoral dissertation, University of California San Diego (I think it should be CMU)).

To some extent, I think the current systems tend to use "Spatial Difference" learning (a word I made up, in contrast of "temporal difference") to predict human behaviors or make high quality contents? Like, the AI can't understand the true essence of contents, and it can only find what people similar to you is enjoying and make predicitions. How can we formalize the essense with in paints, movies, books, and papers?

I notice that the identification of misconceptions is indeed an important focus of the CS Education community. I wonder if there is any way to automate that. On the other hand, it seems that the heavy dependency on qualitative user studies is bringing a somewhat bad reputation, i.e., it is impossible to reproduce, to the HCI community. I'm looking for ways to study qualitative thoughts in a reproducible quantitative way.

# Wednesday, Dec. 11th

Today's main task is to work on the final project of CS415. I have gained a lot of experience with Unreal's animation system. I would say learning is, to some extent, understanding the original developers' problem-solving considerations.

One significant difficulty I encountered was that the animation montage was somehow not played. I didn't manage to find the answer on the web. After carefully checking the existing working blueprints, I found there needs to be a default selection node before outputting.

# Tuesday, Dec. 10th

I learned a bit about Blender's rigging system. I would say the design and the information needed between raw meshes and skeletal meshes are what I anticipated and guessed.

One significant difficulty I encountered was that I didn't know how to select a bone and view its affected vertices. It turned out that I had to pick the bones in the "pose mode", select the skin mesh, and then switch to the "weight painting" mode to solve that. Reflecting on that, I think that concern is pretty similar to my visualization design of enabling getting one node's information from both the visual position and the "graph" traversal point of view.

# Saturday, December 7th

I have been working on the consistency of quote styles.

https://www.howtogeek.com/microsoft-word-change-quote-style/

# Friday, December 6th

I have spent some time adjusting the links in the content part of my tome pages to target "\_blank" and understand how the header attributes in Markdown work. An interesting bug has happened: my "mdtome" uses the file system's modified time to track which files I need to rerender, and that turns out to be the reason why I didn't see the updates in code logic reflect on the resulting HTML: forgeting to "force" update.

## Reading _AI as a Resource_ { #reading_ai_as_a_resource }

> Donahue, K. (2024). AI as a Resource: Strategy, Uncertainty, and Societal Welfare (Doctoral dissertation, Cornell University). Link to her Personal Website: https://www.katedonahue.me/

> "The goal of my research is to view artificial intelligence as a societal resource used by self-interested agents who are often operating under some sources of uncertainty."

> "This framework models a setting where multiple self-interested agents each are trying to build a model that performs well on their own local distribution (which typically differs from the distributions of other agents, modeling the non-i.i.d setting)."

I wonder if we can model the "privileged bias" in similar ways. For example, if the population distribution of something is gradually changing with time, will the teacher models(who learned the parameters from previous distribution)'s estimation of the current students' learning be inaccurate? to what extent?, how different problems, like math education vs. economics vs. computer science affect the level of inaccuracy.

I haven't completely and carefully read the entire paper yet, but I'm curious about whether these distributions also apply to game learning agents with reinforcement learning. For example, if a chess master wants to hold his position, should they try to misguide their opponents with some weird gameplay "rewards," like trying to lead other players in the wrong exploring direction?

## Leetcode 2554. Day 852

I was in a relatively bad mood (the absolute magnitude is low, but still bad). You might be able to see that from my codes. I'm not carefully thinking about the suffix of my variables. I'm grateful that this piece of code passed the tests after two attempts.

```rust
pub fn max_count(mut banned: Vec<i32>, n: i32, max_sum: i32) -> i32 {
    banned.push(n + 1);
    banned.sort_unstable();
    let mut prev_banned_num = 0;
    let mut curr_sum = 0;
    let mut ans_count = 0;
    for banned_num in banned.into_iter() {
        // println!("{} {}", curr_sum, banned_num);
        if banned_num == prev_banned_num {
            continue;
        }
        let elem_num = banned_num - prev_banned_num - 1;
        let group_add_num = (prev_banned_num + banned_num) * (elem_num) / 2;
        if curr_sum + group_add_num > max_sum {
            for elem in (prev_banned_num + 1)..banned_num {
                if curr_sum + elem > max_sum {
                    return ans_count;
                }
                curr_sum += elem;
                ans_count += 1;
            }
        } else if curr_sum + group_add_num == max_sum {
            return ans_count + elem_num;
        }
        ans_count += elem_num;
        curr_sum += group_add_num;
        prev_banned_num = banned_num;
        if banned_num == n + 1 {
            return ans_count;
        }
    }
    ans_count
}
```

# Thursday, December 5th

I have spent some time implementing my design of a "graph group" that can present multiple graphs in one scene. I verified that my idea of using a "path" to identify and only use a part of a JSON file is feasible. That's a reflection of the idea of "spatial locality" from UIUC's CS233 course.

# Sunday, Dec. 1st

I'm personally interested in supporting students from underrepresented communities by building a system grouping course materials, lecture recordings, homework, assignments, and visualizations together, along with using assignment submission data like student codes to identify misconceptions, potential blind spots in teaching materials, find students who might need help, and personalize potential academic interventions.

My personal extracurricular activities mainly consist of designing my website, which can potentially be easily transformed into course materials, along with embedding interactive visualizations of abstract topics like data structures. I'm also trying to understand misconceptions and heuristics identification process through the board game Connect Four, hoping that developing a way to systematically teach Connect Four can shed light on teaching more complicated materials.

## _Understanding Children's Perception of Datafication Online in China_ { #children_perception_of_datafication_online_in_china }

> Zhu, Y., Wang, G., Li, Y., & Zhao, J. (2024). “It's Like How Mom Cooks for You, Tell Her Nothing You Only Get Chicken Soup.”: Understanding Children's Perception of Datafication Online in China. International Journal of Human–Computer Interaction, 1-19.

The authors have conducted interviews with Chinese middle-school-age children to get a better understanding of these children's perceptions of datafication practices. I think the researchers' design of using videos and metaphors to introduce the datafication concept is very considerate and kind.

> - Research Question 1: What are the current perceptions among children in China regarding datafication?
>
>   We identified three key knowledge gaps in children's perception of datafication practices, including their lack of recognition of their data ownership, the transmission of data across platforms, and the broader implications of datafication beyond video recommendation, such as inferences about their personal aspects.
>
> - Research Question 2: How, if at all, may children in China demonstrate any unique cultural traits regarding their perceptions of datafication?
>
>   Chinese children often talked positively about the use of datafication and big data for achieving "collective good for the whole society" and were generally less sensitive to how datafication practices could have impacts on them as individuals.
>
>   Research with Western children has shown that while parental influence remains significant for children in the age 13 group of 11–14, peer influence begins to play a more prominent role, making children more sensitive to interpersonal privacy risks.
>
> - Research Question 3: What kinds of designs and supports may be needed by Chinese children to help them navigate datafication?
>
>   Chinese children's emphasis on the practicality and factual accuracy of datafication, as well as the central role of families in their digital lives, suggest opportunities for designers to incorporate practical and real-world datafication examples and enhance family involvement in educating children about datafication.

## _CHAITok: A Proof-of-Concept System Supporting Children's Sense of Data Autonomy on Social Media_ { #reading_chaitok }

> Wang, G., Zhao, J., Johnston, S. K., Zhang, Z., Van Kleek, M., & Shadbolt, N. (2024, May). CHAITok: A Proof-of-Concept System Supporting Children's Sense of Data Autonomy on Social Media. In Proceedings of the CHI Conference on Human Factors in Computing Systems (pp. 1-19).

The authors have developed an experimental "social media" with cognitive autonomy, emotional autonomy, and behavioral autonomy design concerns in mind and conducted interviews with middle-school-age children to understand their perceptions of data autonomy and the experimental platform.

> - Research Question 1: How, if at all, do children currently experience and perceive the handling of their data on social media platforms?
>
>   A passive and disrespectful experience... As a result, children have shown great distrust in these social media platforms... Many children also expressed concerns about their data-related well-being on social media.
>
> - Research Question 2: How does CHAITok infuence children’s user experience and sense of autonomy over their data?
>
>   Sense of Security... Sense of Empowerment... Sense of Respect...
>
>   Lack of supporting context... Disinterest and lack of confidence...
>
> - Research Question 3: What are children’s expectations towards having data autonomy on social media platforms?
>
>   - Designs enhancing data safety and security.
>   - Designs supporting self-reflection of their data.
>   - Designs enabling users to create and control their own recommendation algorithms.
>   - Data Autonomy as deciding for your own data.
>   - Data Autonomy as resilience over own data.
>   - Data Autonomy as developmental competencies to be learnt.

I think the idea of building an experimental platform is very interesting. I wonder if it's possible to find different social media usage patterns or the general technology usage patterns from users with different levels of awareness of data autonomy, for example, if a user tries to intentionally view random contents just to make the algorithm's recommendation more natural.

### General Reflections

From CS + Education literature about finding student misconceptions, teaching system designs for instructors, and understanding human-centered AI for children, I think using interviews is a very common approach. Teachers conduct interviews with their students to get misconceptions during coding processes, and researchers ask instructors to evaluate novel teaching systems and children's perceptions of social media. I'm personally interested in conducting research to identify AI and human students' Connect Four misconceptions during their learning process and, therefore, maximize teaching efficacy. I wonder if there are ways to model perhaps the student coding process or social media usage, like a sequence of actions, and consequently find "super misconception" or different levels of privacy concerns on social media platforms.

I feel the lack of trust might be a general problem of highly specialized societies. The gap in experience and understanding between the general public and the software engineers and business elites might be just too big.
