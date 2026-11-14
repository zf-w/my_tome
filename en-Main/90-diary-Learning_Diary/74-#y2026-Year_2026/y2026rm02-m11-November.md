---
description: "Nov. 2026."
tab_title: "Nov. 2026 - Diary - Zhifeng"
---

## Friday, Nov. 13th, Rainy

In the morning, I had to rewrite a code snippet for parsing upstream data into a format that I can directly put in my code, but it went quite smoothly.

### Random

- I'm grateful that Docker worked as expected when I went to run my code on another remote machine.
- I'm not sure what might be the best approach for pulling a private Git repository from a virtual machine on the cloud. I suspect it has to involve creating a new temporary SSH key, if you don't want to download things like the GitHub command line tool.
- I'm a little bit puzzled as to why my Ubuntu 26.04 doesn't support Zoom screen share (showing a black screen), probably due to missing software dependencies? 

### Trying to Reduce Plastic Usage

I also visited a local resaurant and asked about using my own glass container. I'm thankful that the clerk went to ask the manager(?). I'm still glad that I tried.

### Trying "A.I."-assisted Programming w. Swival

I gained more experience working with Swival, although "Claude Opus 5.5" provided my a somewhat over-complicated(?) solution. Imagine you need to mark and render some top rated items from a list. I'd like to try passing the "calculated" highest rating value and use a conditional logic to render the ones having the highest rating as "top", instead of passing a "Set" of calculated indices. I'm not sure if I completely understood "Claude Opus 5.5 on Swival"'s "idea" and "reasoning", but it was an interesting learning experience.

### Circuit Drawer

Implementing a circuit drawer can be quite interesting; it required a lot of code cleaning and "understanding" of the logic. I found myself thinking about Blender’s interface for inspiration.

### Gemma-4-12b's Follow-up

- **Q**: About the "Circuit Drawer", how did the "Blender" interface influence your design? (e.g., was it the way it handles "layers" or "properties"?)
  **A**: I'm thinking about how Blender handles its interface interaction state and gives user hints about possible actions. That was really helpful. 

- **Q**: How did the rain affect your productivity? Did the rainy weather make the "coding" feel like a cozy task?
  **A**: I think the cold weather is better for keeping my mind relatively sharp, but it doesn't make "coding" feel like a cozy task in particular. 



# Tuesday, Nov. 10th, Sunny

I find the weather is often surprisingly good after I had a all-nighter study session, which is kind of sad.

## Reflect on LLM Agent Experience

I feel that `Claude Opus 5.5 on Swival` provided me a fairly nice, yet somewhat architecturally hasty approach to implement the desired behavior on top of the existing codebase.
I deeply appreciate the help.
Although I changed it a lot before testing it, I guess the original modification would also have worked.
One interesting thing I noticed was a typo.
As I can recall, I have encountered the typo before, mistyping `form_idx` into `from_idx`.
Both interpretations "work" in the semantic context, but, while the model sets the field as `form_idx` on the client side, it tries to access the `from_idx` on the server side.
Maybe I misunderstood it or the mistake was mine, but I guess symptom was indeed aligning with the foundamental mechanism of LLMs.
I guess it would indeed be very hard to determine what is what when there is a nearby typo.

I'm grateful for the model's help.
I also learned a lot.
Building a consistent and hopefully maintainable architecture is indeed quite challenging.

## CS500 Presentation

I'm quite poor at public speaking and speaking in general.
I'm grateful I had the chance to practice it via the paper presentation activity. 

# Monday, Nov. 9th

I'm grateful that `Claude Opus 5.5 on Swival` helped me to kick-start a large upgrade.
I specifically appreciate how it tried and managed to understand my coding practice and naming style.
How do LLMs turn variable names into tokens must be a complex, carefully engineered design.
One downside might be that the agent sometimes drift off-task to fix minor issues that I was planning to adjust later.
Another concern is the lack of "meta-understanding" (?).
For example, when the LLM is working on a codebase that is under style transition or other complex constructions, it might choose the fast and easy approach instead of trying to guess the user's ideal final target.
I guess that would be indeed be a super challenging task for all intelligence.   

# Thursday, Nov 5th, Rainy

The past few days have been quite intense for me.

## Spiders

I found the two spiders moved to a new location. I'm worried about them producing more offspring.
Also, since they were pretty close to the floor, I was concerned about my daily mopping and cleaning might hurt them.
I decided to use a jar to capture them and set them free in a nice park.
If I were the spider, I guess I'd like to die in a beautiful park rather than live and eventually die in a small apartment.

Capturing of the first spider was quite smooth.
My mason jars suit this task in some sense.
I was able to slide the lid between the floor and the jar to contain the spider.
However, unfortunately, when capturing the second spider, after containing the spider with the jar, I tried to gently move it to an open space a bit further from the wall.
I might have accidentally crushed it while sliding the jar across the floor. May the spider rest in peace. I remembered it trying to eat something(?) before I took action. I hope it didn't suffer.
I managed to set free the first spider in a fairly large and beautiful park.
I saw a bunch of insects living there. I hope it will manage to live.

On the next day, I found another two spiders, a bigger one and a smaller one compared the two I saw yesterday.
I can see the joints on the large spider's leg compared the small ones, but I guess they are still the same type of spider.
I managed to capture the big one on the wall, but the small one managed to escape and disappeared.
I'm not sure about their relationships and whether the smaller spider chose to stay on the yoga-mat roll.
Since it's not a flat surface, the spider managed to escape. Nice move!
I went to the park again and set the large spider free.
I'm sorry that I might have damaged one of its legs during the process.

# Monday, Nov. 2nd, Cloudy

I'm grateful that I have prepared a hamburger for the "breakfast".

## Defensive CS Ed Environment

The most interesting one would be the _Defensive Climate in the Computer Science Classroom_ by Barker et al.
I'm heartened to see researchers focusing on student well-being, especially regarding the marginalized groups within CS education.
Indeed, the culture of Computer Science can often make people feel excluded.
Whether intentionally or unintentionally, instructors and the "tech bros" tend to create a "superiority-focused", hierarchical, impersonal atmosphere.
Their attitudes, combined with automatic grading and the rise of Large Language Models, can create a defensive and isolated environment for students.
It's disheartening to see how even marginalized groups can sometimes form sub-marginalized group that further divide the community.

## Gen AI Study Stress Testing

I have participated a stress-test for a GenAI usage experiment. The LLMs are quite powerful and, at the same time, potentially disempowering.

## Pizza Box Recycling

Reheating and recycling pizza box can be quite tricky.
I learned that 375 F for 15 minutes in a conventional oven might be a good option for reheating pizza.
While the county recycling guide suggests they do not accept pizza boxes, the pizza box itself is marked for recycling.

# Sunday, Nov. 1st, Cloudy

The two spiders didn't move from their spots. I'm grateful for that.
I tried KeePassium on IOS. It's a little bit weird that my iPhone is having problem recognizing my portal drive, while my iPad is able to do so. I'm grateful that it worked on my iPad.
Green St. was super crowdy today. I didn't notice or experience that during previous Halloweens. Picking up my McDonald mobile order took my about fifteen minutes, but it seems they gave me extra 4 chicken nuggets.
I considered going back and correct this issue. But considering they have also gave me 1 less chicken strip before and the crowdy waiting customers, I decided to not to go back.
I tired Mullvad browser. I'm thankful that it can "defingerprint" browser agent metadata and set the page window resolution to a fixed value. 
I tried the helix text editor. Learning a new way of text editing and programming feels great to me. I have been trying a lot of new things recently, and that feels great.
