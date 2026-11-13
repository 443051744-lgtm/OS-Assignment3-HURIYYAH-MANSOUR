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
| **Full Name** | HURIYYAH MANSOUR (حورية منصور) |
| **Student ID** | 443051744 |
| **University Email** | 443051744@std.psau.edu.sa |
| **GitHub Username** | 443051744-lgtm |
| **Repository Link** | https://github.com/443051744-lgtm/OS-Assignment3-HURIYYAH-MANSOUR |
 
---

## 🎥 Video Link

**Video Link**: [Add the public video link after recording]

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

### Entry 1 - [November 13, 2026, 11:21 PM - assisted preparation]
**What I did**: Prepared and tested a synchronized version of the starter with AI assistance; I still need to review the changes myself.

**Details**:
- Ran the original starter with my student ID (443051744) and recorded the race-condition results.
- Applied queue locking, three statistics locks, and a counting semaphore in the starter Java file.
- The first final run and four more runs passed all four verification checks.

**Challenges**: The original program had multiple CPU thread exceptions and a watchdog timeout.

**Solution**: Protect shared state with `ReentrantLock`, use `Semaphore(0)` for queue availability, and release shutdown permits after the last process finishes.

**Time spent**: [Record your actual review/work time]

---

### Entry 2 - [Your actual date and time]
**What I did**: [Record your own work session, e.g., checking the queue lock]

**Details**:

**Challenges**:

**Solution**:

**Time spent**:

---

### Entry 3 - [Your actual date and time]
**What I did**: [Record your own work session, e.g., testing the statistics locks]

**Details**:

**Challenges**:

**Solution**:

**Time spent**:

---

### Entry 4 - [Your actual date and time]
**What I did**: [Record your own work session, e.g., explaining the semaphore]

**Details**:

**Challenges**:

**Solution**:

**Time spent**:

---

### Entry 5 - [Your actual date and time]
**What I did**: [Record your own work session, e.g., GitHub/video review]

**Details**:

**Challenges**:

**Solution**:

**Time spent**:

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

**Total time spent on assignment**: [Add your real total time]

**Most challenging part**: Understanding how to stop the CPUs that are blocked on the semaphore after all processes finish.

**Most interesting learning**: Separate locks can prevent lost updates without blocking unrelated statistics updates.

**What I would do differently next time**: Test one synchronization feature at a time and record the output from every important run.

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

I learned that two or more CPU threads can corrupt shared data even when each thread seems to run correctly on its own. In the original scheduler, several CPUs could read the same queue head before it was removed. I also saw that the read-pause-write pattern of a counter could lose updates if no lock protected it. A `ReentrantLock` keeps the full critical section together, and the `finally` block releases the lock even if a problem occurs. I used a counting semaphore so CPUs wait for available processes instead of repeatedly checking an empty queue. The most important lesson for me is that correct concurrent code needs both safe shared-data access and a safe way to wake waiting threads.

## Question 2: What was the most challenging part of this assignment?

> 💡 **TIP:** Pick **one** specific challenge (understanding why the starter failed, choosing the lock granularity, the initial value of the semaphore, the shutdown of the CPUs, Git, the video) and say *why* it was hard.

**Your Answer:** *(5-7 sentences)*

The most challenging part was understanding how the CPUs should stop when the ready queue becomes empty. An empty queue does not always mean the program has finished, because another CPU may still be executing a quantum and will re-enqueue its process. If a worker simply exits on an empty queue, some processes might never finish. After adding the semaphore, the opposite problem appears: the workers may stay blocked forever after the last process has completed. The solution is to check the completed-process count after waking and send shutdown permits when the count reaches the total number of processes. This was harder than adding the locks because it required understanding the order of events across several threads.

## Question 3: How did you overcome the challenges you faced?

> 💡 **TIP:** Describe your method: reading the slides and the documentation, adding `System.out.println` to debug, running the program many times, re-reading the README, testing after each small change, asking for help.

**Your Answer:** *(5-7 sentences)*

I started by comparing the broken starter's output with the expected values in its verification block. My student ID produced 10 processes and 4 CPUs, so it was easy to see several threads competing for the same ready queue. I identified the shared accesses in `ReadyQueue` and `SharedStats` and protected each complete operation with `try/finally`. Next, I replaced the empty-queue polling with a semaphore that begins at zero permits. I added a shutdown signal for blocked CPUs and checked the result against all four built-in tests. The corrected program passed five runs, which gave me stronger evidence than a single successful run.

## Question 4: Where can synchronization concepts be applied in real-world applications?

> 💡 **TIP:** Use real applications you know (banking and money transfers, ticket or seat booking, a shared counter on a website, a print queue, a database) and connect each one to what you built here (shared data, critical section, lock or semaphore).

**Your Answer:** *(5-7 sentences)*

Synchronization is important whenever multiple users or workers access the same resource at the same time. In online banking, a lock can prevent two withdrawals from reading the same old account balance and both succeeding incorrectly. A ticket-booking system also needs mutual exclusion when updating the number of seats left. The ready queue in this assignment is similar to a printer queue where several workers share a list of jobs. A semaphore can let a printer worker sleep until a new job arrives instead of checking repeatedly. The same ideas help databases and web servers keep shared counters and work queues consistent under heavy use.

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

With student ID 443051744, the original starter crashed with `IllegalThreadStateException` on CPU-1, CPU-2, and CPU-3, and the watchdog reported that the simulation did not finish. Its context-switch count was 16 instead of 25 (9 short), its completed-process count was 7 instead of 10 (3 short), and its total service time was 62,954 ms instead of 95,672 ms (32,718 ms short). There were also 828 busy-wait polls rather than zero. These failures came from unprotected shared queue access and counter updates; on real CPUs, a context switch can interrupt a read-modify-write sequence even without the artificial `RaceWindow.pause()`. The timing changes between runs, so the same bug may appear randomly and be difficult to reproduce.

Verification block of the **original starter**:
```
Exception in thread "CPU-1" java.lang.IllegalThreadStateException
Exception in thread "CPU-3" java.lang.IllegalThreadStateException
Exception in thread "CPU-2" java.lang.IllegalThreadStateException
WATCHDOG: the simulation did not finish (29 s).
Context switches (quanta executed)     expected 25       observed 16       MISMATCH
Completed processes                    expected 10       observed 7        MISMATCH
Total service time (ms)                expected 95672    observed 62954    MISMATCH
Busy-waiting polls (must be 0)         expected 0        observed 828      MISMATCH
```

Verification block of **my final version**:
```
Context switches (quanta executed)     expected 25       observed 25       ✔
Completed processes                    expected 10       observed 10       ✔
Total service time (ms)                expected 95672    observed 95672    ✔
Busy-waiting polls (must be 0)         expected 0        observed 0        ✔
✔ All shared values are consistent.
```

**Explanation of the timeline:**
For example, CPU-1 and CPU-2 can each enter `incrementContextSwitch()` and read `contextSwitchCount = 8` before either writes a new value. During `RaceWindow.pause()`, both keep the same temporary value, then each writes 9, even though two quanta started and the correct count should be 10. The context-switch lock prevents the second read until the first update is finished.

## Question 2: Critical Sections and Lock Granularity

**Question**: List the **critical sections** you protected (variables and methods) and the lock(s) you used. **Lock granularity:** did you use **one lock** for the three statistics or **one lock per variable**? Why, and what is the trade-off? Why is the **ready queue** protected by a **different** lock than the statistics? Explain how your solution provides **mutual exclusion**, and discuss **progress** and **bounded waiting** (a default `ReentrantLock` is not fair: what does that imply?).

> 💡 **TIP:** The three counters are independent: does updating `contextSwitchCount` need to block an update of `totalServiceTime`? Also think about what could go wrong (deadlock, or long waiting) if the queue lock and the statistics lock were the **same** lock and a thread held it while doing something slow.

**Your Answer:** *(3-5 sentences)*

I protected every access to the shared `list` and `map` in `ReadyQueue` with `queueLock`, including `add()`, `poll()`, `processOf()`, and `snapshot()`. I used three separate locks for the independent statistics (`contextSwitchLock`, `completedProcessLock`, and `serviceTimeLock`) so unrelated counters can be updated at the same time; the trade-off is extra locks and more code. Keeping `queueLock` separate from the statistics locks avoids unnecessary interference between queue operations and counter updates. Each lock provides mutual exclusion, while the short critical sections and releasing locks in `finally` support progress. Default `ReentrantLock` is not fair, so it cannot strictly guarantee bounded waiting because a thread may be overtaken repeatedly.

| Critical section (variable / method) | Lock used | Why it needs protection |
|---|---|---|
| `ReadyQueue.add()`, `poll()`, `processOf()`, `snapshot()` (`list` and `map`) | `queueLock` | Prevent duplicate removals, lost queue entries, and unsafe iteration. |
| `incrementContextSwitch()`, `getContextSwitchCount()` | `contextSwitchLock` | Prevent lost increments and protect reads of the count. |
| `incrementCompletedProcess()`, `getCompletedProcessCount()` | `completedProcessLock` | Prevent lost completions and protect shutdown checks. |
| `addServiceTime()`, `getTotalServiceTime()` | `serviceTimeLock` | Preserve the sum of executed quantum times and safe reads. |

## Question 3: Busy Waiting vs Semaphore

**Question**: Describe the **busy waiting** of the starter and its cost (give the `Busy-waiting polls` number from your **starter** run). What does the **value of your semaphore** represent? What is its **initial value** and why? What is its value right after the `numProcesses` initial `add()` calls? Why does the last CPU call `release(totalCPUs)` at the end, and what would happen if it did not?

> 💡 **TIP:** Think about what a CPU does when the queue is empty in the starter, and what a CPU does in your final version (is it running, ready or blocked?). Also check what happens to a CPU blocked in `acquire()` when no process will ever be added again.

**Your Answer:** *(3-5 sentences)*

In the original scheduler, a CPU finding an empty queue repeatedly slept for 20 ms and checked again, causing 828 busy-waiting polls in my starter run. The `readyCount` semaphore starts at 0 because the queue initially contains no processes, and each `add()` releases one permit for an available process. After the 10 initial processes are added (before any CPU starts), the semaphore has 10 permits; an idle CPU then blocks in `acquire()` until a permit appears. When the final process finishes, the worker releases `totalCPUs` (4) shutdown permits so waiting workers wake up, notice that all 10 processes completed, and exit instead of hanging.

## Question 4: Classical Problems and Deadlock

**Question**: The CPUs and the ready queue look like a classical synchronization problem of Chapter 5. **Name it**, and say who plays the **producer** and the **consumer** roles (careful: here the CPUs also re-enqueue processes). If the ready queue were **bounded** (capacity `K`), name the **three semaphores** you would need and their **initial values**. Describe a **deadlock scenario** that appears if a thread acquired the **mutex before** waiting on the semaphore (or if two locks were acquired in different orders), and say **which of the four necessary conditions** you would break to prevent it.

> 💡 **TIP:** Recall the bounded-buffer solution of the slides (`empty`, `full`, `mutex`) and the order of `wait()` calls in the producer and the consumer. For the deadlock, think about a producer that holds the mutex while waiting for a free slot that only a consumer (who needs the mutex) can create.

**Your Answer:** *(3-5 sentences)*

This is a producer-consumer problem: the main thread initially produces processes, while CPU workers consume queue entries and also act as producers when they re-enqueue unfinished processes. If the queue had a maximum capacity `K`, the classical bounded-buffer solution would use `empty = K`, `full = 0`, and `mutex = 1` as semaphore initial values. A producer that acquires `mutex` first and then waits for `empty` when the buffer is full can deadlock with a consumer that needs the same mutex to remove an item and free space. Acquiring `empty` before `mutex` avoids holding the mutex while waiting and breaks the hold-and-wait condition in that scenario.

**Classical problem and roles**:
Bounded-buffer / producer-consumer. The main thread and re-enqueuing CPUs produce ready-queue entries; CPUs consume them when they run a quantum.

**Semaphores for a bounded queue (name and initial value)**:
`empty = K` (free slots), `full = 0` (available items), `mutex = 1` (mutual exclusion).

**Deadlock scenario and prevention**:
If a producer holds `mutex` while waiting on `empty` in a full queue, the consumer cannot lock the queue to create a free slot. Wait for an available `empty` slot before taking `mutex`, breaking hold-and-wait.

## Summary

**Key concepts I understood through these questions:**
1. A read-modify-write update is not atomic without synchronization.
2. Critical sections need consistent locking for both reading and writing.
3. Semaphores avoid polling and can support a clean worker shutdown.

**Concepts I need to study more:**
1. Fair locks and formal bounded-waiting guarantees.
2. Semaphore coordination for bounded queues under high load.

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
