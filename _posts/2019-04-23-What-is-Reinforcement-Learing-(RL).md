---
title: "What is Reinforcement Learning (RL)"
published: true
---

# Preface
I am a student studying in Singapore Polytechnic, currently in year 3. I truly enjoy what my course, Diploma in Computer Engineering has to offer. However, I have yet to see a chance to explore some of my ideas I have since I was year one. Over the years of hackathons, projects, and most importantly guidance from mentors and peers, I feel like I know enough to learn RL at my own pace. This blog is to document what I have learnt over a two-week from my school holiday.

## FUNdementals
To discuss RL in specific terms, it is important to understand the following terminology:
- ```agent``` : this is an algorithm in your machine that you train to achieve your goal
- ```environment``` : this is the place your `agent` interacts with
- ```state``` :  The instantaneous situation the agent finds itself in in relation to other factors.
- ```action``` : This is the step that your agent takes upon determining from the multitude of possible steps from a `state`
- ```reward``` : A feedback used to measure the success/failure of the `agent`.
- ```discount``` : As time goes on, we all die. This is why we include the discount factor, to maximize time to live and do not let the "end game" `action`s affect the early game performance.
- ```episode``` : The session the agent runs from start to finish. 

At the core of RL, we want the agent to learn the best actions to achieve a particular outcome through trial and error. There are multiple methods to be discussed but releasing it all in one article just spoils all the fun hehehe. Today we focus more on the technical terms.

Using the definitions above, we can see how they come together. The `agent` is what we have designed. The `environment` is a function/black box that transforms the `agent`'s current `state` and `action` taken into the next `state` and a feedback(`reward`), while the `agent` `transforms` the new `state` and `reward` into a next `action`. The `agent`'s job is to approximate the `environment`'s function to find the maximum `reward` it produces after each `episode`. A `discount` can be added to allow high performance early in the `episode` (and possibly forever!).

![RL-flow](/images/RL-flow.png)

So, using the above phenomena, we can observe more phenomenas and they can be expressed mathematically. Hence, let's also define a few terms:

- ```policy``` : A strategy that the `agent` uses to determine the next `action` based on the current `state`. It maps `state`s to `action`s of highest `reward`.
- ```Q-value``` or ```action-value``` : `Q` is a abbreviation for `Quality`. This is the expected long-term return with `discount`, taking into consideration of `action`. This value maps `state-action pairs` to `rewards`, having a subtle difference with `policy`.
- ```Value``` : the overall expected `reward` in a particular `state` until the end of the `episode` following a particular `policy` also considering `discounts`. 

Hang on, the definition of `Q-value` and `Value` are similar. Are they the same?

Think of `Value` as the label, and `Q-value` is the predicted outcome. The `policy` is supposed to be updated. With this statement in mind, we actually have some sort of gradient here we can optimize! 

- ```Advantage Function``` :The difference between the `Q-value` and the `Value`.

These are all the important terms, I'll be writing a separate article on model based and model free. Do keep an eye on it!

That's it for today! These should be pretty easy to remember right? The following article will closely tie to this article so stay tuned!

References:
- [https://towardsdatascience.com/the-complete-reinforcement-learning-dictionary-e16230b7d24e]
- [https://skymind.ai/wiki/deep-reinforcement-learning#define]