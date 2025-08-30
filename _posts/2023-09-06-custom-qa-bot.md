---
categories: [ai]
title: Make your own ChatGPT on custom data
thumbnail: "/assets/images/chat_gpt_embeddings_working.png"
---
We all know **ChatGPT** is AI powered model which can interact with humans. Literally you can ask any thing to **ChatGPT** like *recipes for incoming birthday*, *gifts idea for anniversary*, *questions related to any law* etc. The catch here is ChatGPT has knowledge only until **2021** generally available data. It means ChatGPT can't answer about the events happended after **2021**. Also it does not have knowledge about your private data.

This makes the use case of ChatGPT very much limited. Is there any way in which we could extend the **knowledge** of ChatGPT? Is it possible to retrain the ChatGPT with **private documents** ?

In this **article** we will try to figure out answer about above questions. But let's first understand how Chat GPT works. 

#### <u>Under the hood of ChatGPT:</u>
ChatGPT uses LLM (**Large Language Model**) to answer various queries. LLM gives ability to retrieve, generate, translate, predict content from the very large data sets.

![chat_gpt_working](/assets/images/chat_gpt_working.png)

So simply adding data to datasets of LLM would solve our problem? Technically no, because ChatGPT knowledge is private and we can't modify in the knowledge of ChatGPT. 

#### <u>Retrieval Argument Generation:</u> 
Retrieval Argument Generation is a technique in which we extract and attach relevant context with question that is helpful in answering. LLM uses this relevant context to answer the question.

![chat_gpt_working](/assets/images/chat_gpt_embeddings_working.png)

The description of steps are as below:
1. <b>Load the arbitrary document</b> into the vector database. Vector database breaks the document into chunks and allows you search / query them according to semantic similarity. It means that you can fetch data that have same context from the vector DB.
2. <b>Standalone question:</b> Using prompts we first fetch chunks with similar context are from vector database and then using the retrieved context and initial question we make a standalone question.
3. <b>Sending to LLM:</b> Then this standalone question is sent to the LLM model for more refinement and generating the response in given format.

Checkout the whole code in actions: <br>
<a href="https://github.com/shivamarora1/docs-gpt">https://github.com/shivamarora1/docs-gpt</a>