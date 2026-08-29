---
description: "August 2026."
tab_title: "August 2026 - Logs - Zhifeng"
---

# Friday, August 28th, Champaign, Sunny

## Takeaway and Recycling

Today, I noticed that the "dine-in" meal containers don't come with lids. I think this could help me further reduce my plastic use. I'm wondering if it’s safe to reuse the lids I already own so that I don't have to transfer my food into a separate container when I'm at a restaurant.

## Reflecting on Cunningham et al., “Bringing ‘High-Level’ Down to Earth.”

1. Do the abstraction layers completely hide lower level details? For example, when playing MineCraft, a player might need to understand binary numbers to understand why numbers like 64 and 32768 frequently occur in the game system design. Furthermore, another example I can think of would be crashing. Crashes often happen at a low level, where things can go irrecoverably wrong very quickly.
    
2. I guess one of the reasons why programming educations go bottom-up is that the pattern aligns with the development of computer science (from logic gates to assembly code to programming languages). I remember a professor trying to explain an encoding/decoding error, which is related to UTF-8 and the history of it; the process was a little bit difficult. I guess that’s due to students who grew up in the era of App Store hardly encounter those low level errors in their daily lives.

## Reflecting on Chen, WIP: Low Effort, High Grades? Benchmarking LLMs on Various Engineering Assignments.

1. While mathematical methods like induction can prove an algorithm's correctness for all valid inputs, it is difficult to apply similar verification to LLMs.
    
2. A key question arises: Of the many variants of a single assignment assessing the same knowledge, how many can one LLM correctly answer? Does it succeed on all of them, or does it fail on specific ones?

# Thursday, August 27th, Champaign, Sunny

## Joining School WiFi

This is the first time I brought my newly installed Ubuntu virtual machine to school. When joining the school WiFi, a window popped out and asked me to input several pieces of information, including username, password, and CA certificate. After I entered the username and password, the submit button remained inactive and unclickable. I recalled my experience joining the WiFi on my Windows machine and realized that the CA certificate might be related to the "trust or not trust" and "do you expect this WiFi to occur" prompt. I chose to not provide the certificate; the button became clickable, and I was able to join the WiFi. I'm grateful that it worked out quickly as time is often limited during class discussions.

# Friday, August 21st, Sunny

## "Moving" into VM

Setting up a new operating system is like moving into a new house. I'm learning to use virtual disks to make the system more modularized and probably safer. One interesting thing happened when I tried to mount a drive to the home directory. I'm wondering if I can use the mounting of a different 'home drive' technique to achieve a quick workspace swap and isolate different workspaces. 

After rebooting the system, the system re-prompted me about the initial set up options, like location services. I guess mounting the new drive removed the previously stored information about the initialization.

I noticed that I forgot to take notes on adding the "user.signingkey" and the "gpg --keyid-format=long". I researched the Internet and found the answers.

# Wednesday, August 12th

Today is a rainy day.

## Learning CMake 

I have been reading the CMake tutorials. I'm grateful that the community **has** designed these tutorials for beginners. I have completed steps 2 through 4. I found the most difficult part **so far to be** the "ARGN" part. It took me some time to realize **that the "list" is passed to the function via remaining arguments rather than as a second list argument.**

I also recalled that one of the TAs for CS423 FALL 2025 recommended using "clangd" to make development easier. I **searched** through the Piazza forum for the course to find the post. I'm grateful that Piazza has archived **that** the posts.

### References
- *CMake Tutorials*, "https://cmake.org/cmake/help/latest/guide/tutorial/index.html"
- *CMake Tutorials: CMake Language Fundamentals*, "https://cmake.org/cmake/help/latest/guide/tutorial/CMake%20Language%20Fundamentals.html"

## ARGON2

I'm grateful to have encountered the algorithm I read about in a book a month ago. What an interesting **coincidence**! I'm learning how to make a simple application that allows me to input passphrases via standard input instead of command-line arguments, and I'm also studying the design of OpenSSL and how to call its functions. I'm not sure why OpenSSL **designed** its command-line tool to receive passphrases from command-line arguments.

I learned how to disable **terminal echoing of the standard input** and use standard error for prompting.

## SSH Agent

I found **that** I would prefer **inputting** the SSH key passphrase instead of letting the SSH agent handle the **repetitive** task for me. I reviewed how to set the SSH configuration file.

# Monday, August 10th

## Making SVG for Bottle Customization

I'm planning to design a digital signature related pattern to stylize my water bottle. Making a vector graphic to send to the merchant becomes a crucial task. I'm grateful there exist applications like Inkscape to help me transform fonts into path "geometries". I haven't sent my design to the merchant yet, but I hope I can save some of their efforts on finding fonts. To realize this idea, I have been working on:

- Looking for a code friendly font that distinguishes characters like "0" and "O".

- Trying to use my previous graph coarsening methods to stylize my code-inspired "pattern". I'm grateful that my previous Rust programs and Jupyter notebooks continue to work, and the transfer of those programs to my virtual machine workspace was quite smooth. I'm very thankful.

- I have verified my design with OpenSSL on various platforms. I had some fun compiling it on Windows. One major bug I encountered was the "missing stdlib". After some searching, I realized that I need the "Windows SDK" for the compiler to find the relevant files.

- I'm grateful that I had the chance to practice with transporting files between different virtual machines.

- It's quite interesting that the e-commerce platform seems to be flagging Ubuntu machines, and I switched to a Windows virtual machine. Then, the website stopped sending me bot-checking pop-ups. 

# Thursday, August 5th

## OpenSSL Argon2ID

I have been exploring ways to manage passwords, instead of burdening applications to manage my passwords. I'm grateful that the command line arguments naming align with the library constants naming.

### Reference:

Quoted from: *OpenSSL Documentation: EVP_KDF-ARGON2*, https://docs.openssl.org/3.3/man7/EVP_KDF-ARGON2/#supported-parameters

- "pass" (B<OSSL_KDF_PARAM_PASSWORD>) <octet string>

- "salt" (B<OSSL_KDF_PARAM_SALT>) <octet string>

- "secret" (B<OSSL_KDF_PARAM_SECRET>) <octet string>

- "iter" (B<OSSL_KDF_PARAM_ITER>) <unsigned integer>

- "size" (B<OSSL_KDF_PARAM_SIZE>) <unsigned integer>

- "properties" (B<OSSL_KDF_PARAM_PROPERTIES>) <UTF8 string>

  These parameters work as described in L<EVP_KDF(3)/PARAMETERS>.

  Note that RFC 9106 recommends 128 bits salt for most applications, or 64 bits
  salt in the case of space constraints. At least 128 bits output length is
  recommended.

  Note that secret (or pepper) is an optional secret data used along the
  password.

- "threads" (B<OSSL_KDF_PARAM_THREADS>) <unsigned integer>

  The number of threads, bounded above by the number of lanes.

  This can only be used with built-in thread support. Threading must be
  explicitly enabled. See EXAMPLES section for more information.

- "ad" (B<OSSL_KDF_PARAM_ARGON2_AD>) <octet string>

  Optional associated data, may be used to "tag" a group of keys, or tie them
  to a particular public key, without having to modify salt.

- "lanes" (B<OSSL_KDF_PARAM_ARGON2_LANES>) <unsigned integer>

  Argon2 splits the requested memory size into lanes, each of which is designed
  to be processed in parallel. For example, on a system with p cores, it's
  recommended to use p lanes.

  The number of lanes is used to derive the key. It is possible to specify
  more lanes than the number of available computational threads. This is
  especially encouraged if multi-threading is disabled.

- "memcost" (B<OSSL_KDF_PARAM_ARGON2_MEMCOST>) <unsigned integer>

  Memory cost parameter (the number of 1k memory blocks used).

- "version" (B<OSSL_KDF_PARAM_ARGON2_VERSION>) <unsigned integer>

  Argon2 version. Supported values: 0x10, 0x13 (default).

- "early_clean" (B<OSSL_KDF_PARAM_EARLY_CLEAN>) <unsigned integer>

  If set (nonzero), password and secret stored in Argon2 context are zeroed
  early during initial hash computation, as soon as they are not needed.
  Otherwise, they are zeroed along the rest of Argon2 context data on clear,
  free, reset.

  This can be useful if, for example, multiple keys with different ad value
  are to be generated from a single password and secret.

### Usage
```bash
openssl kdf -keylen 32 -kdfopt pass:$PASSWORD -kdfopt hexsalt:$SALT -kdfopt ad:domain:example.com -kdfopt iter:128 -kdfopt lanes:64 -kdfopt memcost:65536 -binary ARGON2ID | openssl base64
```

# Wednesday, August 4th

## CPU Isolation

In addition to isolating the GPU, I learned how to isolate CPUs for the virtual machine. I tested *Resident Evil 4 Remastered* on a Windows VM both before and after applying CPU isolation. Personally, I didn't notice a significant difference in performance. However, I did find that running the game on an Ubuntu VM with Steam Proton felt smoother than running it on a Windows VM. 

I also noticed an option in the Legion BIOS regarding "Dynamic GPU" versus "Dedicated GPU." I am not entirely sure what this setting entails, but switching to the "Dedicated" option did not work as expected.

### References
- *Create KVM with Full GPU and CPU Passthrough*, [https://github.com/HarbourHeading/KVM-GPU-Passthrough](https://github.com/HarbourHeading/KVM-GPU-Passthrough)

### Edit the Grub
Add the following attribute to `GRUB_CMDLINE_LINUX_DEFAULT`:
```bash
isolcpus=8-15
```

### Edit the VM Configuration
```xml
<!-- Inside VM Configuration XML -->
<cputune>
  <vcpupin vcpu="0" cpuset="8"/>
  <vcpupin vcpu="1" cpuset="9"/>
  <vcpupin vcpu="2" cpuset="10"/>
  <vcpupin vcpu="3" cpuset="11"/>
  <vcpupin vcpu="4" cpuset="12"/>
  <vcpupin vcpu="5" cpuset="13"/>
  <vcpupin vcpu="6" cpuset="14"/>
  <vcpupin vcpu="7" cpuset="15"/>
  <emulatorpin cpuset="7"/>
</cputune>
```

### Check CPU Affinities
```bash
# Find the main QEMU process
ps -eo pid,cmd | grep -E '[q]emu-system|[k]vm' | grep -i $YOUR_VM_DOMAIN_NAME

# Find the threads (Example PID: 6056)
ps -T -p 6056 -o pid,tid,psr,comm 
```

