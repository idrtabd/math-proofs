# Chapter 2: The Domino Principle

---

*Still Feynman. Still no bongos. But we're getting closer.*

---

## Forget Math for a Minute

I want you to forget you're learning math. Completely forget it. We're going to talk about dominoes.

You know dominoes, right? You line them up in a row, you flick the first one, and they all go *clickclickclickclickclick* — one after another, all the way down the line.

Now let me ask you something. Suppose I tell you two things about a row of dominoes:

> **Thing 1:** The first domino falls.
>
> **Thing 2:** Whenever ANY domino falls, it knocks over the next one.

If both of those things are true — do ALL the dominoes fall?

Think about it.

...

Yeah. Of course they do. *Of course* they do. It's obvious. The first one falls (Thing 1). That knocks over the second one (Thing 2). The second one knocks over the third (Thing 2 again). The third knocks over the fourth (Thing 2, still working). And so on, and so on, forever.

You don't need to check each domino individually. You don't need to walk down the line and verify that domino number 4,712 fell. You *know* it fell, because:

- Domino 1 fell. *(Thing 1)*
- Domino 1 falling caused domino 2 to fall. *(Thing 2)*
- Domino 2 falling caused domino 3 to fall. *(Thing 2)*
- ...keep going...
- Domino 4,711 falling caused domino 4,712 to fall. *(Thing 2)*

Done. Every domino. All of them. Infinite dominoes, if you like — they ALL fall.

And you proved it with just **two things**.

That's induction. That's the whole idea. We're done.

---

## No, Seriously. That's It.

I'm not being cute. That really is the entire idea behind mathematical induction. Everything else is just translating this domino thing into math language.

But let me say it again, because it's so important:

> **To prove that every domino falls, you only need two things:**
>
> 1. Show that the first one falls.
> 2. Show that if any one falls, the next one falls too.

That's it. Two steps. And you've conquered infinity.

---

## Now Let's Translate to Math (Gently)

OK, let's bring math back — but gently. Softly. We'll barely feel it.

Remember our pattern from Chapter 1? Adding odd numbers gives perfect squares:

```
1                       = 1²
1 + 3                   = 2²
1 + 3 + 5               = 3²
1 + 3 + 5 + 7           = 4²
1 + 3 + 5 + 7 + 9       = 5²
```

We want to prove this works for ALL numbers. Every single one. Forever.

Each "case" is like a domino:

```
Domino 1:   "Adding the first 1 odd number gives 1²"        (that's just: 1 = 1)
Domino 2:   "Adding the first 2 odd numbers gives 2²"       (that's: 1+3 = 4)
Domino 3:   "Adding the first 3 odd numbers gives 3²"       (that's: 1+3+5 = 9)
Domino 4:   "Adding the first 4 odd numbers gives 4²"       (that's: 1+3+5+7 = 16)
...
Domino n:   "Adding the first n odd numbers gives n²"
...forever.
```

There are infinitely many dominoes. We can't check them all. But we don't need to! We just need:

**Thing 1 (The Base Case):** Show that the first domino is true.

> Is it true for n = 1? Does the first odd number equal 1²?
>
> Well, the first odd number is 1, and 1² = 1. Yep. ✓
>
> *The first domino falls.*

**Thing 2 (The Inductive Step):** Show that IF any domino is true, THEN the next one must be true as well.

> This is the big one. This is the engine. This is the part that says: "I don't care WHICH domino you point at — if that one's fallen, the next one's going down too."

And there's a crucial detail hiding inside Thing 2 that I need you to really hear:

---

## The Assumption That Scares People

Here's where students panic. Thing 2 requires you to **assume** something is true.

"Wait — ASSUME? I thought we were PROVING things! How can you just ASSUME something?"

I get it. It feels like cheating. But it's not. Here's why.

Think back to the dominoes. When I said "whenever any domino falls, it knocks over the next one" — I wasn't saying all the dominoes have already fallen. I was describing a **relationship** between neighbors. I was saying: "Pick any domino. IF that one falls, THEN the next one will too."

I'm not claiming domino number 847 has fallen. I'm saying: "IF 847 falls, THEN 848 *will* fall." That's a completely different statement. It's a **conditional** statement. An if-then.

And notice — I don't need domino 847 to have actually fallen to make this argument! I just need to show that the dominoes are set up in such a way that each one *would* knock over the next one *if* it fell.

So in the math version:

> **The assumption (called the "inductive hypothesis"):** Suppose the formula works for some number k. We don't know which k. We don't care. Just... pick one. Assume it works for that one.
>
> **What we then prove:** Using that assumption, we show the formula MUST also work for k + 1.

If we can do that — if we can show that the truth *travels* from any k to k + 1 — then combined with the base case, we're done. The dominoes all fall.

---

## A Non-Math Example (Because Why Not)

Suppose I tell you about an infinite line of people, numbered 1, 2, 3, 4, ...

And I tell you two things:

> **Thing 1:** Person 1 knows the secret.
>
> **Thing 2:** Whenever a person knows the secret, they immediately tell the next person.

Does person 1,000,000 know the secret?

Of course. Person 1 tells person 2 (Thing 2). Person 2 tells person 3 (Thing 2). This chain keeps going. Person 999,999 tells person 1,000,000 (Thing 2).

Does person *n* know the secret, for any n?

Yes. Every person in the line knows the secret.

And you didn't need to check each person individually. You just needed Thing 1 and Thing 2.

**Same structure. Same logic. That's induction.**

---

## The Three Parts, Named

Alright, let's give our pieces their official names. You'll see these everywhere:

| Domino Language | Math Language | What It Means |
|---|---|---|
| The first domino falls | **Base Case** | The statement is true for the first value (usually n = 0 or n = 1) |
| Assume domino k has fallen | **Inductive Hypothesis** | Assume the statement is true for some arbitrary number k |
| Then domino k+1 falls | **Inductive Step** | Prove the statement is true for k+1, using the assumption about k |

**Base Case** + **Inductive Hypothesis** + **Inductive Step** = proof for ALL numbers.

That's the whole machine. Three parts.

And here's the beautiful thing: the Inductive Hypothesis — the assumption — isn't some separate thing you have to prove. It's a *tool*. You pick it up, you use it inside the inductive step, and it's what makes the whole argument click together.

---

## Let's Make Sure This Really Landed

Before we move on, I want to give you a quick gut-check. Answer these in your head:

**Question 1:** In the domino metaphor, what does the "base case" correspond to?

*(Answer: Knocking over the first domino.)*

**Question 2:** What is the inductive hypothesis?

*(Answer: The ASSUMPTION that some particular domino — domino k — has fallen. We don't prove this separately. We assume it, then show what follows.)*

**Question 3:** What is the inductive step?

*(Answer: Showing that IF domino k has fallen, THEN domino k+1 must fall too.)*

**Question 4:** Why do these two things together prove the statement for ALL numbers?

*(Answer: The base case starts the chain. The inductive step keeps it going. Together, they reach every number, no matter how large.)*

**Question 5:** Is the inductive hypothesis "cheating" — are we assuming what we're trying to prove?

*(Answer: No! We're not assuming the whole thing is true. We're assuming it's true for ONE specific value k, and then we PROVE it must be true for k+1. Combined with the base case, this creates an unbreakable chain.)*

---

## What's Coming Next

In Chapter 3, we're going to actually DO one. A real, full induction proof. With numbers and equals signs and everything. But it won't be scary, because now you know what's happening behind the curtain:

We're just knocking over dominoes.

---

*Next time, in Chapter 3: We prove that 1 + 3 + 5 + ... + (2n−1) = n², step by excruciating step. Training wheels fully on.*
