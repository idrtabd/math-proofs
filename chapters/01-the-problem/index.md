---
layout: default
title: "Chapter 1: The Problem That Started It All"
---

[← Back to Table of Contents]({{ site.baseurl }}/)

# Chapter 1: The Problem That Started It All

---

*In the style of Richard Feynman — physicist, bongo drummer, safe-cracker, and the greatest explainer who ever lived.*

---

## Let's Play a Game

Alright, come here. Sit down. Forget everything anyone ever told you about "proofs." We're going to play a game.

I'm going to add up odd numbers. Just the odd ones. Starting from 1. And I want you to watch what happens.

```
1                       = 1
1 + 3                   = 4
1 + 3 + 5               = 9
1 + 3 + 5 + 7           = 16
1 + 3 + 5 + 7 + 9       = 25
```

Now — do you see it?

Look at the right-hand side. 1, 4, 9, 16, 25...

Those are **perfect squares**. 1², 2², 3², 4², 5².

Isn't that something? You just add up the first few odd numbers and — *bang* — you get a perfect square every time. Every. Single. Time.

Go ahead, try the next one yourself:

```
1 + 3 + 5 + 7 + 9 + 11  = ?
```

You get 36. Which is 6². Of course it is!

So here's what you're probably thinking: *"OK, Feynman, that's a cute pattern. It works for 1 through 6. It probably works forever."*

And you'd be right! It does work forever. But here's the thing that's going to bother you — or at least, it *should* bother you:

**How do you KNOW?**

---

## The Trouble With "Probably"

See, this is where most people stop. They say, "I checked a bunch of cases, it keeps working, therefore it's true." And in everyday life, that's perfectly reasonable. If you flip a light switch six times and the light turns on every time, you don't sit there wondering if it'll work a seventh time. You just trust it.

But mathematics isn't a light switch. Mathematics is *weirder* than a light switch.

Let me show you why "it worked every time I checked" is **dangerous** in math.

Here's a formula. It looks totally innocent:

> Is the number n² + n + 41 always a prime number?

Let's check:

```
n = 0:   0 + 0 + 41  = 41     ← prime!
n = 1:   1 + 1 + 41  = 43     ← prime!
n = 2:   4 + 2 + 41  = 47     ← prime!
n = 3:   9 + 3 + 41  = 53     ← prime!
n = 4:   16 + 4 + 41 = 61     ← prime!
n = 5:   25 + 5 + 41 = 71     ← prime!
```

Hey, this is great! Primes every time! Let's keep going...

```
n = 10:  100 + 10 + 41 = 151   ← prime!
n = 20:  400 + 20 + 41 = 461   ← prime!
n = 30:  900 + 30 + 41 = 971   ← prime!
```

This formula gives you a prime number for n = 0, 1, 2, 3, 4, 5, 6, 7... all the way up to n = 39. That's **forty straight successes**. Forty!

You'd be pretty confident by now, right?

But then:

```
n = 40:  1600 + 40 + 41 = 1681 = 41 × 41
```

**Boom.** Not prime. The pattern breaks at n = 40.

Forty examples. All perfect. And the forty-first? A lie.

This is why mathematicians are paranoid. This is why mathematicians don't say "it works for every number I tried." Because in math, "every number I tried" might be the first 40 out of *infinity*. And infinity is a lot bigger than 40.

---

## So What Do We Do?

OK so we have a problem. A real problem. We've got this beautiful pattern — adding odd numbers gives perfect squares — and we *believe* it's true for all numbers, but we can't check all numbers because there are infinitely many of them. We'd be checking forever. Literally forever.

We need a different strategy entirely.

And this is the moment — right here — where one of the most elegant ideas in all of mathematics walks through the door.

It's called **mathematical induction**.

And the beautiful thing about it is this: it lets you prove something is true for *every* number — all infinitely many of them — in a **finite** number of steps.

That sounds like a magic trick, right? Proving an infinite number of things with a finite amount of work?

It is a magic trick. One of the best ones humans ever invented.

But we're going to save the trick for Chapter 2. Because right now, I want you to sit with that *discomfort*. I want you to really feel the problem:

> **Patterns can fool you. Examples aren't proof. And you can't check infinity.**

That's the problem. That's the itch.

Mathematical induction is the scratch.

---

## What to Take Away from This Chapter

Here's what I want in your head before we move on:

**1. Patterns are seductive.** Adding odd numbers gives perfect squares — it's gorgeous, and it *is* true. But seeing it work for 5, 10, even 100 cases doesn't tell you it works for case 101.

**2. Examples can betray you.** That n² + n + 41 formula was a traitor. Forty perfect results, then — failure. In math, you cannot trust examples alone. Not ever.

**3. We need a new tool.** A tool that lets us go from "I think this is always true" to "I *know* this is always true." A tool that handles infinity.

That tool is induction. And it's coming next.

---

[Next: Chapter 2 — The Domino Principle →]({{ site.baseurl }}/chapters/02-the-domino-principle/)
