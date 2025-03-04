# Babel - Open Multilingual Large Language Models Serving Over 90% of Global Speakers

## Authors

[Yiran Zhao](https://zhaoyiran924.github.io/) | [Chaoqun Liu](https://www.linkedin.com/in/chaoqun-liu/) | [Yue Deng](https://ntudy.github.io/) | [Jiahao Ying](https://yingjiahao14.github.io/) | Mahani Aljunied | [Zhaodonghui Li](https://mlxdb.github.io/author/li-zhaodonghui/) | [Lidong Bing](https://lidongbing.github.io/research.html/) | [Hou Pong Chan](https://kenchan0226.github.io/) | [Yu Rong](https://royrong.me/) | [Deli Zhao](https://zhaodeli.github.io/) | [Wenxuan Zhang*](https://isakzhang.github.io)  (Corresponding Author)

## Links

- 📄 [Paper](https://github.com/babel-llm/babel-llm/blob/main/paper/babel.pdf)
- 💻 [GitHub Repository](https://github.com/babel-llm/babel-llm)
- 🤗 [Hugging Face Models](https://huggingface.co/Tower-Babel)

---

## Introduction

> *People built the **Tower of Babel** to reach heaven and achieve unity,  
> but God confused their language and scattered them across the earth.*  
> — *Story from Genesis, Old Testament*

## Abstract

Large language models (LLMs) have transformed natural language processing (NLP), yet open-source multilingual LLMs remain scarce, with existing models often limited in language coverage.  

To address this disparity, we introduce **Babel**, a multilingual LLM that covers the top 25 languages by number of speakers, supports over 90% of the global population, and includes many languages neglected by other open multilingual LLMs.

Unlike traditional continue pretraining approaches, Babel expands its parameter count through a layer extension technique that elevates Babel's performance ceiling. We introduce two variants:

- **Babel-9B**: Designed for efficient inference and fine-tuning.
- **Babel-83B**: Sets a new standard for open multilingual LLMs.

Extensive evaluations on multilingual tasks demonstrate its superior performance compared to open LLMs of comparable size. Using existing supervised fine-tuning datasets, Babel achieves remarkable performance, with Babel-9B-Chat leading among 10B-sized LLMs and Babel-83B-Chat setting a new standard for open LLMs, performing comparably to GPT-4o on certain tasks.

---

## Supported Languages

The following table lists the languages supported by Babel, sorted by the number of speakers. Highlighted languages are those underexplored by previous multilingual LLMs.

| Language               | Speakers | Language Family       | Macroarea                |
| ---------------------- | -------- | --------------------- | ------------------------ |
| English                | 1.5B     | Germanic              | Worldwide                |
| Chinese (Mandarin)     | 1.4B     | Sinitic               | Asia                     |
| **Hindi**              | **700M** | **Indo-Aryan**        | **Asia**                 |
| Spanish                | 595M     | Romance               | Americas, Europe         |
| Standard Arabic        | 400M     | Semitic               | Asia, Africa             |
| French                 | 300M     | Romance               | Europe, Africa, Americas |
| **Bengali**            | 3**00M** | **Indo-Aryan**        | **Asia**                 |
| Portuguese             | 270M     | Romance               | Americas, Europe, Africa |
| Russian                | 260M     | Slavic                | Europe, Asia             |
| **Urdu**               | **230M** | **Indo-Aryan**        | **Asia**                 |
| **Indonesian**         | **200M** | **Malayo-Polynesian** | **Asia**                 |
| Standard German        | 135M     | Germanic              | Europe                   |
| Japanese               | 130M     | Japonic               | Asia                     |
| **Swahili**            | **100M** | **Bantu**             | **Africa**               |
| **Filipino (Tagalog)** | **100M** | **Malayo-Polynesian** | **Asia**                 |
| **Tamil**              | **90M**  | **Dravidian**         | **Asia**                 |
| **Vietnamese**         | **86M**  | **Vietic**            | **Asia**                 |
| Turkish                | 85M      | Turkic                | Asia, Europe             |
| Italian                | 85M      | Romance               | Europe                   |
| **Javanese**           | 83M      | **Malayo-Polynesian** | **Asia**                 |
| Korean                 | 80M      | Koreanic              | Asia                     |
| **Hausa**              | 80M      | Chadic                | Africa                   |
| **Iranian Persian**    | 80M      | **Indo-Iranian**      | **Asia**                 |
| **Thai**               | **80M**  | **Kra-Dai**           | **Asia**                 |
| **Burmese**            | **50M**  | **Tibeto-Burman**     | **Asia**                 |

---

## Multilingual Capability

We evaluate Babel using diverse multilingual tasks:

1. **World Knowledge**: MMMLU, M3Exam (authentic human exam questions).
2. **Reasoning**: MGSM, XCOPA.
3. **Understanding**: XNLI.
4. **Translation**: Flores-200.

### Performance of 10B-Size Base Models vs. Babel-9B-Base

| Dataset     | GLM4-9B | Gemma2-9B | Mistral-12B | Llama3.1-8B | Qwen2.5-7B | **Babel-9B** |
| ----------- | ------- | --------- | ----------- | ----------- | ---------- | ------------ |
| MMMLU       | 55.6    | **59.8**  | 52.8        | 49.4        | 56.7       | 59.4         |
| M3Exam      | 56.6    | **61.6**  | 54.2        | 52.5        | 58.8       | 61.3         |
| XCOPA       | 87.3    | 84.6      | 81.3        | 75.9        | 81.1       | **89.2**     |
| MGSM        | 39.0    | 34.3      | 26.0        | 18.0        | 41.1       | **43.4**     |
| XNLI        | 69.9    | 61.7      | 55.0        | 48.9        | 70.3       | **71.9**     |
| Flores-200  | 46.6    | 53.2      | 50.8        | 50.9        | 45.5       | **55.1**     |
| **Average** | 59.2    | 59.5      | 53.4        | 49.3        | 58.9       | **63.4**     |

### Performance of Open Large Multilingual LLMs vs. Babel-83B-Base

| Dataset     | Llama3.1-70B | Qwen2.5-72B | **Babel-83B** |
| ----------- | ------------ | ----------- | ------------- |
| MMMLU       | 69.1         | 74.7        | **76.3**      |
| M3Exam      | 67.4         | 71.2        | **72.1**      |
| XCOPA       | 92.6         | 81.1        | **92.8**      |
| MGSM        | 48.9         | **63.9**    | 62.6          |
| XNLI        | 66.2         | 74.9        | **76.6**      |
| Flores-200  | 57.4         | 53.1        | **58.8**      |
| **Average** | 66.9         | 69.8        | **73.2**      |

---

## Acknowledgements

We thank Guanzheng Chen for assisting with the training codebase. Special thanks to Tantong Champaiboon, Nguyen Ngoc Yen Nhi, and Tara Devina Putri for their contributions to dataset evaluation and fact-checking. Additional thanks to Fan Wang, Jiasheng Tang, Xin Li, and Hao Zhang for coordinating computing resources.

---

## Citation

If you find our project useful, please cite it using:

```bibtex
@misc{zhao2025babelopenmultilinguallarge,
      title={Babel: Open Multilingual Large Language Models Serving Over 90% of Global Speakers}, 
      author={Yiran Zhao and Chaoqun Liu and Yue Deng and Jiahao Ying and Mahani Aljunied and Zhaodonghui Li and Lidong Bing and Hou Pong Chan and Yu Rong and Deli Zhao and Wenxuan Zhang},
      year={2025},
      eprint={2503.00865},
      archivePrefix={arXiv},
      primaryClass={cs.CL},
      url={https://arxiv.org/abs/2503.00865}, 
}

```
