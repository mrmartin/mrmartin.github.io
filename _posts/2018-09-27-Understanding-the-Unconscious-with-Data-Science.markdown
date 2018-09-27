---
layout: post
title:  "Understanding the Unconscious with Data Science"
date:   2018-09-27 09:54:30 +0100
categories: science psychology
---
{% include analytics.html %}

The human mind is boggling, and the way we think has yet to be understood. Popular science book "[On Human Nature](https://www.amazon.com/Human-Nature-Edward-Wilson-ebook/dp/B00AQLFQKW/ref=sr_1_6?s=digital-text&ie=UTF8&qid=1538044010&sr=1-6&keywords=edward+o+wilson)" by Edward O. Wilson first takes apart psychology and psychiatry as unscientific, and then explores the potential of "Sociobiology", a rigurous study of human behaviour through quantifiable fact: biology.

But we can go beyond mapping evolutionary biology and brain chemistry to model the mind. We can hope to understand the subconscious using Data science. An instance of this kind of exploration is to find synonymous expressions with different emotional footprint, and map them to state-of-mind. Let me explain what I mean.

Imagine the following experimental setup: for each partcicipant, ask how they feel (very unhappy to very happy), then get them to listen to a recorded dialogue. Next, ask them to paraphrase something which was mentionned. By analyzing how they phrase the factual information, we can dilute the subjective perspective out of it. The original recorded sentence may be "Good soup". Sad people are likely to say "Joey said that the soup wasn't terrible", and happier subjects may say "His friend said he liked the soup".

Utterances can be mapped to an embedding which separates meaning from expression, and the way a phrase has been expressed can then be mapped to the happy/sad information we started with. This way, through established methods of machine learning and natural language processing, we may extract the emotional information carried by subtleties in speech. And whether we are happy or sad is just the first of many dimensions.

I believe that this framework can be extended to help us analyze a lot of what's happening in the human mind beyond the objective information we communicate, and beyond what we ourselves know we are expressing to others. It can take us away from a sensible but ungrounded theory of psychology, where a list of words is associated to a state of mind because Jung hypothesized it is so, and into the realm of quantifiable science, where the words for a given state of mind can be correlated to the state of mind with a grounding in data and a verifiable p-value.
