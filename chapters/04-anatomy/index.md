---
layout: default
title: "Chapter 4: The Anatomy of Every Induction Proof"
---

[← Back to Table of Contents]({{ site.baseurl }}/) | [← Chapter 3]({{ site.baseurl }}/chapters/03-your-first-proof/)

# Chapter 4: The Anatomy of Every Induction Proof

---

*Feynman here. We've knocked over dominoes. We've done a full proof. Now let's step back and see the MACHINE.*

---

## The Moment You've Been Waiting For

Alright. You've now seen an induction proof done from scratch in Chapter 3. You watched every step. You saw the algebra. You felt the rhythm.

But here's what I want you to realize: **every induction proof you will ever see in your entire life has the exact same skeleton.** Every. Single. One.

Different formulas, different numbers, different contexts — but the bones? Identical.

And once you see the bones, once you can look at ANY induction proof and immediately spot the three parts, you become dangerous. In the best way.

So let's dissect this thing.

---

## The Template

Here it is. The universal induction proof template. Tattoo it on your brain:

```
╔══════════════════════════════════════════════════════╗
║           THE INDUCTION PROOF TEMPLATE               ║
╠══════════════════════════════════════════════════════╣
║                                                      ║
║  THEOREM: [Statement P(n) is true for all n ≥ ?]     ║
║                                                      ║
║  PROOF (by induction):                               ║
║                                                      ║
║  STEP 1 — BASE CASE:                                ║
║    Show P(first value) is true.                      ║
║    (Knock over the first domino.)                    ║
║                                                      ║
║  STEP 2 — INDUCTIVE HYPOTHESIS:                     ║
║    Assume P(k) is true for some arbitrary k.         ║
║    (Assume domino k has fallen.)                     ║
║                                                      ║
║  STEP 3 — INDUCTIVE STEP:                           ║
║    Using the assumption in Step 2,                   ║
║    prove that P(k+1) must also be true.              ║
║    (Show that domino k+1 falls.)                     ║
║                                                      ║
║  CONCLUSION:                                         ║
║    By induction, P(n) is true for all n ≥ first.     ║
║    (All dominoes fall.)                              ║
║                                                      ║
╚══════════════════════════════════════════════════════╝
```

That's it. That's the machine. Let's take it apart, piece by piece.

---

## Part 1: The Base Case (a.k.a. "Flick the First Domino")

This is the easy part. Almost always the easy part. You just plug in the first value and check that the statement works.

Usually the first value is n = 0 or n = 1. The problem will tell you.

Here's what the base case looked like in our Chapter 3 proof:

> **Statement:** 1 + 3 + 5 + ... + (2n−1) = n²
>
> **Base case (n = 1):** Is it true that 1 = 1²? Yes. 1 = 1. ✓

That's all. Plug in, check, done.

Now, some people wonder: "Why do we even bother? It's so simple!"

Remember the dominoes. If you don't flick the first one, nothing happens. You can have a million dominoes perfectly lined up, but if nobody pushes the first one — they all just stand there. The base case is the *match that lights the fuse*.

Without it, the inductive step is just a description of a chain reaction that never starts.

---

## Part 2: The Inductive Hypothesis (a.k.a. "The Magic Words")

This is the part that was **missing** from your original homework problem. This is step [2] — the blank line. And there's a reason it matters so much.

The inductive hypothesis is where you say:

> **"Assume the statement is true for some value k."**

Or, more precisely, you write down what P(k) looks like. You take the original statement and replace n with k.

For our Chapter 3 proof, P(n) was: 1 + 3 + 5 + ... + (2n−1) = n²

So P(k) is: **1 + 3 + 5 + ... + (2k−1) = k²**

And the inductive hypothesis says: **"Assume this is true."**

Now, here's why this step is so important, even though it looks like you're "just writing something down":

**The inductive hypothesis is the tool you use in Step 3.**

It's like picking up a wrench before you loosen a bolt. You don't just stare at the bolt — you need the wrench. The hypothesis IS the wrench. In Step 3, there will be a moment where you're stuck, where the algebra doesn't simplify... and then you reach for the hypothesis, substitute it in, and everything clicks.

If you don't state the hypothesis, Step 3 has no justification. It's like pulling a rabbit out of a hat without the hat.

Let me say that differently because it's crucial:

> **The inductive hypothesis isn't decoration. It's the engine of Step 3. Without it, Step 3 is just hand-waving.**

---

## Part 3: The Inductive Step (a.k.a. "The Heavy Lifting")

This is where the work happens. This is the part that actually requires you to think.

The mission is simple to state:

> **Start with P(k+1) — the "next case" — and show it must be true, USING the fact that you assumed P(k) is true.**

In practice, this almost always goes like this:

1. Write down what P(k+1) looks like. (What does the formula say when n = k+1?)
2. Rearrange or manipulate the left side.
3. At some point, you'll see a chunk that looks exactly like P(k) — the thing you assumed was true!
4. Substitute in the hypothesis. Replace that chunk with what it equals.
5. Simplify. Arrive at what P(k+1) should equal.
6. Celebrate.

That moment in step 3 — where you spot P(k) hiding inside P(k+1) — that's the magic moment. That's the "aha!" That's where you use your wrench.

---

## Let's See The Skeleton in Action

Let me put two proofs side by side so you can see how the skeleton is IDENTICAL even though the formulas are completely different:

### Proof A (from Chapter 3): Sum of Odd Numbers

| Part | What It Looks Like |
|---|---|
| **Statement** | 1 + 3 + 5 + ... + (2n−1) = n² |
| **Base case** | n = 1: Is 1 = 1²? Yes. ✓ |
| **Hypothesis** | Assume 1 + 3 + ... + (2k−1) = k² |
| **Inductive step** | Show 1 + 3 + ... + (2k−1) + (2(k+1)−1) = (k+1)² |
| **Key move** | Replace the first chunk with k² (hypothesis!), get k² + 2k + 1 = (k+1)² ✓ |

### Proof B (preview): Sum of First n Integers

**Before you look at the table below, try this.** You know the statement is: 1 + 2 + 3 + ... + n = n(n+1)/2. Using what you learned from Proof A, can you fill in these blanks?

- Base case: what value of n do you check, and does it work?
- Hypothesis: what would you assume? (Remember: take P(n) and replace n with k.)
- Key move: what would you substitute in?

Really try this one — don't just glance at the blanks and scroll. You have everything you need from Proof A. The pattern is the same; only the formula changes. Write your answers down, then scroll to check.

...

...

...

...

...

| Part | What It Looks Like |
|---|---|
| **Statement** | 1 + 2 + 3 + ... + n = n(n+1)/2 |
| **Base case** | n = 1: Is 1 = 1(2)/2 = 1? Yes. ✓ |
| **Hypothesis** | Assume 1 + 2 + ... + k = k(k+1)/2 |
| **Inductive step** | Show 1 + 2 + ... + k + (k+1) = (k+1)(k+2)/2 |
| **Key move** | Replace the first chunk with k(k+1)/2 (hypothesis!), simplify to (k+1)(k+2)/2 ✓ |

How did you do? If you got the hypothesis right — "assume the sum up to k equals k(k+1)/2" — then you've internalized the pattern. If not, no worries. That's exactly what practice is for.

See it? **Same skeleton.** The formulas change, but the dance is identical:

1. Base case — plug in, check. ✓
2. Hypothesis — write down P(k), assume it.
3. Inductive step — write P(k+1), spot P(k) hiding inside, substitute, simplify.

---

## The "Spotting P(k)" Trick

I want to dwell on this because it's the single most useful skill in doing induction proofs.

When you write out P(k+1) — the "next case" — it almost always contains P(k) as a piece of itself. Here's why:

P(k+1) is usually P(k) **plus one more term**.

Think about it:

- The sum of the first **k+1** odd numbers = the sum of the first **k** odd numbers + **one more odd number**
- The sum of the first **k+1** integers = the sum of the first **k** integers + **one more integer**
- The sum of powers of 2 up to **2^(k+1)** = the sum up to **2^k** + **one more power of 2**

It's always: **[old stuff] + [new term]**

And [old stuff] is exactly P(k) — the thing you assumed was true!

So you replace [old stuff] with what the hypothesis says it equals, add the new term, and simplify.

That's the move. Every time.

---

## A Checklist You Can Actually Use

Next time you sit down to write an induction proof, here's your checklist. Print it out. Tape it to your wall. I don't care.

```
□ Step 0: Identify what P(n) is.
           (What's the statement you're trying to prove?)

□ Step 1: BASE CASE
           Plug in the first value. Does it work?
           If yes: write "Base case verified" and check the box.

□ Step 2: INDUCTIVE HYPOTHESIS  ← DON'T SKIP THIS
           Write: "Assume P(k) is true for some integer k ≥ [first value]"
           Write out what P(k) actually says (the formula with k).

□ Step 3: INDUCTIVE STEP
           a. Write out what P(k+1) should look like.
           b. Start with the left side of P(k+1).
           c. Spot P(k) hiding inside.
           d. Replace it using the hypothesis.
           e. Simplify until you reach the right side of P(k+1).

□ Step 4: CONCLUSION
           Write: "By mathematical induction, P(n) is true for all n ≥ [first value]."
           Drop the mic.  □
```

---

## Why Step 2 Gets Skipped (And Why That's a Problem)

You know what? Let me tell you why your homework proof has a blank at step [2].

Because the inductive hypothesis *feels* redundant. You look at it and think: "I'm just rewriting the theorem with k instead of n. Why bother?"

And honestly? From a *mechanical* standpoint, you could argue you don't need to write it down — you use it implicitly in Step 3 anyway.

But here's the thing: **writing it down is what makes the proof VALID.** It's like a lawyer saying "Your Honor, I'd like to enter this into evidence." You can't just use evidence in your argument without formally presenting it. The hypothesis is your evidence. Step 3 is your argument. You need to formally state the evidence before you use it.

Skipping Step 2 is like a lawyer saying "the defendant is guilty because of... well, you know... that thing." What thing? STATE IT.

In formal mathematics, an induction proof with a missing hypothesis is **incomplete**. It might be clear what the hypothesis *would* be, but it hasn't been stated. And in math, unstated = unproven = not valid.

That's why your problem specifically calls attention to it. That's why step [2] is blank. They WANT you to notice the gap.

---

## What to Take Away from This Chapter

**1. Every induction proof has the same three parts.** Base case, inductive hypothesis, inductive step. Always. Forever. No exceptions.

**2. The inductive hypothesis is not decoration.** It's the tool you use to make Step 3 work. It's the wrench. Don't skip it.

**3. The key move in Step 3 is always the same:** Spot P(k) hiding inside P(k+1), then substitute using the hypothesis.

**4. You now have a reusable template.** Any induction proof you'll ever write fits the same skeleton. Fill in the blanks, follow the checklist, and you'll get there.

---

[Next: Chapter 5 — Practice Round — A Second Proof →]({{ site.baseurl }}/chapters/05-practice-round/)
