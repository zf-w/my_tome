---
description: "Nov. 2026."
tab_title: "Nov. 2026 - Diary - Zhifeng"
---

## Monday, Nov. 23rd, Sunny

### Fortune Cookies and Bottle Caps

- "There's enough to go around."
- "You will make a change for the better."
- "You are open and honest when it comes to matters of the heart."
- "Your road to glory will be rocky, but fulfilling."
- "Seek new challenges."
- "You create enthusiasm around you."
- "Your kindness will lead you to success."
- "Your next decision will deliver unexpected happiness."
- "The key to happiness is reasonable expectations."
- "Never let the fear of striking out keep fou from playing the game." - Babe Ruth

### Reviewing Receipts

I am grateful to the people that prepared, crafted, and processed my meals.

## Thursday, Nov. 19th, Sunny

### Implemented a Circuit Grading Logic

I implemented a circuit grading logic on the server side. Some important steps includes deserializing the student circuit and evaluating all possible combinations of input and checking the output against the ground truth circuit.

The time was a bit limited. I'm grateful and relieved that I was able to deliver this part kind of on-time.

I have encountered three major interesting bugs during the development process.

- Every thing evaluates to None, and the queue popping loop only loops one time. It turned out to be a bad indentation in a piece of Python code. The return logic got caught in the next node popping loop, where it should not be.

- Weird gate got evaluated first: turned out to be Python list pop method was actually popping the last element. I thought it was popping the first.

- Component evaluation logic encountered a null value. It turned out to be a typo. The queue appending logic was supposed to be appending the gates which all the input data were determined, but I instead checked the number of determined input against the number of output of those components.

### Project Politics

Group project politics can be very exhaustive.

### The Spider

I finally found the previous (?) escaped spider. I knew we were going to see each other again. I hope it and I can peacefully share my room.

### Diligently Wiping and Cleansing

Wiped the dining table and the dish washer surface. I'm grateful I had some time to do this.

## Wednesday, Nov. 18th, Sunny

### Random

- **Just Ice Tea**: "Justice, justice shall you pursue." - The Bible

### Two Bugs I Encountered Yesterday

When implementing a graph structure, I noticed the edge deletion was reporting errors about deleting unkonwn edges. After some debugging, I realized it was not due to problems in the graph, but a click event doubly firing from a single action.

When working on serialization and deserialization of that graph structure, I noticed a few edges went missing after deserialization. After some investigations, I noticed that the serialized string was not updated after edge creation, not a problem from the deserialization part.

I'm grateful those things worked in the end.

## Monday, Nov. 16th, Sunny

### Random

- **Just Ice Tea**: "When I let go of what I am, I become what I might be." - Lao Tzu (Not an authentic quote, loosely translated from "Bowed down then preserved; Bent then straight; Empty then full; Worn then new; A little then benefited; A lot then perplexed.")

- Cleaning benefits me personally, while coding for course works or projects might not, at least not completely.

## Sunday, Nov. 15th, Sunny

### Random

- Tried a type of wipe tissue specially designed for cleaning stainless steel surfaces. I'm grateful and relieved that it worked and made the fridge shiny.

### Reflect on Mopping

When mopping the floor recently, several thoughts came into mind. The first one was, similar to how sweeping the floor makes you notice and care about small details, dust, and traces on the floor, my experience learning to program also kind of shares this characteristic. Reading and learning CS encourages you to dig and dive and at least try to understand and be considerate to every details.

Another thought was about empowerment. In some ways, programming offers a unique opportunity: it not only enables people but also encourages people wanting to do things differently to design and use their own program, without relying, at least to some extent, on the main stream solution or the mainstream ideas. That empowerment can be way beyond independently writing a program. It's about a way of life.

I do personally have practices of cleaning that, I guess, are different from the main stream. For example, beyond diligently recycling different types of items, I take photos of items that helped me to do the cleaning, for example various types of tissues for cleaning different surfaces. I feel like that's a way of honoring and showing respect to their help and sacrifice. It not about whether they can feel or not, maybe they can, maybe they cannot. This practice is more about honoring and documenting a kind of characteristics, metaphors, and virtues that I value, as well as building a consistent world view in my heart.   

## Saturday, Nov. 14th

### Random

- **Just ICE Tea**: Failure is just data on how to succeed next time. - Grace UnHae Kwon

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

# Thursday, Nov. 12th

## Previous Server Design

Spending more time on my previous implementation, I remembered the reason why I set up a `ServerState` design was that I was planning about testing the server logic and making the dependencies clearer. I noticed that the LLM somewhat took the shortcut.


# Wednesday, Nov. 11th, Sunny

## Fortune Items

- Just Ice Tea: The sun shines not on us but in us. The river folow not past, but through us. - John Muir
- Just Ice Tea: History doesn't repeat itself, but it often rhymes. - Unknown
- Panda Express: You are a fun-loving person and will find much happiness.
- Panda Express: A refreshing change is in your future.
- Panda Express: Meet your partner half way.

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
