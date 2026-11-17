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
| **Full Name** | Tief Aljallal |
| **Student ID** | 444052215 |
| **University Email** | 444052215@std.psau.edu.sa |
| **GitHub Username** | Tief-dev |
| **Repository Link** | https://github.com/Tief-dev/OS-Assignment3-tief-aljallal |
 
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

### Entry 1 - November 17, 2026, approximately 7:09 PM

**What I did**: Started Assignment 3 and set up the GitHub repository.

**Details**:
- Reviewed the assignment requirements.
- Forked the starter repository and renamed it `OS-Assignment3-tief-aljallal`.
- Opened the project in VS Code.
- Updated my student ID to `444052215`.
- Configured Git and connected the repository to GitHub.

**Challenges**: Getting familiar with the assignment structure and GitHub workflow.

**Solution**: Followed the setup process step by step and checked the repository configuration before modifying the synchronization code.

**Time spent**: Part of the November 17 work session.

---

### Entry 2 - November 17, 2026

**What I did**: Implemented Feature 1, ready queue synchronization.

**Details**:
- Added `ReentrantLock queueLock` to `ReadyQueue`.
- Protected `add()`, `poll()`, `processOf()`, and `snapshot()`.
- Used `try/finally` to release the lock safely.
- Committed and pushed the feature separately.

**Challenges**: Identifying the shared queue operations that required protection.

**Solution**: Used mutual exclusion around accesses to the shared queue and process map.

**Time spent**: Part of the November 17 work session.

---

### Entry 3 - November 17, 2026

**What I did**: Implemented Feature 2, shared statistics synchronization.

**Details**:
- Added `ReentrantLock statsLock` to `SharedStats`.
- Protected the context-switch counter, completed-process counter, and total service-time counter.
- Protected the corresponding getter methods.
- Committed and pushed the statistics synchronization separately.

**Challenges**: Preventing lost updates when multiple CPU threads modify statistics concurrently.

**Solution**: Used one shared lock for the statistics operations so updates could not overlap.

**Time spent**: Part of the November 17 work session.

---

### Entry 4 - November 17, 2026

**What I did**: Implemented Feature 3, semaphore-based CPU coordination.

**Details**:
- Imported `Semaphore` and initialized `availableProcesses` to zero.
- Added `waitForProcess()` to block CPU workers until work becomes available.
- Released a semaphore permit whenever a process was added to the queue.
- Added `wakeUpCPUs()` to allow waiting CPU workers to terminate after completion.
- Created commit `5f5e69a` with the message `Feature 3: Replace busy waiting with Semaphore`.

**Challenges**: Replacing repeated queue polling without leaving CPU threads blocked permanently.

**Solution**: Used semaphore permits to signal available processes and additional permits to wake waiting CPUs during shutdown.

**Time spent**: Part of the November 17 work session.

---

### Entry 5 - November 17, 2026

**What I did**: Verified the final implementation and pushed the completed feature to GitHub.

**Details**:
- Tested the scheduler using four CPUs and thirteen processes.
- Observed earlier runs with inconsistent statistics.
- Obtained five consecutive successful verification runs.
- Confirmed that all expected statistics matched the observed results.
- Verified that busy-waiting polls were zero.
- Pushed Feature 3 to the `main` branch of my GitHub repository.

**Challenges**: Some earlier executions produced inconsistent results, making repeated verification necessary.

**Solution**: Checked the verification block after each run and continued testing until five consecutive runs passed.

**Time spent**: Part of the November 17 work session.

---

## Development Log Summary

**Total time spent on assignment**: One work session on November 17, 2026; exact duration not recorded.

**Most challenging part**: Replacing busy waiting with semaphore-based coordination while ensuring CPU workers terminate correctly.

**Most interesting learning**: Understanding the difference between using mutex locks to protect shared data and using semaphores to coordinate thread execution.

**What I would do differently next time**: Start the assignment earlier, document each work session immediately, and spread development and commits across multiple days.

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

> 💡 **TIP:** Talk about race conditions (read-modify-write), critical sections, mutual exclusion with `ReentrantLock` and `try/finally`, the role of a counting semaphore, and what surprised you when the starter failed.

**Your Answer:** *(5-7 sentences)*

I learned that synchronization is important when multiple threads access the same data at the same time. Without proper synchronization, race conditions can cause incorrect results even when the program runs without errors. In this assignment, I used ReentrantLock to protect the ready queue and shared statistics from concurrent access. I also learned why try/finally is important, since it ensures the lock gets released after the operation. Using a counting semaphore taught me how threads can wait for available work instead of continuously checking an empty queue. The biggest lesson was that concurrent programs need repeated testing because their results can change depending on thread execution timing.


## Question 2: What was the most challenging part of this assignment?

> 💡 **TIP:** Pick **one** specific challenge (understanding why the starter failed, choosing the lock granularity, the initial value of the semaphore, the shutdown of the CPUs, Git, the video) and say *why* it was hard.

**Your Answer:** *(5-7 sentences)*

The most challenging part was implementing the semaphore to replace busy waiting. I needed to understand how CPU workers would know when a process was available in the ready queue. I also had to consider what would happen if the queue became empty while other processes were still executing. Another difficulty was making sure the CPU workers could terminate after all processes were completed. This required implementing wakeUpCPUs() to release enough permits for the waiting threads. Understanding how semaphore permits work alongside the queue lock was the part that required the most attention.


## Question 3: How did you overcome the challenges you faced?

> 💡 **TIP:** Describe your method: reading the slides and the documentation, adding `System.out.println` to debug, running the program many times, re-reading the README, testing after each small change, asking for help.

**Your Answer:** *(5-7 sentences)*

I approached the assignment one feature at a time instead of modifying everything together. First, I added synchronization to the ready queue using queueLock. After that, I protected the shared statistics with statsLock before moving on to the semaphore implementation. I used VS Code to edit the program and the terminal to compile, run, and check the results. When earlier runs showed inconsistent statistics, I continued testing and checking the synchronization logic. Eventually, I achieved five consecutive successful runs where all four verification checks passed.


## Question 4: Where can synchronization concepts be applied in real-world applications?

> 💡 **TIP:** Use real applications you know (banking and money transfers, ticket or seat booking, a shared counter on a website, a print queue, a database) and connect each one to what you built here (shared data, critical section, lock or semaphore).

**Your Answer:** *(5-7 sentences)*

Synchronization is used in many real-world applications where multiple users or threads access shared resources. For example, banking systems need synchronization to prevent two transactions from incorrectly updating the same account balance. Online booking systems also use synchronization to prevent two customers from reserving the same seat simultaneously. Mutex locks can protect these shared resources by allowing only one thread to modify them at a time. Semaphores can be used in web servers to coordinate access to a limited number of resources or available tasks. These applications are similar to the scheduler in this assignment because they require safe access to shared data and proper coordination between concurrent operations.


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

**Question**: Run the **original starter** (before any fix) and paste the **verification block** of that run. Which value was wrong (expected vs observed)? Explain **step by step**, with two named threads/CPUs, how **one lost update** happens on one of the shared variables (read, `RaceWindow.pause()`, write). Why can the same bug happen on a real machine even without `RaceWindow`, and why is it hard to detect?

> ⚠️ **WARNING:** The snippet must come from **your own run** (with your student ID), not from a classmate or from this README.
>
> 💡 **TIP:** Use a small timeline: *CPU-1 reads `contextSwitchCount` = 12 → CPU-2 reads 12 → CPU-1 writes 13 → CPU-2 writes 13 → one increment is lost.* If your starter run crashed before printing numbers, run it several times (or paste the exception and the watchdog message and explain it).

**Your Answer:** *(3-5 sentences)*

The original scheduler had race conditions because multiple CPU threads could access shared variables without synchronization. For example, two CPUs could read the same value of contextSwitchCount and both attempt to increment it. If both threads read the old value before either writes the new one, one increment is lost. RaceWindow.pause() makes this problem easier to reproduce by increasing the chance of thread interleaving. The same problem can occur on real machines without an artificial delay because thread scheduling is unpredictable, making race conditions difficult to detect consistently.

Verification block of the **original starter**:
```
[Paste the verification block (or the exception/watchdog message) of the starter here]
```

Verification block of **my final version**:
```
Context switches (quanta executed):
Expected: 26 | Observed: 26 | PASS

Completed processes:
Expected: 13 | Observed: 13 | PASS

Total service time (ms):
Expected: 105290 | Observed: 105290 | PASS

Busy-waiting polls:
Expected: 0 | Observed: 0 | PASS

```

**Explanation of the timeline:**
CPU-1 reads contextSwitchCount = 12, then execution switches to CPU-2 during RaceWindow.pause(). CPU-2 also reads the value 12. CPU-1 writes 13, and CPU-2 writes 13 using its previously read value. The correct result should be 14, but the actual result is 13, meaning one increment was lost.

## Question 2: Critical Sections and Lock Granularity

**Question**: List the **critical sections** you protected (variables and methods) and the lock(s) you used. **Lock granularity:** did you use **one lock** for the three statistics or **one lock per variable**? Why, and what is the trade-off? Why is the **ready queue** protected by a **different** lock than the statistics? Explain how your solution provides **mutual exclusion**, and discuss **progress** and **bounded waiting** (a default `ReentrantLock` is not fair: what does that imply?).

> 💡 **TIP:** The three counters are independent: does updating `contextSwitchCount` need to block an update of `totalServiceTime`? Also think about what could go wrong (deadlock, or long waiting) if the queue lock and the statistics lock were the **same** lock and a thread held it while doing something slow.

**Your Answer:** *(3-5 sentences)*

I protected the shared ready queue using queueLock and the shared statistics using statsLock. I chose one lock for all three statistics counters because it simplifies synchronization, although it can reduce concurrency when threads update independent counters. The queue has a separate lock because queue operations and statistics updates do not need to block each other. Both locks provide mutual exclusion, and keeping critical sections short helps threads make progress. However, the default ReentrantLock is nonfair, meaning bounded waiting is not guaranteed because some threads may repeatedly acquire the lock before others.

| Critical section (variable / method) | Lock used | Why it needs protection |
|ReadyQueue.processOf()|queueLock|Protects access to the shared process map|
| ReadyQueue.add() | queueLock | reasPrevents simultaneous queue modificationson |
| ReadyQueue.poll() | queueLock | Prevents multiple CPUs from removing the same queue entry |
|ReadyQueue.snapshot()|queueLock|Prevents inconsistent queue snapshots|
|SharedStats.incrementContextSwitch()|statsLock|Prevents lost increments|
|SharedStats.incrementCompletedProcess()|statsLock|Protects the completed-process counter|
|SharedStats.addServiceTime()|statsLock|Prevents lost updates to service time|
|Statistics getter methods|statsLock|Ensures synchronized access to counter values|

## Question 3: Busy Waiting vs Semaphore

**Question**: Describe the **busy waiting** of the starter and its cost (give the `Busy-waiting polls` number from your **starter** run). What does the **value of your semaphore** represent? What is its **initial value** and why? What is its value right after the `numProcesses` initial `add()` calls? Why does the last CPU call `release(totalCPUs)` at the end, and what would happen if it did not?

> 💡 **TIP:** Think about what a CPU does when the queue is empty in the starter, and what a CPU does in your final version (is it running, ready or blocked?). Also check what happens to a CPU blocked in `acquire()` when no process will ever be added again.

**Your Answer:** *(3-5 sentences)*

In the original scheduler, CPU workers repeatedly checked the ready queue when it was empty, wasting CPU time through busy waiting; the exact starter poll count was not preserved. I replaced this behavior with availableProcesses, a counting semaphore initialized to zero because no processes have been added initially. After the thirteen initial add() calls, the semaphore would contain thirteen permits before any CPU acquires one. CPU workers use acquire() to block until work becomes available instead of continuously polling the queue. When all processes finish, wakeUpCPUs() releases four permits so waiting CPU workers can wake up and terminate instead of remaining blocked indefinitely.

## Question 4: Classical Problems and Deadlock

**Question**: The CPUs and the ready queue look like a classical synchronization problem of Chapter 5. **Name it**, and say who plays the **producer** and the **consumer** roles (careful: here the CPUs also re-enqueue processes). If the ready queue were **bounded** (capacity `K`), name the **three semaphores** you would need and their **initial values**. Describe a **deadlock scenario** that appears if a thread acquired the **mutex before** waiting on the semaphore (or if two locks were acquired in different orders), and say **which of the four necessary conditions** you would break to prevent it.

> 💡 **TIP:** Recall the bounded-buffer solution of the slides (`empty`, `full`, `mutex`) and the order of `wait()` calls in the producer and the consumer. For the deadlock, think about a producer that holds the mutex while waiting for a free slot that only a consumer (who needs the mutex) can create.

**Your Answer:** *(3-5 sentences)*

**Classical problem and roles**:
Producer-consumer (bounded-buffer) problem.

Producer: Initial scheduler setup and CPU workers re-enqueuing unfinished processes.

Consumer: CPU workers removing processes from the ready queue.

**Semaphores for a bounded queue (name and initial value)**:
|Semaphore|Initial value|Purpose|
|empty|K|Counts available queue slots|
|full|0|Counts queued processes|
|mutex|1|Provides mutual exclusion for queue operations|

**Deadlock scenario and prevention**:
A producer acquires mutex and then waits on empty because the queue is full. A consumer cannot remove a process to free space because it is blocked waiting for the same mutex. This creates circular waiting. To prevent it, threads must acquire the counting semaphore before acquiring the mutex, breaking the circular-wait condition.

## Summary

**Key concepts I understood through these questions:**
1.Mutex locks protect critical sections and prevent race conditions.
2.Counting semaphores allow threads to wait efficiently for available work.
3.Correct synchronization requires careful lock ordering to prevent deadlock.

**Concepts I need to study more:**
1.Fairness and bounded waiting in multithreaded programs.
2.Synchronization strategies for bounded queues.

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
