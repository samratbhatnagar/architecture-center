---
title: Choosing a natural language processing technology
description:
author: zoinerTejada
ms.date: 02/12/2018
ms.topic: guide
ms.service: architecture-center
ms.subservice: cloud-fundamentals
---

# Choosing a natural language processing technology in Azure

Free-form text processing is performed against documents containing paragraphs of text, typically for the purpose of supporting search, but is also used to perform other natural language processing (NLP) tasks such as sentiment analysis, topic detection, language detection, key phrase extraction, and document categorization. This article focuses on the technology choices that act in support of the NLP tasks.

<!-- markdownlint-disable MD026 -->

## What are your options when choosing an NLP service?

<!-- markdownlint-enable MD026 -->

In Azure, the following services provide natural language processing (NLP) capabilities:

- [Azure Machine Learning service](/azure/machine-learning/service)
- [Azure Databricks](/azure/azure-databricks/what-is-azure-databricks)
- [Azure HDInsight](/azure/hdinsight/spark/apache-spark-overview)
- [Microsoft Cognitive Services](/azure/cognitive-services/welcome)

## Key selection criteria

To narrow the choices, start by answering these questions:

- Do you want to use prebuilt models? If yes, consider using the APIs offered by Microsoft Cognitive Services.

- Do you need to train custom models against a large corpus of text data? If yes, consider using Azure Databricks or the Azure Machine Learning service.

- Do you need low-level NLP capabilities like tokenization, stemming, lemmatization, and term frequency/inverse document frequency (TF/IDF)? If yes, consider using Azure Databricks or Azure Machine Learning service.

- Do you need simple, high-level NLP capabilities like entity and intent identification, topic detection, spell check, or sentiment analysis? If yes, consider using the APIs offered by Microsoft Cognitive Services.

## Capability matrix

The following tables summarize the key differences in capabilities.

### General capabilities

|                                                         |  Azure Databricks / Azure HDInsight  |  Azure Machine Learning service  | Microsoft Cognitive Services         |
| ------------------------------------------------------- | ---------------------------------- | ---------------------------------- | ------------------------------------ |
| Provides pretrained models as a service                 | No                                 | No                                 | Yes                                  |
| REST API                                                | Yes                                | Yes                                | Yes                                  |
| Programmability                                         | Python, Scala, Java, R             | Python, Scala, Java, R             | C#, Java, Node.js, Python, PHP, Ruby |
| Support processing of big data sets and large documents | Yes                                | Yes                                | No                                   |

### Low-level natural language processing capabilities

|                                                    | Azure Databricks / Azure HDInsight | Azure Machine Learning service | Microsoft Cognitive Services  |
| -------------------------------------------------- | ---------------------------------- | ---------------------------------- | ----------------------------- |
| Tokenizer                                          | Yes                     | Yes                     | Yes (Linguistic Analysis API) |
| Stemmer                                            | Yes                     | Yes                     | No                            |
| Lemmatizer                                         | Yes                     | Yes                     | No                            |
| Part of speech tagging                             | Yes                     | Yes                     | Yes (Linguistic Analysis API) |
| Term frequency/inverse-document frequency (TF/IDF) | Yes                     | Yes                     | No                            |
| String similarity&mdash;edit distance calculation  | Yes                     | Yes                     | No                            |
| N-gram calculation                                 | Yes                     | Yes                     | No                            |
| Stop word removal                                  | Yes                     | Yes                     | No                            |

### High-level natural language processing capabilities

|                                             | Azure Databricks / Azure HDInsight | Azure Machine Learning service | Microsoft Cognitive Services                                |
| ------------------------------------------- | ---------------------------------- | ----------------------------------------------------------- |
| Entity/intent identification and extraction | No                                 | No                                 | Yes (Language Understanding Intelligent Service (LUIS) API) |
| Topic detection                             | Yes                                | Yes                                | Yes (Text Analytics API)                                    |
| Spell checking                              | Yes                                | Yes                                | Yes (Bing Spell Check API)                                  |
| Sentiment analysis                          | Yes                                | Yes                                | Yes (Text Analytics API)                                    |
| Language detection                          | No                                 | No                                 | Yes (Text Analytics API)                                    |
| Supports multiple languages besides English | No                                 | No                                 | Yes (varies by API)                                         |

## See also

[Natural language processing](../scenarios/natural-language-processing.md)
