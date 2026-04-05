---
layout: default
title: "Chapter 6: The Powers-of-2 Proof — Your Original Problem"
---

[← Back to Table of Contents]({{ site.baseurl }}/) | [← Chapter 5]({{ site.baseurl }}/chapters/05-practice-round/)

# Chapter 6: The Powers-of-2 Proof — Your Original Problem

---

*Feynman here. This is the chapter we've been building toward. Your homework problem. Let's crack it open.*

---

## Welcome Back to Where We Started

Remember this? The image you showed me at the very beginning? Let me write out exactly what was on that page:

```
Theorem: For all nonnegative integers: 1 + 2 + 2² + ... + 2ⁿ = 2ⁿ⁺¹ − 1

Proof:
[1]  For n = 0, 2⁰ = 1 = 2⁰⁺¹ − 1
[2]
[3]  1 + 2 + 2² + ... + 2ᵏ + 2ᵏ⁺¹
[4]  = (1 + 2 + 2² + ... + 2ᵏ) + 2ᵏ⁺¹
[5]  = (2ᵏ⁺¹ − 1) + 2ᵏ⁺¹
[6]  = 2 · 2ᵏ⁺¹ − 1
[7]  = 2ᵏ⁺² − 1   □
```

Step [2] is blank. And the question tells you: "the proof skips the step of stating the inductive hypothesis."

Four chapters ago, that might have sounded like gibberish. But now? Now you know exactly what's going on. Let's walk through every single line.

---

## First: What's the Theorem Actually Saying?

The theorem says: if you add up powers of 2, starting from 2⁰ all the way up to 2ⁿ, you always get 2ⁿ⁺¹ − 1.

Let's just check that this makes sense with some numbers:

```
n = 0:   2⁰                           = 1     and  2¹ − 1 = 2 − 1 = 1       ✓
n = 1:   2⁰ + 2¹                      = 1+2 = 3     and  2² − 1 = 4 − 1 = 3       ✓
n = 2:   2⁰ + 2¹ + 2²                 = 1+2+4 = 7     and  2³ − 1 = 8 − 1 = 7       ✓
n = 3:   2⁰ + 2¹ + 2² + 2³            = 1+2+4+8 = 15    and  2⁴ − 1 = 16 − 1 = 15     ✓
n = 4:   2⁰ + 2¹ + 2² + 2³ + 2⁴       = 1+2+4+8+16 = 31  and  2⁵ − 1 = 32 − 1 = 31     ✓
```

Beautiful. Every time you add up powers of 2, you get "one less than the next power of 2." It's like filling up a container — 1+2+4+8 = 15, which is *just* one short of 16.

If you're a computer person, this might look familiar. It's why 8-bit numbers go up to 255 (that's 2⁸ − 1), and why 16-bit numbers go up to 65,535 (that's 2¹⁶ − 1). This formula is everywhere in computing.

But we're not here to admire it. We're here to prove it.

---

## Step 0: Identify P(n)

> **P(n):** 1 + 2 + 2² + ... + 2ⁿ = 2ⁿ⁺¹ − 1

(Note: I'm writing 2⁰ as 1, since 2⁰ = 1. The proof on your page does the same thing.)

---

## Step 1: Base Case — That's Line [1]

The proof starts at n = 0 (not n = 1 this time — the theorem says "nonnegative integers," which starts at 0).

> **[1]** For n = 0, 2⁰ = 1 = 2⁰⁺¹ − 1

Let's unpack this carefully:

- Left side of P(0): just 2⁰, which is 1.
- Right side of P(0): 2⁰⁺¹ − 1 = 2¹ − 1 = 2 − 1 = 1.
- Left side = Right side = 1. ✓

> **Base case: verified.** ✓

First domino: down.

That's exactly what we've done in Chapters 3 and 5. Same move. Plug in, check, done.

---

## Step 2: The Inductive Hypothesis — THE MISSING LINE

Here it is. The blank. The gap. The thing the question is asking about.

**OK. This is your moment.** You've written inductive hypotheses twice now — once in Chapter 3, once in Chapter 5. You know the move: take P(n) and replace n with k.

P(n) is: 1 + 2 + 2² + ... + 2ⁿ = 2ⁿ⁺¹ − 1

**Write down what goes in step [2]. Do it now, before you scroll down. This is literally the answer to your homework.**

...

...

...

Here's what it should be:

> **Assume P(k) is true for some nonnegative integer k ≥ 0.**

And what does P(k) say? Take P(n) and swap n for k:

> **Assume: 1 + 2 + 2² + ... + 2ᵏ = 2ᵏ⁺¹ − 1**

That's it. That's what goes in the blank at line [2]. Did you get it? If you did — and I bet you did — then you just answered your homework question on your own. Everything from here is gravy.

Let me write it the way it would appear in the proof:

```
[2]  Assume that for some nonneg. integer k, 1 + 2 + 2² + ... + 2ᵏ = 2ᵏ⁺¹ − 1
```

This is the wrench. This is the ammunition. This is domino k, assumed to have fallen.

And you're about to see it get USED in line [5].

---

## Step 3: The Inductive Step — Lines [3] Through [7]

**Goal:** Show that P(k+1) is true. That means we need to show:

> 1 + 2 + 2² + ... + 2ᵏ + 2ᵏ⁺¹ = 2⁽ᵏ⁺¹⁾⁺¹ − 1 = 2ᵏ⁺² − 1

Our **target** is 2ᵏ⁺² − 1. Let's see how the proof gets there.

---

### Line [3]: Write Out the Left Side of P(k+1)

```
[3]  1 + 2 + 2² + ... + 2ᵏ + 2ᵏ⁺¹
```

This is just the sum of powers of 2 up to 2ᵏ⁺¹. Nothing clever yet — we're just writing down what we want to evaluate.

---

### Line [4]: Spot P(k) Hiding Inside

```
[4]  = (1 + 2 + 2² + ... + 2ᵏ) + 2ᵏ⁺¹
```

HERE IT IS. The move. The same move we've done twice before.

They've put parentheses around everything except the last term. Look at what's inside those parentheses:

```
(1 + 2 + 2² + ... + 2ᵏ)    +    2ᵏ⁺¹
╚═══════════════════════╝         ╚═══╝
      This is P(k)!             New term
```

The stuff in parentheses is the sum from 2⁰ to 2ᵏ. That's exactly the left side of P(k) — the thing we ASSUMED was true in step [2]!

---

### Line [5]: USE THE HYPOTHESIS ← This Is the Big Moment

**Before you look at line [5], think:** We just isolated (1 + 2 + 2² + ... + 2ᵏ) in parentheses in line [4]. You know the hypothesis from step [2]. What does the hypothesis say this chunk equals? What should line [5] look like?

...

...

...

```
[5]  = (2ᵏ⁺¹ − 1) + 2ᵏ⁺¹
```

THERE IT IS. They replaced (1 + 2 + 2² + ... + 2ᵏ) with 2ᵏ⁺¹ − 1.

Why can they do that? **Because of step [2].** Because the inductive hypothesis TOLD us that 1 + 2 + 2² + ... + 2ᵏ equals 2ᵏ⁺¹ − 1.

This is *exactly* the moment from our previous proofs:

- Chapter 3: we replaced (1 + 3 + ... + (2k−1)) with k²
- Chapter 5: we replaced (1 + 2 + ... + k) with k(k+1)/2
- Now: we replace (1 + 2 + 2² + ... + 2ᵏ) with 2ᵏ⁺¹ − 1

Same. Move. Every. Time.

And NOW you see why the missing step [2] matters so much! Without it, line [5] comes out of nowhere. You'd look at line [4] and then line [5] and say: "Wait — HOW did the stuff in parentheses turn into 2ᵏ⁺¹ − 1?" The hypothesis is the JUSTIFICATION for that substitution.

---

### Line [6]: Simplify — Combine the Two 2ᵏ⁺¹ Terms

**Quick mental check:** You've got (2ᵏ⁺¹ − 1) + 2ᵏ⁺¹. How many copies of 2ᵏ⁺¹ is that? And what happens to the −1?

...

...

...

```
[6]  = 2 · 2ᵏ⁺¹ − 1
```

We had (2ᵏ⁺¹ − 1) + 2ᵏ⁺¹ from line [5]. Let's just do the arithmetic:

```
  (2ᵏ⁺¹ − 1) + 2ᵏ⁺¹

= 2ᵏ⁺¹ − 1 + 2ᵏ⁺¹         ← drop the outer parentheses

= 2ᵏ⁺¹ + 2ᵏ⁺¹ − 1          ← rearrange (addition is commutative)

= 2 · 2ᵏ⁺¹ − 1              ← because X + X = 2X
```

That's it. Two copies of 2ᵏ⁺¹ added together give you 2 · 2ᵏ⁺¹. Just like 7 + 7 = 2 × 7. Nothing fancy.

---

### Line [7]: Simplify — Use the Exponent Rule

```
[7]  = 2ᵏ⁺² − 1   □
```

Here we use one of the basic rules of exponents:

> 2 · 2ᵏ⁺¹ = 2¹ · 2ᵏ⁺¹ = 2¹⁺ᵏ⁺¹ = 2ᵏ⁺²

That rule is: when you multiply powers of the same base, you ADD the exponents. So 2¹ times 2ᵏ⁺¹ = 2⁽¹⁺ᵏ⁺¹⁾ = 2ᵏ⁺².

Therefore:

```
2 · 2ᵏ⁺¹ − 1 = 2ᵏ⁺² − 1
```

And what were we trying to show? That P(k+1) is true, meaning:

> 1 + 2 + 2² + ... + 2ᵏ⁺¹ = 2⁽ᵏ⁺¹⁾⁺¹ − 1 = 2ᵏ⁺² − 1

We got 2ᵏ⁺² − 1. That's our target. **DONE.** ✓

The little square □ at the end of line [7] is the mathematician's way of saying "Q.E.D." — which is Latin for "that which was to be demonstrated." It means: "We're done. Drop the mic."

---

## The Complete Proof, With Nothing Missing

Let's write the whole thing out, with step [2] filled in, so you can see the complete, beautiful proof:

```
Theorem: For all nonnegative integers n, 1 + 2 + 2² + ... + 2ⁿ = 2ⁿ⁺¹ − 1

Proof (by mathematical induction):

[1]  Base case: For n = 0, 2⁰ = 1 = 2¹ − 1 = 1. ✓

[2]  Inductive hypothesis: Assume for some nonneg. integer k,
     1 + 2 + 2² + ... + 2ᵏ = 2ᵏ⁺¹ − 1.

     Inductive step: We must show P(k+1) is true, i.e.,
     1 + 2 + 2² + ... + 2ᵏ⁺¹ = 2ᵏ⁺² − 1.

[3]  1 + 2 + 2² + ... + 2ᵏ + 2ᵏ⁺¹

[4]  = (1 + 2 + 2² + ... + 2ᵏ) + 2ᵏ⁺¹        ← group the first k+1 terms

[5]  = (2ᵏ⁺¹ − 1) + 2ᵏ⁺¹                      ← substitute hypothesis from [2]

[6]  = 2 · 2ᵏ⁺¹ − 1                             ← combine like terms

[7]  = 2ᵏ⁺² − 1                                  ← exponent rule: 2¹ · 2ᵏ⁺¹ = 2ᵏ⁺²

     By induction, the theorem holds for all nonneg. integers n. □
```

---

## The Three-Proof Comparison

Let's put all three proofs side by side one last time. Look at how they're *identical* in structure:

| | Odd Numbers (Ch. 3) | Sum of Integers (Ch. 5) | Powers of 2 (Ch. 6) |
|---|---|---|---|
| **P(n)** | 1+3+...+(2n−1) = n² | 1+2+...+n = n(n+1)/2 | 1+2+2²+...+2ⁿ = 2ⁿ⁺¹−1 |
| **Base** | n=1: 1=1² ✓ | n=1: 1=1(2)/2 ✓ | n=0: 1=2¹−1 ✓ |
| **Hypothesis** | Assume true for k | Assume true for k | Assume true for k |
| **Key move** | Replace sum with k² | Replace sum with k(k+1)/2 | Replace sum with 2ᵏ⁺¹−1 |
| **Simplify** | k²+2k+1 = (k+1)² | k(k+1)/2+(k+1) = (k+1)(k+2)/2 | 2·2ᵏ⁺¹−1 = 2ᵏ⁺²−1 |

Three different theorems. Three different formulas. **One identical strategy.**

---

## So What's the Answer to Your Homework?

Your homework asks what's missing at step [2]. Now you can answer with confidence:

> **Step [2] should state the Inductive Hypothesis:**
> "Assume that for some nonnegative integer k, 1 + 2 + 2² + ... + 2ᵏ = 2ᵏ⁺¹ − 1."

And you can explain WHY it matters: because step [5] *uses* this assumption to replace the parenthesized sum with 2ᵏ⁺¹ − 1. Without step [2], step [5] has no justification.

---

## What to Take Away

**1. You just read a real induction proof — your homework proof — and understood every line.** That's not nothing. That's huge.

**2. The missing step [2] is the inductive hypothesis.** It's the assumption that P(k) is true, which gets used as the justification for the substitution in step [5].

**3. All three proofs we've seen follow the same pattern.** Base case → hypothesis → spot P(k) → substitute → simplify. The formula changes; the method never does.

**4. The exponent rule (2ᵃ · 2ᵇ = 2ᵃ⁺ᵇ) was the only "new" algebra here.** Everything else was the same induction machinery you already knew.

---

[Next: Chapter 7 — Common Mistakes & How to Avoid Them →]({{ site.baseurl }}/chapters/07-common-mistakes/)
