---
description: "Oct. 2026."
tab_title: "Oct. 2026 - Diary - Zhifeng"
---

<<<<<<< Updated upstream
# Saturday, Oct. 17th, 2026, Sunny
=======
# Saturday, Oct. 31st

- Just ICE Tea: "If you are too busy to laugh, you are too busy. - Unknown"
- Just ICE Tea: "Great spirits have always encountered violent opposition from mediocre minds. - Albert Einstein"
- Just ICE Tea: "Those who say it cannot be done should not interrupt the people doing it. - Chinese Proverb"

# Wednesday, Oct. 28th, Sunny

I wondered why did the previous design use `elem[0]` to get an HTML element. It turned out it used "queryByName" instead of "queryById".

After some modifications on other issues and went back to this issue, I forgot to switch to the "byId" and remove the indexing. That's funny.

Without the help of IDE autocompletion, the previous developers made some typos trying to access non-existent variables. 

# Oct. 16th, 2026, Cloudy 
>>>>>>> Stashed changes

## Resources Note

- https://github.com/drduh/YubiKey-Guide

# Friday, Oct. 16th, 2026, Cloudy 

# Thursday, Oct. 15th, 2026, Rainy

## Debugging Debian Wayland

I have been trying to set up a Debian 13 virtual machine with a passed-through GPU. 

The primary symptoms are that the guest OS was unable to stably identify the monitor connected to the GPU, and I experienced persistent screen freezes when using the Spice virtual QXL screen. While the primary laptop screen froze, the external monitor remained active, allowing me to move my cursor there.

I'm grateful that the virutal machine set up allows me to experience various different Operating Systems coupled with different desktop environments, for example Fedora Gnome, Fedora KDE Plasma, Debian Xfce, Debian Gnome, and Debian KDE Plasma. During this process, I noticed that it seems only Wayland is able to properly detect and use the dedicated GPU instead of the virtual one to render windows and find the external monitors connected to the passed-through GPU.

After settling on desktop environments that support Wayland, I noticed that Debian somehow switched back to X-org. After some chats with Claude Sonnet medium, The system was defaulting to the virtual QXL as the primary card. The "udev" rule was likely checking for the presence of a virtual GPU and automatically opting out of Wayland if the OS set up was detected as having a GPU pass through. I commented out that section detecting virtual machine with GPU passthrough, and Wayland went back. Even though the "vga_boot" is still the virtual GPU, as long as windows still in window form or borderless window, the screen doesn't freeze anymore. I used to believe that Ubuntu and Fedora somehow fixed the virtual monitor rendering issue, but I guess it turned out they were just using borderless window. 

I also learned from Claude that, sometimes, the monitor also needs a fresh handshake for the OS to detect it, so re-plug-in the cable might be helpful.

By the way, it was indeed inconvenient for me to chat with a local LLM on a frequently rebooting Virtual Machine. I'm thankful that Claude provides a mobile APP, allowing me to debug my machine. 

## Event Device Keyboard

Another issue for me is that the default "ctrl-alt" keyboard doesn't allow me to use super key and some hotkeys in the guest OS. Even though previously I have found to use "evdev" to fully pass the keyboard control to the guest OS, I didn't know it's possible to switch back under that setting. However, Claude Sonnet Medium taught me that it's actually possible. After some searching, I was able to set up a "ctrl-ctrl" hotkey to swtich between operating systems. I'm glad that it worked.

# Oct. 12th, 2026, Sunny

## Baking Frozen Food

The geometry of frozen food items (even from the same product) can be very different. Sometimes a piece fits perfectly into my glass bakeware; other times, the shape prevents it from fitting. Larger baking dishes often leave too much empty space, resulting in food on the outer "border" edges to overcook. This time, I chose to montior the food closly, eventually moving the food to a smaller and more compact bakeware once the food became hot and soft. I'm grateful it worked.

## Small Things

- **Learning Docker**: I fixed several bugs and explored Docker concepts like volumes, images, and containers. Strategizing which modifications require a "sync" versus a "rebuild" requires careful planning.
- **Copy by Reference Bug**: I noticed an interesting "copy-by-reference" bug where an action on one page caused changes on a totally irelevant page even after page refreshings.
- **Interacting with GitHub Issues**: The design of issues provides a way for programmers to document their daily work and progress. I guess it also provides a considerable amount of data for machine learning.

## Language Usage Observation

When someone uses English as their professional language but keeps their native tongue for personal devices, concealing their native language is nearly impossible. It leaves a trail of digital traces: email auto-replies and the "reply" word before messages, default file titles, browser bookmarks, and specific punctuation marks. It is nearlly impossible to hide the linguistic DNA of a person's native culture.

# Oct. 11th, 2026, Sunny

I have been experimenting with different types of "conventional-oven-cooked" frozen food. They looked healthy and I'm grateful.

I tried to install a Debian operating system and test if it, combined with "gnome", works with Bluetooth. It seems there was a problem in "gnome", when using it, only one of microphone and speakers can work. Fedora worked. So I guess I will be trying "KDE Plasma" with Debian next.

# Oct. 10th, 2026, Sunny

I noticed the spider web near the back door of my apartment; the spider seems to have already repaired the broken web. It is breathtaking. Looking up from the ground, it is astonishing to see how much of the wall is covered in silk. I wish I could be so skillful with my own creations.

# Oct. 8th, 2026, Sunny

- **Experimenting Fedora OS:** Created a Fedora virtual machine and experienced its interface.
- **Bluetooth Passthrough:** Tried to pass through the Bluetooth device into the VM. Forgot to remove the bluetooth modules on the host machine. Realized that and confirmed with LLM.
- **Room Cleaning**. Used garbage disposal to clean some of my roommate's leftovers, and cleaned some of my remaining plastic packets and paper bags.

## Usability Testing

I'm grateful that my preparation worked fairly well. I'm grateful that one of my classmates from another team complimented my performance on their usability test. I also uncovered an inconsistency in their README.

# Oct. 6th, 2026, Sunny

## Small Things
- **The Stairway:** There was a piece of abandoned cardboard in the stairway. It had been sitting there for a few days. I finally took the time to break it down and place it in the recycling bin.
- **The Food:** I noticed that the packaging for many of my "healthy" frozen meals is marked as non-recyclable.
- **System Logs:** The webcam is passing through the VM via Cheese (X11) and Zoom.
- **The Grocery Store:** While I was trying to select a shopping basket, a store assistant was organizing the shelves. I whispered "excuse me" to him—the basket was quite close to his face, and I didn't want to startle him. He thought I was asking a question. I pointed at the basket and mumbled, "No, no, I was just trying to pick up a basket." I’m glad he seemed to understand. Later, after I checked out, he said, "Have a great night." I echoed back, "Thank you. Have a great night," and he replied, "Thank you, and you too."
- **Panda Express:** It seems they have stopped using paper plates for the "plate" option (two entrees with one side).
- **Roommate:** I washed my roommate's two dirty dishes and recycled one of his bottles.
- **Stack Memory:** Read about how zero/initialization might lead to more entries being copied to stack memory.