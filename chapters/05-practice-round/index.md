---
layout: default
title: "Chapter 5: Practice Round — A Second Proof"
---

[← Back to Table of Contents]({{ site.baseurl }}/) | [← Chapter 4]({{ site.baseurl }}/chapters/04-anatomy/)

# Chapter 5: Practice Round — A Second Proof

---

*Feynman again. The training wheels are loosening. You can feel it. Good.*

---

## Why We're Doing This Again

You might be thinking: "Feynman, I already did a proof in Chapter 3. Why are we doing another one?"

Because of something every musician, every athlete, every craftsperson knows: **you don't learn a skill by doing it once.** You learn it by doing it twice, noticing the pattern, and realizing "oh — it's the SAME thing."

A pianist doesn't play one scale and say "I understand scales now." They play C major, then G major, then D major, and at some point their fingers realize: "Ah. It's the same *shape*. Just shifted."

That's what we're doing here. Same shape. Different notes.

---

## The Theorem

Here's what we're going to prove:

> **Theorem:** For all positive integers n, 1 + 2 + 3 + ... + n = n(n+1)/2

This is the formula for the sum of the first n positive integers. It's one of the most famous formulas in all of mathematics. Legend has it that Gauss — as a schoolboy — figured this out to annoy his teacher. (Gauss was that kind of kid.)

Let's verify it makes sense before we prove anything:

```
n = 1:   1                   = 1(2)/2   = 1     ✓
n = 2:   1 + 2               = 2(3)/2   = 3     ✓
n = 3:   1 + 2 + 3           = 3(4)/2   = 6     ✓
n = 4:   1 + 2 + 3 + 4       = 4(5)/2   = 10    ✓
n = 5:   1 + 2 + 3 + 4 + 5   = 5(6)/2   = 15    ✓
```

Looks true. But we learned in Chapter 1 that "looks true" isn't good enough. So let's PROVE it.

And this time, I'm going to use the template from Chapter 4. You should have that checklist in your head by now. Let's fill it in.

---

## Step 0: Identify P(n)

What's the statement we're proving?

> **P(n):** 1 + 2 + 3 + ... + n = n(n+1)/2

Good. Now we know what P(n) is. Everything else flows from this.

---

## Step 1: Base Case

We need to check: is P(1) true?

P(1) says: 1 = 1(1+1)/2

Let's compute the right side:

```
1(1+1)/2 = 1(2)/2 = 2/2 = 1
```

Left side: 1. Right side: 1. They match.

> **Base case: verified.** ✓

First domino: flicked.

*(Easy. It's always easy. Don't overthink the base case.)*

---

## Step 2: Inductive Hypothesis

Here's where we pick up our wrench.

**But wait — this time, YOU write it.** You've done this before. You know P(n) is: 1 + 2 + 3 + ... + n = n(n+1)/2. What does the inductive hypothesis look like? What do you write down?

Take a second. Write it out — on paper, in your head, wherever.

...

...

...

Here's what you should have:

> **Assume P(k) is true for some positive integer k.**

What does P(k) say? We take P(n) and replace every n with k:

> **Assume: 1 + 2 + 3 + ... + k = k(k+1)/2**

Write it down. Underline it. Circle it. Draw a little star next to it. This is the thing you're going to USE in Step 3. It's your ammunition.

We're not saying this is true for all k. We're saying: "Pick a k. Any k. Assume the formula works for THAT particular k."

Domino k is down. Now let's knock over k+1.

---

## Step 3: Inductive Step

**Goal:** Show that P(k+1) is true.

**Quick challenge:** What should P(k+1) look like? You've got the formula n(n+1)/2. If you replace n with (k+1), what do you get on the right side? Work it out before peeking.

...

...

...

We need to show:

> 1 + 2 + 3 + ... + k + (k+1) = (k+1)(k+2)/2

Where did (k+1)(k+2)/2 come from? I just took the formula n(n+1)/2 and replaced n with (k+1):

```
n(n+1)/2   →   (k+1)((k+1)+1)/2   →   (k+1)(k+2)/2
```

So that's our **target**. That's what we need to arrive at. Let's start from the left side and work our way there.

---

**Left side of P(k+1):**

```
1 + 2 + 3 + ... + k + (k+1)
```

Now here's where I want you to DO THE THING. You've done this before in Chapter 3. You're looking at:

```
1 + 2 + 3 + ... + k + (k+1)
```

**You know the drill. What's the move?** Can you identify which part is P(k), what the hypothesis lets you replace it with, and what the expression becomes after the substitution? Try to write out the next line of the proof yourself before scrolling.

...

...

...

Here's what you should have seen:

```
1 + 2 + 3 + ... + k    +    (k+1)
╚═══════════════════╝        ╚════╝
    This is P(k)!           New term
```

The first part — everything up to k — is EXACTLY the left side of P(k). The thing we ASSUMED was true!

And our hypothesis told us what that equals:

> 1 + 2 + 3 + ... + k = k(k+1)/2

So we SUBSTITUTE:

```
1 + 2 + 3 + ... + k + (k+1)

= k(k+1)/2 + (k+1)          ← USED THE HYPOTHESIS! This is the key move!
```

Did you feel that? That substitution — that's the moment. That's where the wrench meets the bolt. Every time.

---

Now we just need to simplify k(k+1)/2 + (k+1) and show it equals (k+1)(k+2)/2.

This is just algebra. No more induction cleverness needed — just honest arithmetic.

**One more challenge before I show you.** You've got k(k+1)/2 + (k+1). Two terms being added, one of which is a fraction. How would you start simplifying this? (Hint: what do you do when you want to add a whole number to a fraction?)

...

...

...

**Let's get a common denominator:**

```
  k(k+1)/2 + (k+1)

= k(k+1)/2 + 2(k+1)/2       ← rewrite (k+1) as 2(k+1)/2

= [k(k+1) + 2(k+1)] / 2     ← combine the fractions
```

**Now factor out (k+1):**

```
= (k+1)[k + 2] / 2           ← factor (k+1) from both terms

= (k+1)(k+2) / 2
```

And THAT is exactly what P(k+1) says the answer should be!

> **(k+1)(k+2)/2 = (k+1)(k+2)/2** ✓

WE DID IT.

---

## Step 4: Conclusion

> By mathematical induction, 1 + 2 + 3 + ... + n = n(n+1)/2 for all positive integers n. ∎

All the dominoes fall. Every last one.

---

## Let's Replay the Key Moment in Slow Motion

I want to make sure you caught the move. Because it's the SAME move as Chapter 3. Let me replay it:

**Chapter 3 (Odd numbers):**
```
1 + 3 + 5 + ... + (2k-1) + (2k+1)
╚════════════════════════╝
     This is P(k) = k²

= k² + (2k+1)    ← hypothesis substitution
= (k+1)²         ← simplify
```

**Chapter 5 (Sum of integers):**
```
1 + 2 + 3 + ... + k + (k+1)
╚═══════════════════╝
  This is P(k) = k(k+1)/2

= k(k+1)/2 + (k+1)    ← hypothesis substitution
= (k+1)(k+2)/2        ← simplify
```

**See it?** It's the EXACT same dance:

1. Write out the P(k+1) case
2. Separate it into [P(k) stuff] + [new term]
3. Substitute the hypothesis for the P(k) stuff
4. Simplify

Different formula. Same skeleton. Same move. Same shape, different notes.

---

## The Algebra — Let's Be Honest About It

Now, I want to be straight with you about something. The induction part — the logic, the structure, the domino reasoning — that's always the same and it's not that hard once you get it.

The part that varies, and the part that can trip you up, is **the algebra in Step 3.** Getting a common denominator, factoring, expanding — that's where the messiness lives.

But here's the good news: the algebra is just algebra. It's not some special "induction algebra." It's the same simplifying and factoring you'd do anywhere. If you can add fractions and factor expressions, you can handle Step 3.

The *thinking* — the *strategy* — is always:

> "Spot P(k), substitute, simplify."

The algebra is just the cleanup crew.

---

## How This Felt vs. Chapter 3

Think back to Chapter 3. That proof probably felt like a lot of new information — new structure, new logic, new everything.

This one should have felt... *familiar*. A little easier. A little smoother.

That's because you weren't learning the structure anymore. You already knew the structure. You were just **applying** it to new content.

And that's exactly where I wanted to get you. Because in Chapter 6, we're going to apply this same structure to the proof from your homework — the powers of 2 — and you're going to be ready for it.

---

## What to Take Away

**1. Same dance, different music.** The structure of induction doesn't change from problem to problem. Only the formula changes.

**2. The key move is ALWAYS the same:** spot P(k) inside P(k+1), substitute, simplify.

**3. The algebra is just algebra.** Don't let fractions or factoring intimidate you — that's not the induction part. The induction part is the *structure*.

**4. You've now done TWO proofs.** If you can do two, you can do two hundred. It's the same skeleton every time.

---

[Next: Chapter 6 — The Powers-of-2 Proof — Your Original Problem →]({{ site.baseurl }}/chapters/06-powers-of-2/)
