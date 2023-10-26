---
categories: [ai]
title: Document Transformers?
hidden: true
---
### Document Transformers
In this article we are going to discuss about the document transformers. Basically document transformer is the process in which we split the large documents into multiple smaller chunks so that they can be retrieved easily.

The document transformation seems easy but it becomes complex when you go deeper.

``` mermaid
---
title: Document Transformation
---
flowchart LR
    LD[Large Document]
    subgraph chunks
        direction TB
        CH1[Chunk 1]
        CH2[Chunk 2]
        CH3[Chunk 3]
        CH1 ~~~ CH2 ~~~ CH3
    end

    VDB[(Vector DB)]
    LD --> chunks
    chunks --> VDB
```

In RAG (Retrieval-Augmented Generation), Knowledge of LLM is extended by providing context of the document. This makes the answer of LLM more reliable and avoids hallucination. The pipeline for converting raw data looks like this in RAG:
1. Loading
2. Splitting
3. Storage
4. Retrieval
5. Generation

```mermaid
---
Title: RAG Chain
---
flowchart LR
    subgraph Loading
        direction TB
        url[[URL]]
        db[(Database)]
        url ~~~ db
    end    
    
    subgraph Splitting
        direction TB
        ch-1[Chunk 1]
        ch-2[Chunk 2]
        ch-3[Chunk 3]
        ch-1  ~~~ ch-2 ~~~ ch-3
    end

    subgraph Storage
        direction TB
        VS[(Vector Store)]
    end

    subgraph Retrieval
        direction TB
        ch-4[Chunk]
        ch-5[Chunk]
        ch-6[Chunk]
        ch-4  ~~~ ch-5 ~~~ ch-6
    end
    
    subgraph Output
        direction LR
        pr[Prompt]
        llm((LLM))
        pr  --> llm
    end

    ans(Answer)

    Loading --Documents--> Splitting    
    Splitting --> Storage
    Storage --Similar Search --> Retrieval
    Retrieval --Relevant Splits--> Output
    Output --> ans
```

reference: 
https://python.langchain.com/docs/use_cases/question_answering/
https://www.promptingguide.ai/techniques/rag
https://python.langchain.com/docs/modules/data_connection/document_transformers/
