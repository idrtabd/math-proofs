---
layout: default
title: "Chapter 3: Your First Induction Proof"
---

[← Back to Table of Contents]({{ site.baseurl }}/) | [← Chapter 2]({{ site.baseurl }}/chapters/02-the-domino-principle/)

# Chapter 3: Your First Induction Proof — With Training Wheels

---

*Feynman here. Sleeves rolled up. Chalk in hand. Let's do this.*

---

## What We're Proving

Remember our friend from Chapter 1? The beautiful pattern?

> **Claim:** The sum of the first n odd numbers equals n².

Written with symbols:

> 1 + 3 + 5 + ... + (2n − 1) = n²

Now, before we dive in, let me decode that "(2n − 1)" for you, because it looks scary and it's not.

The odd numbers are: 1, 3, 5, 7, 9, 11, ...

What's the pattern? Each one is 2 more than the last. And there's a neat formula: the *n*-th odd number is (2n − 1). Let's check:

```
n = 1:   2(1) − 1 = 1     ← first odd number ✓
n = 2:   2(2) − 1 = 3     ← second odd number ✓
n = 3:   2(3) − 1 = 5     ← third odd number ✓
n = 4:   2(4) − 1 = 7     ← fourth odd number ✓
```

See? It's just a machine that spits out odd numbers. Put in which one you want, get the odd number out. Nothing mysterious.

So "1 + 3 + 5 + ... + (2n − 1)" just means "add up the first n odd numbers."

And we claim that always equals n².

OK. Now let's PROVE it. For real. With induction.

---

## Step 1: The Base Case (Knock Over the First Domino)

We need to show the formula works for the very first case. The smallest value. n = 1.

**The left side** (what we're adding up):

> The first 1 odd number is just... 1.

**The right side** (what the formula predicts):

> n² = 1² = 1

**Do they match?**

> 1 = 1 ✓

Yes! That's it! The base case is done!

I know what you're thinking: "That was too easy." And you're right, base cases are almost always easy. They're the gimme. The freebie. The first domino is usually already tipping over by the time you look at it.

The real work is coming. Here it comes.

---

## Step 2: The Inductive Hypothesis (The Assumption)

Now we set up our assumption. Remember from Chapter 2 — this is NOT cheating. We're saying:

> **"Suppose — just suppose — that the formula works for some particular number k."**

Written out, that means we're ASSUMING:

> 1 + 3 + 5 + ... + (2k − 1) = k²

Let me be really clear about what we're doing here. We're picking some number k. We don't know what it is. Could be 7. Could be 50. Could be a million. Doesn't matter. We're saying: "For this particular k, the formula holds."

This is our tool. We're going to pick it up and USE it in the next step.

I want to give this assumption a nickname so we can refer to it. Let's call it **"The Assumption."** Creative, I know.

> **The Assumption:** 1 + 3 + 5 + ... + (2k − 1) = k²

Tattoo it on your brain. We're about to need it.

---

## Step 3: The Inductive Step (If Domino k Falls, Prove k+1 Falls)

HERE is where the magic happens. This is the engine room. This is where you earn your stripes.

**Our goal:** Show that the formula also works for k + 1.

In other words, we need to show:

> 1 + 3 + 5 + ... + (2k − 1) + (2(k+1) − 1) = (k + 1)²

Let me simplify that last odd number real quick:

> 2(k + 1) − 1 = 2k + 2 − 1 = 2k + 1

So our goal is to show:

> 1 + 3 + 5 + ... + (2k − 1) + (2k + 1) = (k + 1)²

Look at the left side of that equation. Look at it carefully. Do you see something familiar?

```
1 + 3 + 5 + ... + (2k − 1)  +  (2k + 1)
╰─────────────────────────╯     ╰───────╯
    this part we KNOW!           this is just
    it equals k²!               the next odd
    (The Assumption!)            number
```

THIS is the moment. This is where The Assumption earns its keep.

We ASSUMED that 1 + 3 + 5 + ... + (2k − 1) = k². So we can REPLACE that whole chunk with k².

Watch:

```
  1 + 3 + 5 + ... + (2k − 1) + (2k + 1)

= k² + (2k + 1)                            ← Used The Assumption!

= k² + 2k + 1                              ← Just removed parentheses

= (k + 1)²                                 ← Factored! This is just (k+1)(k+1)!
```

**THAT'S IT. WE'RE DONE.**

We wanted to show the left side equals (k + 1)². And it does.

---

## Wait, Let Me Make Sure You Saw What Just Happened

That went by fast, so let me replay it in slow motion.

**What we wanted:** To show the formula works for k + 1 (the next domino).

**What we did:**

1. We wrote out what "the formula works for k + 1" actually looks like.

2. We noticed that the left side *contains* the sum for k — it's just the sum for k, plus one more number (the next odd number, 2k + 1).

3. We used The Assumption to replace the sum-for-k with k².

4. We did a tiny bit of algebra: k² + 2k + 1 = (k + 1)².

5. And — boom — we arrived exactly where we needed to be.

**The domino falls.**

---

## Let Me Show You Why Step 3 Is So Satisfying

Here's what's so gorgeous about this. Let me lay it all out:

```
THE BASE CASE SAID:     It works for n = 1.        (domino 1 falls)

THE INDUCTIVE STEP SAID: If it works for k,         (if domino k falls...)
                         then it works for k + 1.   (...then domino k+1 falls)
```

So now chain them together:

```
It works for n = 1.                        (base case)
Since it works for 1, it works for 2.      (inductive step, with k = 1)
Since it works for 2, it works for 3.      (inductive step, with k = 2)
Since it works for 3, it works for 4.      (inductive step, with k = 3)
Since it works for 4, it works for 5.      (inductive step, with k = 4)
...
...forever.
```

**Every domino falls. The formula is true for ALL n. We're done. Q.E.D.**

(That's Latin for "I told you so." Well, roughly.)

---

## The Whole Proof, Clean and Pretty

Now let me write the whole thing the way you'd see it in a textbook — but after what we just did, it should feel like reading a story you already know:

---

**Theorem:** For all positive integers n, 1 + 3 + 5 + ... + (2n − 1) = n².

**Proof (by induction on n):**

**Base case (n = 1):**
The left side is 1. The right side is 1² = 1. They are equal. ✓

**Inductive hypothesis:**
Assume that for some positive integer k, the formula holds:
1 + 3 + 5 + ... + (2k − 1) = k²

**Inductive step:**
We must show: 1 + 3 + 5 + ... + (2k − 1) + (2k + 1) = (k + 1)²

Starting from the left side:

```
  1 + 3 + 5 + ... + (2k − 1) + (2k + 1)
= k² + (2k + 1)                           [by the inductive hypothesis]
= k² + 2k + 1
= (k + 1)²                                ✓
```

Since the base case holds and the inductive step holds, by the principle of mathematical induction, the formula is true for all positive integers n. ∎

---

## What I Want You to Notice

Look at that clean proof above. It's short! Like, really short. A few lines. And yet it proves something is true for EVERY positive integer. Every one. Up to infinity and beyond.

And here's what I *really* want you to notice: **the inductive hypothesis showed up right in the middle of the work.** See it? That line that says "[by the inductive hypothesis]"? That's where we used The Assumption. That's where domino k knocked over domino k + 1.

Without that assumption, we'd be stuck. We'd have this big sum on the left side — 1 + 3 + 5 + ... + (2k − 1) + (2k + 1) — and no way to simplify it. The assumption is what lets us collapse most of it into k² and then do the easy algebra.

**The assumption is the tool. The inductive step is where you use it.**

---

## The Key Move (Burn This Into Your Brain)

In almost every induction proof, the key move is the same:

> **The sum up to k + 1  =  (the sum up to k) + (the new term)**

And since you ASSUMED you know what "the sum up to k" is, you just... substitute it in.

That's the trick. That's always the trick. You take the big scary sum for k + 1, you split off the last piece, and you use your assumption to handle everything else.

It's like being handed a 1,000-piece jigsaw puzzle, but 999 pieces are already assembled (that's your assumption), and you just have to figure out where the last piece goes.

---

## Quick Self-Check

Before you move on, make sure you can answer:

**Q: Where exactly did we use the inductive hypothesis in the proof?**

A: When we replaced "1 + 3 + 5 + ... + (2k − 1)" with k². That substitution IS the hypothesis being used.

**Q: Why couldn't we do the proof without the hypothesis?**

A: Because without it, we'd have no way to simplify the sum. We'd just be staring at "1 + 3 + 5 + ... + stuff" with no way to evaluate it.

**Q: What was the algebra trick at the end?**

A: Recognizing that k² + 2k + 1 = (k + 1)². This is just the expansion of (k + 1)(k + 1) = k² + k + k + 1 = k² + 2k + 1, run in reverse.

---

*You just did your first induction proof. How does it feel?*

*Next time, in Chapter 4: We extract the template — the skeleton that EVERY induction proof follows. Once you have it, they all look the same.*

---

[Next: Chapter 4 — The Anatomy of Every Induction Proof →]({{ site.baseurl }}/chapters/04-the-anatomy/) *(coming soon)*
