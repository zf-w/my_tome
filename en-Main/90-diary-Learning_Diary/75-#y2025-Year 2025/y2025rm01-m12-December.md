---
description: "December 2025."
long_title: "December 2025 - Diary - Zhifeng"
---

# Tuesday, December 9th

I'm thankful that the staff at Jurassic Burger allowed me to use my own lunch box to take my burger away. The staff is thoughtful and careful. He noticed some water drops remained in my lunch box and wiped them with a tissue. I deeply appreciate that. I will be more careful with that next time. I guess it's indeed true that water left at the bottom of containers will affect taste of food.

# Friday, December 5th

## CS440 MP11 Reinforcement Learning

I have spent around half a day completing the final Machine Problem assignment. I'm grateful that I have completed the assignment and learned knowledge.

The first challenge I encountered was mysterious incorrect N table and Q table updates. To debug this issue, I have implemented several visualization utilities to use characters to print out the game scene and make my debugging process largely easier. I noticed that, even though the "early checking testcases" are not testing on finding the best actions based on the N and Q table and instead using a fixed sequence of actions, I still didn't get the N and Q table correct. With some further digging, I found that the model was actually visiting wrong states: some states that should be visited were not visited, and vice versa. Finally, I found that my code was recognizing states from game scenes in the wrong way: my tie-breaking for comparing values of big fruit and small fruit is wrong; instead of chasing small fruit when there is a tie, my code chases the large fruit.

The second group of challenges emerged from careless copying of codes with similar structures and forgetting to edit them to suit the desired functionality. For example, I have already written a piece of code for finding the maximum next value. In another place, I need codes to find the "argmax" of next values, and, since the logics are similar, I reused my previous code for finding maximum without adding logic for updating the "argument", resulting in the "argmax" only returning the first argument.

The third challenge was that I thought I should only update the N and Q tables during the training part. In the end, I realized that I should also update them in the testing session, just not "exploring" and only "exploiting".
