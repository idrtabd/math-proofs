---
layout: default
title: "Chapter 7: Common Mistakes & How to Avoid Them"
---

[← Back to Table of Contents]({{ site.baseurl }}/) | [← Chapter 6]({{ site.baseurl }}/chapters/06-powers-of-2/)

# Chapter 7: Common Mistakes & How to Avoid Them

---

*Feynman, one last time. We've built the machine. Now let's make sure you don't accidentally stick your hand in it.*

---

## Why This Chapter Exists

You know what? Most textbooks teach you how to do something and then move on. They don't tell you how to do it *wrong*. And that's a problem, because knowing the common traps is half the battle.

I learned more physics from my mistakes than from my successes. Every wrong answer I ever got taught me something the right answer couldn't. So let's learn from the mistakes OTHER people make, so you don't have to make them yourself.

Here are the seven deadly sins of induction proofs.

---

## Mistake #1: Skipping the Base Case

**What it looks like:**

> "Assume P(k) is true. Then P(k+1) is true because... [algebra]. Therefore P(n) is true for all n."

**What's wrong:**

No base case! You proved that IF any domino falls, the next one falls too — but you never knocked over the FIRST domino. So nothing ever starts.

This is like building an elaborate Rube Goldberg machine and then forgetting to push the marble. The whole chain reaction just... sits there.

**Why this matters more than you think:**

Here's something wild. Without a base case, you can "prove" things that are completely FALSE. Watch this:

> **False "theorem":** For all n ≥ 1, n = n + 1.
>
> **Bogus "proof":**
> Assume k = k + 1. Then k + 1 = (k + 1) + 1. So if P(k) is true, P(k+1) is true.
> "By induction," n = n + 1 for all n. ∎

**What's wrong here?** This "proof" has an inductive step. It looks like it follows the template. But something crucial is missing. Can you spot it before I tell you?

...

...

...

We just "proved" that every number equals the number after it. Which would mean 1 = 2 = 3 = 4 = ... and the entire number system collapses.

But of course, we can't do the base case: is 1 = 2? No. Obviously not. The base case CATCHES the lie. Without it, the inductive step is just a chain reaction that never starts — and in this case, it's a chain reaction that SHOULDN'T start, because the whole statement is garbage.

**The fix:** Always. Do. The. Base. Case. Even when it feels trivial. *Especially* when it feels trivial.

---

## Mistake #2: Skipping the Inductive Hypothesis

**What it looks like:**

This is literally your homework problem! The proof goes from the base case straight to the algebra of the inductive step, without ever stating what it's assuming.

```
[1]  Base case ✓
[2]  (blank)
[3]  Start doing algebra...
```

**What's wrong:**

Without the hypothesis, step [5] in your proof — where you replace the sum with 2ᵏ⁺¹ − 1 — has no justification. It's like a lawyer saying "and therefore the defendant is guilty" without presenting any evidence.

You might think: "But it's obvious what the hypothesis is — it's just the theorem with k instead of n."

And yes, it IS obvious to someone who already understands induction. But math doesn't run on "obvious." Math runs on "stated and justified." The hypothesis is the LEGAL BASIS for the substitution in the inductive step. If you don't state it, the substitution is unauthorized.

**The fix:** Write it down every single time. Make it a reflex. After the base case, your pen should automatically write: "Assume P(k) is true for some integer k ≥ [starting value]." Then write out what P(k) actually says.

---

## Mistake #3: Assuming What You're Trying to Prove

**What it looks like:**

> "We want to show that 1 + 2 + ... + n = n(n+1)/2.
> Assume 1 + 2 + ... + n = n(n+1)/2.
> Then it's true. ∎"

**What's wrong:**

This person assumed P(n) for ALL n, not just for a specific k. They assumed the whole theorem, then concluded the theorem. That's circular reasoning. That's a dog chasing its own tail.

**Can you explain the difference?** Before reading on, try to articulate — in your own words — what makes the inductive hypothesis DIFFERENT from just assuming the whole theorem. You've got the domino analogy. Use it.

...

...

...

**How it's different from the inductive hypothesis:**

The inductive hypothesis assumes P(k) — for ONE specific, particular value k. Not for all n. Not for k+1. Just for k. And then you PROVE — with actual algebra — that P(k+1) follows.

There's a world of difference between:

- ❌ "Assume it's true for everything" (circular)
- ✓ "Assume it's true for k, then PROVE it for k+1" (induction)

**The fix:** Be precise with your language. You assume P(k). You prove P(k+1). Those are two different statements, and the work you do in the inductive step is what bridges the gap between them.

---

## Mistake #4: Using the Wrong Base Case

**What it looks like:**

The theorem says "for all n ≥ 0" but you start with n = 1. Or the theorem says "for all n ≥ 3" but you start with n = 1.

**What's wrong:**

You need to check the FIRST value the theorem claims to be true for. If the theorem says n ≥ 0, you check n = 0. If it says n ≥ 5, you check n = 5.

In your homework, the theorem says "for all nonnegative integers" — that means starting at n = 0. And indeed, step [1] checks n = 0, not n = 1.

**Why this matters:**

Some formulas are true starting from n = 3 but false for n = 1 and n = 2. If you check the wrong base case, you might "prove" a statement for values where it's actually false.

**The fix:** Read the theorem carefully. What's the starting value? Check THAT one.

---

## Mistake #5: Doing the Algebra Wrong

**What it looks like:**

The induction structure is perfect — base case, hypothesis, inductive step — but somewhere in the simplification, there's an algebra error. A sign is wrong, a term is dropped, a fraction isn't handled correctly.

**What's wrong:**

This isn't really an induction mistake. It's an algebra mistake that happens to occur inside an induction proof. But it's the NUMBER ONE reason students get induction problems wrong on exams.

**The most common algebra errors in induction proofs:**

Let me show you each one — the WRONG way and the RIGHT way side by side, so you can see exactly where students go off the rails:

```
ERROR 1: Forgetting the negative sign stays

  WRONG:  (2ᵏ⁺¹ − 1) + 2ᵏ⁺¹  =  2·2ᵏ⁺¹ − 1 + 1  =  2·2ᵏ⁺¹
  RIGHT:  (2ᵏ⁺¹ − 1) + 2ᵏ⁺¹  =  2ᵏ⁺¹ − 1 + 2ᵏ⁺¹  =  2·2ᵏ⁺¹ − 1
                                          ↑
                            The −1 doesn't go anywhere!
```

```
ERROR 2: Wrong exponent rule

  WRONG:  2 · 2ᵏ  =  4ᵏ       (NO! You don't multiply the bases!)
  RIGHT:  2 · 2ᵏ  =  2¹ · 2ᵏ  =  2ᵏ⁺¹   (Add the exponents!)

  Check with real numbers: 2 · 2³ = 2 · 8 = 16 = 2⁴ = 2³⁺¹  ✓
  But 4³ = 64. Not 16. The wrong answer isn't even close.
```

```
ERROR 3: Forgetting the middle term when squaring

  WRONG:  (k+1)²  =  k² + 1
  RIGHT:  (k+1)²  =  (k+1)(k+1)  =  k² + k + k + 1  =  k² + 2k + 1
                                           ↑
                            Don't forget the 2k in the middle!
```

**The fix:** Slow down during the algebra. Write every step. Don't skip "obvious" simplifications — those are where mistakes hide. And when in doubt, check with a specific number. Plug in k = 3 and see if both sides match. The number check catches mistakes instantly.

---

## Mistake #6: Not Actually Using the Hypothesis

**What it looks like:**

The student writes down the hypothesis, then never uses it. They try to prove P(k+1) from scratch, without referring to P(k) at all.

**What's wrong:**

If you're not using the hypothesis, you're not doing induction. You're trying to prove the formula directly — which is a different (and usually harder) approach.

The whole POINT of induction is that you get to use P(k) as a stepping stone to P(k+1). The hypothesis is a gift. It's free. Use it.

**How to tell if you've used it:**

Look at your inductive step. There should be a specific line where you substitute something. A line where the left side of P(k) gets replaced by the right side of P(k). If that line doesn't exist — if there's no substitution — you haven't used the hypothesis.

In your homework proof, that moment is line [5], where (1 + 2 + 2² + ... + 2ᵏ) becomes (2ᵏ⁺¹ − 1). That substitution IS the hypothesis in action.

**The fix:** When you're doing Step 3, actively LOOK for where P(k) is hiding. It's always there. Find it, substitute it, and you're on your way.

---

## Mistake #7: Thinking Induction Is Just for Sums

**What it looks like:**

A student learns induction through sum formulas (like we did!) and then thinks: "OK, induction is a technique for adding things up."

**What's wrong:**

Induction works for ANY statement about natural numbers. Sums are just the most common first examples because they're clean and the algebra is manageable. But induction can prove:

- Divisibility: "6 divides n³ − n for all n ≥ 1"
- Inequalities: "2ⁿ > n² for all n ≥ 5"
- Counting: "A set with n elements has 2ⁿ subsets"
- Geometry: "The angles of any n-sided convex polygon sum to (n−2)·180°"
- And much, much more

The structure is ALWAYS the same: base case, hypothesis, inductive step. The content changes, but the skeleton doesn't.

**The fix:** Remember that induction is a LOGICAL STRUCTURE, not a calculation technique. It works for any statement P(n) where you can show that P(k) implies P(k+1).

---

## The Final Checklist

Here's your "before you submit" checklist. Run through it every time you write an induction proof:

```
□  Did I state what P(n) is?
□  Did I do the base case for the CORRECT starting value?
□  Did I STATE the inductive hypothesis? (Not just think it — WRITE IT.)
□  Did I clearly state what P(k+1) looks like — what I'm trying to show?
□  Did I actually USE the hypothesis? (Can I point to the exact line?)
□  Did I double-check my algebra?
□  Did I write a conclusion?
```

If you can check every box, your proof is solid.

---

## The End — But Really, The Beginning

We've covered a lot of ground in seven chapters:

1. **Why we need induction** — patterns lie, examples aren't proof, you can't check infinity
2. **The domino principle** — base case + inductive step = all dominoes fall
3. **Your first proof** — the odd numbers sum, every step explained
4. **The universal template** — every induction proof has the same skeleton
5. **A second proof** — the sum of integers, same dance different music
6. **Your homework proof** — the powers of 2, decoded line by line
7. **Common mistakes** — the seven traps and how to dodge them

You walked in saying "I know very little math." But you just understood a proof technique that many college students struggle with. You understood it not by memorizing steps, but by understanding WHY it works — the dominoes, the logic, the structure.

That's how you learn math. Not by memorizing. By understanding.

Now go fill in that step [2], and know exactly why it belongs there.

---

*"The first principle is that you must not fool yourself — and you are the easiest person to fool."*
*— Richard Feynman*

*Course complete.*

---

[← Back to Table of Contents]({{ site.baseurl }}/)
