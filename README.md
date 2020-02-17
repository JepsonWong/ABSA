# ABSA (Aspect-based Sentiment Analysis)

关注phrase和word级别的情感分析，取决于aspect context。

## Why

在文档和句子级别对文本进行情感分类通常是不够的，因为他们没有确定意见目标或将情感分配给这些**目标**。即使我们假设每个文档或者句子都评估一个**实体**，一个对实体的正面评价文本并不意味着对**实体的各个方面**都具有正面评价；同时，一个负面评价文本并不意味着对**实体的各个方面**都持负面态度。

为了进行更全面的分析，我们需要发现文本的各个方面（aspect），并确定每个方面的情绪是正面还是负面的。

## What

针对传统的文档或句子级别的情感分析，分析时主要有四部分组成：(g, s, h, t)
* g: the opinion (or sentiment) target (can be decomposed into an **entities**(or objects) and an attribute(or features/**aspects**/facets/topics) of the entity) (**Note**: **A target is usually an entity or an entity aspect.** When an opinion is on the entity itself as a whole, the special aspect **GENERAL** is used to denote it.)
 * e: entity
 * a: aspect
* s: the sentiment about the target
* h: the opinion holder
* t: the time when the opinion was expressed

aspect-based sentiment analysis covers both entities and aspects.

## How

Mainly focuses on the two core tasks:
* Aspect extraction: This task extracts aspects that have been evaluated.
* Aspect sentiment classification: This task determines whether the opinions on different aspects are positive, negative, or neutral. 

**Note**: If the opinion targets are given, we do not need to perform entity or aspect extraction, but only to determine the sentiments on the targets. 

### Aspect Extraction:  information extraction task

* Extraction based on frequent nouns and noun phrases
* Extraction by exploiting opinion and target relations 
* Extraction using supervised learning 
* Extraction using topic modeling

### Aspect sentiment classification

* lexicon-based approach
  * Mark **sentiment** words and phrases to 1(positive word) or -1(negative word)
  * Apply sentiment shifters(words and phrases that can change sentiment orientations, like not, never……)
  * Handle but-clauses, like but, not only …… but also.
  * Aggregate opinions
* supervised learning approach

## Eva

Dataset:
* Twitter
 * ATSA
* SemEval14: Restaurant/Laptop Review
 * Restaurant: ATSA、ACSA
 * Laptop: ATSA
* MAMS
 * ATSA
 * ACSA

MAMS的特点是，一个句子中一定包含至少两个Aspect，并且同一个句子中至少有两个Aspect情感极性是不同的。而Restaurant，Laptop和Twitter这三个数据集中，大多数句子只包含一个Aspect或者包含多个相同情感的Aspect，这样会造成基于方面的情感分析任务退化成句子级别的情感分析任务。

## Others

Targeted Aspect Based Sentiment Analysis

