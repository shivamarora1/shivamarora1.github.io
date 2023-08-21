---
categories: [ai]
published: false
title: What really Prompt Engineers do?
---

With the rise of **AI generative** tools like **ChatGPT**, **Dall-E**, **Whisper** , A new term Prompt Engineering also came to world. But what kind of engineers are **prompt engineer**. Let us first understand meaning of word *Prompt*.

A *prompt* is something we give to trained model to get the useful output. A *prompt* can change depending upon the trained model that you are using. For **Chat GPT** it is textual, for **Dall-E** it can be textual or image.

![prompt_input_output](/assets/images/prompt_engineer.png)

**Prompt engineer** is person who creates *prompts* for the training models so that you can get best possible result from them. Basically prompt engineer decides best effective way to communicate with the trained model. Once prompt engineer has decided suitable prompt to get the best result then other persons can use that as a template to get different results.

![garbage_prompt_output](/assets/images/garbage_prompt.png)

Let us try to understand this with a example. 

`Suppose there is a task in upwork in which you have to write prompts for a quiz based application to generate the multi choice questions with answers on certain topic.`

The prompt template for this task would be: 
```
{no-questions} unique question on {topic} with {choices} choices in {csv|json|yaml} format
```

In this template user have to replace variables to get the desired output. This is simplest example of prompt engineering's work but it can become complex as per requirement.
```
Write a prompt to generate the thumbnail for the batch of Youtube videos.
Write a prompt to extract required information from the CV.
``