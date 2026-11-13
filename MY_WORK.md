# 📝 MY_WORK: Student Information, Development Log, Reflection & Answers

> This is the **only file** your instructor reads to grade Parts 3 and 4 (documentation and video). Everything you write here must be **in your own words**.

---

## 🛑 STOP: Read This Before You Do Anything Else

> ### 1️⃣ Read the whole `README.md` first
> The `README.md` in this repository contains the full instructions: how this assignment continues Assignment 1, the Chapter 5 recap, class descriptions, feature specifications, question prompts and the video script. **If you skip it, you will lose marks.**
>
> ### 2️⃣ Understand the full code before answering any question
> Open `SchedulerSimulationSync.java` and read it **from top to bottom**. You must be able to explain what `SharedStats`, `ReadyQueue`, `CpuWorker`, `RaceWindow.pause()`, `ReentrantLock` and `Semaphore` do **before** you write a single answer in Parts B and C. **Run the original starter first** (it is intentionally broken) and **save its output**: you need it for Question 1 of Part C.
>
> ### 3️⃣ Use only the code of this repository
> Work **only** on `SchedulerSimulationSync.java` from this repository. Do **not** copy or paste code from your previous assignments.
>
> ### 4️⃣ Commit many times, not once
> A single commit, or all commits made in the last hour, costs you **-0.5 mark**. See the [Commit Rules](#-commit-rules-mandatory) below.

**How to use this file:**
1. Fill in your **Student Information** (below) right now.
2. Follow the steps in the **Work Roadmap** in order.
3. Update the **Development Log** *every time* you work on the assignment, not at the end.
4. Do not delete any section header. Replace the `[...]` placeholders with your own text.

---

## 👤 Student Information

> ⚠️ **WARNING:** Fill this in first. Your name and ID must match the student ID you set in `SchedulerSimulationSync.java` (line 304) and the one you say in your video.

| Field | Your Answer |
|-------|-------------|
| **Full Name** | [Mohammed Aldosari] |
| **Student ID** | [444052541] |
| **University Email** | 444052541@std.psau.edu.sa |
| **GitHub Username** | [Mohammed-Aldosari1] |
| **Repository Link** | [Paste your repository link here] |
 
---

## 🎥 Video Link

**Video Link**: [Paste your video link here]

> ⚠️ **WARNING:** The video must be **publicly accessible** ("Anyone with the link can view") on **Google Drive**, **YouTube (Unlisted or Public)** or any other cloud file-sharing system. A private, restricted or broken link counts as a **missing video (-1 mark)**.
>
> 💡 **TIP:** Open the link in a **private/incognito window** before you submit. If it asks you to log in or request access, it is not public.
>
> 📌 **NOTE:** The link goes in **this file only** (`MY_WORK.md`), **not** in `README.md`. Name your video file `StudentID_Assignment3_Demo.mp4`. It must last **2 to 3 minutes**.

---

## 🗺️ Work Roadmap (follow in this order)

| Step | What to do | Where | Marks |
|:----:|------------|-------|:-----:|
| 0 | Read `README.md`, read the full code, **run the original starter and save its output** (it fails on purpose) | Your IDE | – |
| 1 | Fork, rename, keep the repo **PUBLIC**, set your student ID (line 304), **commit** | GitHub + code | Part 1 (1) |
| 2 | Feature 1: Mutex lock on the ready queue, **commit** | Code | Part 2 (0.25) |
| 3 | Feature 2: Mutex lock(s) on the shared statistics, **commit** | Code | Part 2 (0.25) |
| 4 | Feature 3: Counting semaphore instead of busy waiting, **commit** | Code | Part 2 (0.5) |
| 5 | Development Log (5+ entries, different dates) | This file, Part A | Part 3 (0.5) |
| 6 | Reflection (4 questions) | This file, Part B | Part 3 (0.5) |
| 7 | Technical Answers (4 questions) | This file, Part C | Part 3 (0.5) |
| 8 | Record the video, upload it, paste the link above | Video + this file | Part 4 (1.5) |
| 9 | Final check, then submit the repo link on Blackboard | Blackboard | – |

> 💡 **TIP:** Tick each step off as you go. Do not leave the log, the reflection or the video for the last day.

---

## 🔁 Commit Rules (MANDATORY)

> ### ⚠️ MANY COMMITS ARE REQUIRED. A single bulk commit is penalized (-0.5 mark).

**Minimum: 4 meaningful commits. Aim for 7 or more.**

| # | Commit | Example message |
|:-:|--------|-----------------|
| 1 | Student ID set | `Set my student ID: 441234567` |
| 2 | Feature 1: Ready queue lock | `Feature 1: Protected the ready queue with a ReentrantLock` |
| 3 | Feature 2: Statistics locks | `Feature 2: Added locks to the shared statistics counters` |
| 4 | Feature 3: Semaphore | `Feature 3: Replaced busy waiting with a counting semaphore` |
| 5 | Development log entries | `Docs: Added development log entries 1-3` |
| 6 | Reflection and answers | `Docs: Completed reflection and technical answers` |
| 7 | Video link | `Docs: Added demo video link` |

**Rules:**
- ✅ **One commit per feature.** Do not put all three features in one commit.
- ✅ **Commit after each work session**, and after each part of this file.
- ✅ **Spread your commits over different dates.** Not all in one day.
- ❌ **Do not make all commits in the last hour** before the deadline (November 14, 2026).
- ❌ **No vague messages** like `done`, `update` or `final version`.

> 💡 **TIP:** Your commit history is checked and you **show it in your video** (at least 4 commits visible). Your development log dates should match your commit dates.
>
> 💡 **TIP:** **Use VS Code** (see *Recommended Development Environment* in `README.md` for the full setup). Sign in to GitHub in VS Code, then commit from the Source Control panel (Ctrl+Shift+G) → stage → write a message → Commit → Sync/Push. You can edit and commit this file the same way. **Pushing** matters: commits that are not pushed to GitHub are invisible to the instructor.

---

# Part A: Development Log (0.5 mark)

> ⚠️ **WARNING:** Minimum **5 entries**, spread over **different dates**. Five entries written on the same day, or written all at once at the end, will lose marks and look like a copy. Entry dates should be **between the start of the assignment and the deadline (November 14, 2026)**.
>
> 💡 **TIP:** Write an entry at the **end of each work session**, while you still remember what happened. It takes 5 minutes.
>
> 💡 **TIP:** Be specific. "Worked on the code" is a weak entry. "Added a `ReentrantLock queueLock` to `ReadyQueue` and wrapped the body of `poll()` in `lock()` / `try` / `finally { unlock() }`" is a strong one.
>
> 📌 **NOTE:** Each entry needs: date and time, what you did, details, challenges, solution, and time spent. Real challenges are fine (and expected). Do not invent fake ones.

## Example Entry (do not copy it, write your own)

### Entry 1 - [November 2, 2026, 4:30 PM]
**What I did**: Forked the repository, set my student ID, and ran the original starter

**Details**:
- Forked the starter repository and renamed it
- Changed student ID on line 304 to my actual ID (441234567)
- Ran the original program: 4 CPUs started, three of them picked `P1`, then `IllegalThreadStateException` and the watchdog stopped the program
- Saved the output in a text file for Question 1
- Committed and pushed: `Set my student ID: 441234567`

**Challenges**: I did not understand why the same process was picked by three CPUs

**Solution**: Read `ReadyQueue.poll()` again and found the `RaceWindow.pause()` between reading the head and removing it

**Time spent**: 45 minutes

---

## Your Development Log

### Entry 1 - [November 12, 2026, 7:00 PM]
**What I did**: I read the complete beginning code, set my student ID, and read the README.

**Details**:
In SchedulerSimulationSync.java, set studentID = 444052541.
Go top to bottom through SharedStats, ReadyQueue, CpuWorker, Process, and RaceWindow.
found the three features' TODO locations.

**Challenges**: did not comprehend the reason for RaceWindow.Between a read and a write, pause() is used.

**Solution**: I realized that it makes the race condition seem consistently by simulating the OS preempting a thread at the worst possible time.

**Time spent**: 3 hour

---

### Entry 2 - [November 12, 2026, 10 PM]
**What I did**: safeguarded the statistics that were shared.

**Details**:
ContextSwitchLock, completedProcessLock, and serviceTimeLock were added as ReentrantLocks.
In lock(), try, and finally { unlock() }, wrap incrementContextSwitch(), incrementCompletedProcess(), and addServiceTime().
used the identical locks to safeguard the three getters.

**Challenges**: choose one lock for each of the three variables or one lock for each.

**Solution**: Since the variables are independent, I only needed one lock per variable to prevent needless thread blocking.

**Time spent**: 2 hours

---

### Entry 3 - [November 13, 2026, 12 AM]
**What I did**: Feature 1: protected the ready queue.

**Details**: 
queueLock was added to ReadyQueue.
Lock(), try, and finally { unlock()} are used to protect add(), poll(), processOf(), and snapshot.

**Challenges**:
 Unreachable code issues resulted from old, unprotected code left under my new code, and unbalanced brackets caused insert "+" to finish ClassBody.

**Solution**: I added the missing finally in snapshot(), removed the outdated duplicate code in poll() and processOf(), and used the Problems panel to skip to each error.

**Time spent**: 2 hours

---

### Entry 4 - [November 13, 2026, 2 AM]
**What I did**: Feature 3: a counting semaphore took the role of busy waiting.

**Details**:
 Added Semaphore availableProcesses = new Semaphore (0).
called acquire() in acquireProcess() and release() in add() before to poll().
I make a single call to release(cpuCount) in signalShutdown(), protected by the shutdownSignaled flag.

**Challenges**: Knowing how to awaken the CPUs that are blocked in acquire() when there will never be another process introduced.

**Solution**: 
 One CPU releases one permit per CPU, just once, after the final process is finished.

**Time spent**: 2:30 hours

---

### Entry 5 - [November 13, 2026,4:30 AM]
**What I did**: Ran the finished program, checked the outcomes, and committed.

**Details**: Each of the four verification lines (24 context switches, 12 finished processes, 69984 ms service time, 0 busy-waiting polls) was . The code was committed and pushed.

**Challenges**:
 There is a last block missing and a typo (queueLook instead of queueLock).

**Solution**: Using the compiler messages in the Problems panel, I resolved both.

**Time spent**: 2 hours

---

### Entry 6 - [Optional - Date and Time]
**What I did**:

**Details**:

**Challenges**:

**Solution**:

**Time spent**:

---

## Development Log Summary

> 💡 **TIP:** Fill this in **last**, after all entries are written.

**Total time spent on assignment**: [11:30 hours]

**Most challenging part**: identifying the imbalanced braces, as the reported fault was far from the actual error, and comprehending how the CPUs are shut down by the semaphore.

**Most interesting learning**: observing the busy-waiting polls drop to zero with the semaphore and the missed updates vanish once every important area was secured.

**What I would do differently next time**: Save and compile after each minor edit, update the log at the conclusion of each session, and commit after every feature.

---

# Part B: Reflection (0.5 mark)

> 🛑 **STOP:** Do **not** start this part until you have read the `README.md`, read the **entire** `SchedulerSimulationSync.java`, run it, and finished the three features.
>
> ⚠️ **WARNING:** Each answer must be **5 to 7 sentences**, in **your own words**. Copied or AI-generated answers without understanding get **0 marks for the whole assignment**. You may be asked to explain them in person.
>
> 💡 **TIP:** Mention concrete things you actually did: a method you wrote, an error you hit, a line of output you saw. Generic answers score low.
>
> 💡 **TIP:** Draft your answer in a few bullet points first, then turn them into sentences.

## Question 1: What did you learn about synchronization?
 I discovered that a race issue occurs when many threads do a read-modify-write on shared data, such as contextSwitchCount = tmp + 1, and one thread overwrites another's change.I used lock() and try/finally { unlock() } to safeguard any important piece of the code that encounters shared data with a ReentrantLock. The finally block is important because it releases the lock regardless of whether the procedure throws an exception or returns early. so rather than repeatedly probing the queue, a counting semaphore allows a CPU to sleep until a process is available. I was taken aback by that RaceWindow.Almost always, pause() causes an uncommon issue to show up. The verification in my final test matched exactly: 24 context shifts, 12 finished processes, and 69984 ms of service time.

> 💡 **TIP:** Talk about race conditions (read-modify-write), critical sections, mutual exclusion with `ReentrantLock` and `try/finally`, the role of a counting semaphore, and what surprised you when the starter failed.

**Your Answer:** *(5-7 sentences)*

[Write your answer here.]

## Question 2: What was the most challenging part of this assignment?
 Correcting the grammatical mistakes brought on by uneven braces following my adjustments was the hardest task. The compiler reported inserting "!" to finish ClassBody at the end of the file, far from the actual error, due to a missing finally in snapshot(). As a result, ReadyQueue and CpuWorker appeared in Visual Studio Code as though they were nested inside other classes. Because the error message indicated a line that wasn't the cause, it was challenging. Unreachable code issues in poll() and processOf() were later triggered by outdated, unprotected code that remained after a return. I learned from this to carefully examine every error and to remove the old code after writing the protected version.
 
> 💡 **TIP:** Pick **one** specific challenge (understanding why the starter failed, choosing the lock granularity, the initial value of the semaphore, the shutdown of the CPUs, Git, the video) and say *why* it was hard.

**Your Answer:** *(5-7 sentences)*

[Write your answer here.]

## Question 3: How did you overcome the challenges you faced?
 I clicked on each error to jump to its precise line using the Problems window in Visual Studio Code. Additionally, I discovered where a brace was missing by using the breadcrumb and the sticky class headers to determine which class contained which code. After making each correction, I saved the file, checked the Problems section once more, and rectified one error at a time. When the Unreachable code arose, I removed the duplicate old code and fixed the mistake queueLook to queueLock. Ultimately, I executed the software and verified that each of the four verification lines was đ. I then go over each lock and the semaphore again to make sure I could justify their presence.

> 💡 **TIP:** Describe your method: reading the slides and the documentation, adding `System.out.println` to debug, running the program many times, re-reading the README, testing after each small change, asking for help.

**Your Answer:** *(5-7 sentences)*

[Write your answer here.]

## Question 4: Where can synchronization concepts be applied in real-world applications?
 Banking is a prime example: the balance update is a crucial area that is locked since two transfers on the same account cannot read the same balance and erase one another. Booking a ticket or a seat is comparable because two people cannot have the same seat. Similar to my ready queue, a print queue is a shared list that several threads add to and remove from, necessitating a lock for each access. Similar to my contextSwitchCount, a website visit counter produces an incorrect value when an update is lost. Semaphores work well in resource pools, such database connection pools, where threads do not poll until a connection becomes available. Each of these has a lock or semaphore, a vital portion, and shared data.

> 💡 **TIP:** Use real applications you know (banking and money transfers, ticket or seat booking, a shared counter on a website, a print queue, a database) and connect each one to what you built here (shared data, critical section, lock or semaphore).

**Your Answer:** *(5-7 sentences)*

[Write your answer here.]

### Optional: What would you like to learn more about?

[Any topics related to synchronization or operating systems that you're curious about?]

### Optional: How confident do you feel about synchronization concepts now?

[Beginner / Intermediate / Confident. What do you understand well? What needs more practice?]

### Optional: Feedback on the assignment

[Any comments? Was it helpful? Too easy or hard? Suggestions?]

---

# Part C: Technical Answers (0.5 mark)

> 🛑 **STOP:** You cannot answer these questions without understanding the code. Re-read `SchedulerSimulationSync.java` and **run it** first. Your answers must reference **your own code and your own output** (your student ID makes your output and your expected values unique).
>
> ⚠️ **WARNING:** Each answer must be **3 to 5 sentences**, with specific examples from your code or output. Use correct terms: race condition, critical section, mutual exclusion, mutex lock, semaphore, busy waiting, deadlock, producer, consumer.
>
> 💡 **TIP:** Keep the output of the **original starter** and the output of your **final version** in text files or screenshots, so you can copy real snippets for Question 1.

## Question 1: Race Condition in Your Own Output
The initial starter's verification revealed a discrepancy on [write the incorrect line, such as "Context switches: expected 24, observed XX"]. This is how a missed update occurs: CPU-1 calls RaceWindow after reading contextSwitchCount = 12 into tmp.pause(); CPU-2 reads 12 during the pause; CPU-1 writes 13 and CPU-2 writes 13, resulting in the loss of one increment. When the operating system preempts a thread between its read and write, the identical fault can occur on a real machine without RaceWindow. The failure is uncommon, random, and challenging to replicate because the window is only a few nanoseconds wide, making it difficult to detect.

Block of verification for the initial starter:

[Run the initial starter from the initial "init" commit and insert its verification block here]

Block of verification for my finished version:

VERIFICATION (your seed is used to calculate predicted values)
  Quanta conducted context switches: anticipated 24, observed 24
  Completed procedures: predicted 12, observed 12
  Total service time (ms): 69984 anticipated, 69984 observed
  Expected 0, observed 0, busy-waiting polls (must be 0), and all shared values are consistent.

An explanation of the timeline

ContextSwitchCount = 12 (stored in tmp) is read by CPU-1.
CPU-1 is "preempted" and executes RaceWindow.pause().
ContextSwitchCount = 12 is read by CPU-2.
13 is written by CPU-1 and 13 by CPU-2.
One update was lost because two quanta began but the counter only climbed by one.

**Question**: Run the **original starter** (before any fix) and paste the **verification block** of that run. Which value was wrong (expected vs observed)? Explain **step by step**, with two named threads/CPUs, how **one lost update** happens on one of the shared variables (read, `RaceWindow.pause()`, write). Why can the same bug happen on a real machine even without `RaceWindow`, and why is it hard to detect?

> ⚠️ **WARNING:** The snippet must come from **your own run** (with your student ID), not from a classmate or from this README.
>
> 💡 **TIP:** Use a small timeline: *CPU-1 reads `contextSwitchCount` = 12 → CPU-2 reads 12 → CPU-1 writes 13 → CPU-2 writes 13 → one increment is lost.* If your starter run crashed before printing numbers, run it several times (or paste the exception and the watchdog message and explain it).

**Your Answer:** *(3-5 sentences)*

[Write your answer here.]

Verification block of the **original starter**:
```
[Paste the verification block (or the exception/watchdog message) of the starter here]
```

Verification block of **my final version**:
```
[Paste the verification block of your final version here (all lines ✔)]
```

**Explanation of the timeline:**
[Explain the lost update step by step.]

## Question 2: Critical Sections and Lock Granularity
 Because the counters are independent, updating totalServiceTime does not require blocking an update of contextSwitchCount, therefore I used queueLock to secure the ready queue (list and map) and three different locks for the three statistics. The trade-off is that I have to manage more locks, but since I never hold two locks at once, there is no chance of a jam. Because the queue is utilized more frequently and safeguards different data, it has its own lock; sharing one lock would merely lead to conflict. Because only the thread holding the lock can execute the crucial portion and always releases it, mutual exclusion is maintained. Because a waiting thread always receives a free lock and because a default ReentrantLock

**Question**: List the **critical sections** you protected (variables and methods) and the lock(s) you used. **Lock granularity:** did you use **one lock** for the three statistics or **one lock per variable**? Why, and what is the trade-off? Why is the **ready queue** protected by a **different** lock than the statistics? Explain how your solution provides **mutual exclusion**, and discuss **progress** and **bounded waiting** (a default `ReentrantLock` is not fair: what does that imply?).

> 💡 **TIP:** The three counters are independent: does updating `contextSwitchCount` need to block an update of `totalServiceTime`? Also think about what could go wrong (deadlock, or long waiting) if the queue lock and the statistics lock were the **same** lock and a thread held it while doing something slow.

**Your Answer:** *(3-5 sentences)*

[Write your answer here.]

| Critical section (variable / method) | Lock used | Why it needs protection |
|---|---|---|
| [e.g., `ReadyQueue.poll()`] | [lock name] | [reason] |
| [...] | [...] | [...] |

## Question 3: Busy Waiting vs Semaphore
 A CPU in the starter wasted CPU time by repeatedly probing the queue after discovering it was empty; in my starter run, the Busy-waiting polls value was [paste the number from your starter run]. Because the queue is initially empty, the semaphore value in my version is 0, but after the 12 first add() calls, it is 12. My final run displays 0 polls because a CPU calls acquire() before poll(), blocking rather than spinning. When a process is finished, one CPU calls release(totalCPUs) (2 in this case), which causes the CPUs that are still blocked in acquire() to awaken, verify that every process has finished, and end. Without it, the program would be halted by the watchdog and they would have to wait indefinitely.

**Question**: Describe the **busy waiting** of the starter and its cost (give the `Busy-waiting polls` number from your **starter** run). What does the **value of your semaphore** represent? What is its **initial value** and why? What is its value right after the `numProcesses` initial `add()` calls? Why does the last CPU call `release(totalCPUs)` at the end, and what would happen if it did not?

> 💡 **TIP:** Think about what a CPU does when the queue is empty in the starter, and what a CPU does in your final version (is it running, ready or blocked?). Also check what happens to a CPU blocked in `acquire()` when no process will ever be added again.

**Your Answer:** *(3-5 sentences)*

[Write your answer here.]

## Question 4: Classical Problems and Deadlock
This is the Producer-Consumer (Bounded-Buffer) dilemma. I would use three semaphores if the queue had capacity K: empty = K, full = 0, and mutex = 1. By running acquire() before poll() takes the lock, my code prevents a deadlock that arises when a producer takes mutex before wait(empty). I would break the hold-and-wait condition to avoid that.

The Producer-Consumer (Bounded-Buffer) dilemma is a classic problem with roles. When they re-enqueue an incomplete process using add(), the CPUs are the producers (in the beginning). The CPUs that use poll() in a process are the consumers.

Semaphores (name and initial value) for a bounded queue:

empty = K (number of available slots)
full = 0 (number of slots filled)
mutex = 1 (buffer protection)

Deadlock scenario and prevention: A producer keeps mutex while waiting for a free slot if it takes mutex first and then waits on empty while the queue is full. In order to remove an item and free a slot, a customer needs mutex, which means both parties must wait indefinitely. As my code does with acquire() before poll(), I would always execute wait(empty) or wait(full) before wait(mutex) to break the hold and wait condition. I would use a fixed global lock order to break a circular wait if two locks were obtained in different orders.

**Question**: The CPUs and the ready queue look like a classical synchronization problem of Chapter 5. **Name it**, and say who plays the **producer** and the **consumer** roles (careful: here the CPUs also re-enqueue processes). If the ready queue were **bounded** (capacity `K`), name the **three semaphores** you would need and their **initial values**. Describe a **deadlock scenario** that appears if a thread acquired the **mutex before** waiting on the semaphore (or if two locks were acquired in different orders), and say **which of the four necessary conditions** you would break to prevent it.

> 💡 **TIP:** Recall the bounded-buffer solution of the slides (`empty`, `full`, `mutex`) and the order of `wait()` calls in the producer and the consumer. For the deadlock, think about a producer that holds the mutex while waiting for a free slot that only a consumer (who needs the mutex) can create.

**Your Answer:** *(3-5 sentences)*

**Classical problem and roles**:
[Name the problem; who is the producer, who is the consumer?]

**Semaphores for a bounded queue (name and initial value)**:
[Name the three semaphores and their initial values.]

**Deadlock scenario and prevention**:
[Describe the scenario and the necessary condition you would break.]

## Summary

**Key concepts I understood through these questions:**
1. A missing update in a read-modify-write on shared data is known as a race problem.
2. Try/finally and mutual exclusion with ReentrantLock, and why lock granularity is important.
3. Busy waiting is replaced with a counting semaphore, which requires the proper shutdown signal.

**Concepts I need to study more:**
1. Bounded waiting and fair locks.
2. How to avoid each of the four impasse situations.

---

# ✅ Final Checklist (complete before submitting)

> ⚠️ **WARNING:** Go through every line. Blackboard does not accept submissions after the deadline, which is **November 14, 2026**.

**Repository**
- [ ] Repository is **PUBLIC** (Settings → Danger Zone → Visibility)
- [ ] Repository is renamed to `OS-Assignment3-YourFirstName-YourLastName`
- [ ] GitHub account uses the university email (`@std.psau.edu.sa`)

**Code**
- [ ] Student ID is set in `SchedulerSimulationSync.java` (line 304)
- [ ] My code is based **only** on the starter of this repository (nothing copied from previous assignments)
- [ ] Code compiles and runs with no errors, and terminates by itself (no `⛔ WATCHDOG`)
- [ ] Feature 1 (ready queue lock), Feature 2 (statistics locks) and Feature 3 (semaphore, no busy waiting) all work
- [ ] **The four verification lines are ✔ in 5 consecutive runs**
- [ ] Every lock is released in a `finally` block
- [ ] `RaceWindow`, `Config`, the verification block and the watchdog are **unchanged**
- [ ] Each feature has clear comments

**Commits**
- [ ] **At least 4 meaningful commits, ideally 7 or more**
- [ ] **One commit per feature**
- [ ] Commits are spread over **different dates** (not all in the last hour)
- [ ] Everything is **pushed** to GitHub

**This file (`MY_WORK.md`)**
- [ ] Full name and student ID filled in at the top
- [ ] Development log has **5+ entries** on different dates
- [ ] Reflection: 4 questions, 5-7 sentences each
- [ ] Technical answers: 4 questions, 3-5 sentences each, with examples from **your** output (starter output **and** final output pasted in Question 1)
- [ ] No `[...]` placeholders left
- [ ] No section headers deleted

**Video**
- [ ] 2-3 minutes long, named `StudentID_Assignment3_Demo.mp4`
- [ ] Shows your name, ID, repository, 3 features (and your lock granularity choice), IDE execution with the verification block, one synchronization concept, and commit history
- [ ] Link is **public** (tested in an incognito window) and pasted in the **Video Link** section above

**Blackboard**
- [ ] Submit **only** the link to your public GitHub repository

> 🎯 **Good luck!** Start early, commit regularly, and make sure you can explain every line you submit.
