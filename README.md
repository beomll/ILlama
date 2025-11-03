# 🩺 ILlama
> *Leveraging Knowledge Graph-Enhanced LLMs for Context-Aware Medical Consultation* (EMNLP 2025).  
> A novel RAG framework leveraging structured medical knowledge via subgraphs for context-aware, hallucination-reduced medical consultations.

---

## 🗝️ Key feature
- ✅ **Reliable Medical Facts**: Reduces errors with clear causal relationships.
- 🔎 **Accurate Retrieval**: Uses granular knowledge and vector search for higher precision.
- 💉 **Superior Clinical Utility**: Achieves state-of-the-art performance for reliable and practical medical guidance.

<p align="center">
  <img src="./assets/ILlama.png" width="100%" alt="Framework Overview">
</p>

<p align="center">
  <img src="./assets/data_gen.jpg" width="100%" alt="Data Generation Pipeline">
</p>

---

## 📖 Usage
### Installation
Install dependent Python libraries by running the command below.
```
pip install -r requirements.txt
```

### Quick Start Example
```python
import asycnio
from illama.illama import ILlama

illama = ILlama(
        model_name='Codingchild/ILlama-8b-LoRA',
        retriever_name='Codingchild/medical-bge-large-en-v1.5',
        reranker_name='Codingchild/medical-bge-reranker-large',
    )

async def main():
    # prepare illama model & prompt
    chain = illama.prepare_illama(
        generation_type='w_rag'
    )

    # generate response for user's query
    response = await illama.inference(
        chain=chain,
        query='I have a headache and a fever. What should I do?'
    )

    print(response)

asyncio.run(main())
```

## 📜 Citation
If you find this work helpful, please consider citing us:
```bibtex
@inproceedings{park-etal-2025-leveraging-knowledge,
    title = "Leveraging Knowledge Graph-Enhanced {LLM}s for Context-Aware Medical Consultation",
    author = "Park, Su-Hyeong  and
      Kim, Ho-Beom  and
      Park, Seong-Jin  and
      Aliyeva, Dinara  and
      Kim, Kang-Min",
    editor = "Christodoulopoulos, Christos  and
      Chakraborty, Tanmoy  and
      Rose, Carolyn  and
      Peng, Violet",
    booktitle = "Proceedings of the 2025 Conference on Empirical Methods in Natural Language Processing",
    month = nov,
    year = "2025",
    address = "Suzhou, China",
    publisher = "Association for Computational Linguistics",
    url = "https://aclanthology.org/2025.emnlp-main.1549/",
    pages = "30447--30463",
    ISBN = "979-8-89176-332-6",
    abstract = "Recent advancements in large language models have significantly influenced the field of online medical consultations. However, critical challenges remain, such as the generation of hallucinated information and the integration of up-to-date medical knowledge. To address these issues, we propose **I**nformatics **Llama** (ILlama), a novel framework that combines retrieval-augmented generation with a structured medical knowledge graph. ILlama incorporates relevant medical knowledge by transforming subgraphs from a structured medical knowledge graph into text for retrieval-augmented generation. By generating subgraphs from the medical knowledge graph in advance, specifically focusing on diseases and symptoms, ILlama is able to enhance the accuracy and relevance of its medical reasoning. This framework enables effective incorporation of causal relationships between symptoms and diseases. Also, it delivers context-aware consultations aligned with user queries. Experimental results on the two medical consultation datasets demonstrate that ILlama outperforms the strong baselines, achieving a semantic similarity F1-score of 0.884 when compared with ground truth consultation answers. Furthermore, qualitative analysis of ILlama{'}s responses reveals significant improvements in hallucination reduction and clinical usefulness. These results suggest that ILlama has strong potential as a reliable tool for real-world medical consultation environments."
}
```

## 📬 Contact
Email: pshpulip22@catholic.ac.kr
