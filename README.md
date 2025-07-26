<div align="center">

# Agentar-DeepFinance-100K

<div>
</div>

</div>
<div align="center">
  <h3>A · large-scale · in-depth financial industry · CoT dataset</h3>
</div>
<div>
<br>

<div align="center">

[![License](https://img.shields.io/badge/License-Apache_2.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)

[![Data](https://img.shields.io/badge/Data-4d5eff?style=for-the-badge&logo=huggingface&logoColor=ffffff&labelColor)](https://huggingface.co/datasets/inclusionAI/Agentar-DeepFinance-100K)
[![arXiv](https://img.shields.io/badge/arXiv-2507.12901-b31b1b.svg?style=for-the-badge)](https://arxiv.org/abs/2507.12901)
</div>

</div>

<div align="center">

**中文** | [**EN**](README.md)

</div>

![全面的CoT合成流程](.assets/framework.png)

Currently, **high-quality financial Chain of Thought (CoT)** represents an efficient and feasible pathway to building specialized reasoning models for the financial domain. However, mainstream CoT synthesis methods often remain at a shallow sampling stage, failing to systematically explore how to construct an effective and in-depth financial reasoning knowledge system. This limitation creates bottlenecks in improving data quality and reasoning depth. To address this issue, we have designed a systematic optimization framework for CoT synthesis tailored to the complex demands of financial reasoning. This approach deeply mines CoT by focusing on three core dimensions, culminating in the creation of **Agentar-DeepFinance-100K**:

**(1) Deep CoT → Knowledge Expansion**: By introducing **Multi-perspective Knowledge Extraction (MKE)**, we leverage counterfactual augmentation strategies to generate more diverse and in-depth financial reasoning chains from multiple layers of content, including questions, thought processes, and final answers. The augmented data better reflects the complex dynamics of real-world financial problems, creating reasoning trajectories that **cover a wide range of scenarios**, ensuring relevance across various use cases.

**(2) Deeper CoT → Knowledge Extraction**: We conduct a **multidimensional analysis of the key factors influencing CoT quality**, including the necessity of CoT, the appropriate length of reasoning chains, and the optimal design of synthesizers. Through precise identification and evaluation of these elements, we establish a theoretical foundation for designing high-quality financial CoT datasets. Additionally, we provide **a set of guiding principles** to inform the generation of even more robust reasoning chains.

**(3) Deeply Integrated CoT → Human-AI Collaborative Validation**: To meet the high-precision requirements of real-world financial applications, we incorporate a validation process **combining human expert verification with Self-corrective and Rewriting (SCR) technology**. For challenging cases where synthesis fails, we integrate model-driven self-corrective with domain expert annotations and validations. This collaborative human-AI labeling approach significantly **enhances the success rate and accuracy of CoT synthesis**, aligning it more closely with practical business needs.

Through this optimized workflow, we have constructed **Agentar-DeepFinance-100K**, a high-quality, large-scale dataset for financial reasoning research and applications. By refining data synthesis and validation logic, this dataset **aims to advance technological exploration in financial reasoning** and empower **efficient, secure, and professional** financial AI applications. Our research not only introduces **methodological innovations** for generating financial reasoning chains but also lays a solid foundation for applying large language models in advanced financial reasoning tasks. It provides critical insights for **developing financial agents with enhanced precision and capabilities**.

## 💎 Why Does Agentar-DeepFinance-100K Have Industry-Wide Value?

- **CoT Data with Depth and Precision** 

  By leveraging **Multi-perspective Knowledge Extraction and Self-corrective techniques**, Agentar-DeepFinance-100K generates **high-quality, deeply layered** reasoning data. The depth of this data effectively enhances the model's reasoning and decision-making capabilities in complex financial scenarios, accommodating diverse institutional needs—from advanced financial computations to compliance analysis.

- **Alignment with Real-World Scenarios**

  The dataset is **meticulously annotated and calibrated by domain experts**, ensuring it is closely aligned with actual business environments. This **"scenario alignment"** design approach not only increases the dataset's applicability in real-world use cases but also significantly reduces the "scenario adaptation costs" associated with deploying intelligent systems in financial institutions, enabling seamless transitions from research results to practical implementation.

- **Universality and Standardization of Methodology**

  During the multidimensional CoT knowledge extraction process, key factors such as **reasoning necessity, text length, and synthesizer** design were rigorously tested. This led to the development of **a reusable "High-Quality CoT Evaluation Framework"**. The framework not only provides theoretical support for constructing the dataset but also offers methodological guidance for financial institutions to independently optimize and expand their context-specific datasets, thereby driving the development of industry-wide technical standards.

- **Fostering End-to-End Intelligent Agent Capabilities**

  The dataset includes financial CoTs that **span critical task modules such as financial analysis and interpretation, financial mathematics, and compliance and security**. These modular reasoning processes lay a solid foundation for **training end-to-end intelligent agents** capable of supporting the full spectrum of financial operations, addressing the long-term pursuit of multi-task, multi-step intelligent solutions by financial institutions.

The value of Agentar-DeepFinance-100K lies not only in its outstanding data quality but also in its ability to **systematically address** longstanding industry challenges, such as **"scenario misalignment, insufficient reasoning capabilities, and inconsistent data quality."** By offering **reusable, scalable, and trustworthy** foundational capabilities, it paves the way for the large-scale deployment of financial intelligent systems, serving as a crucial cornerstone for driving the industry's intelligent transformation.

## 💻 Who Should Use Agentar-DeepFinance-100K?

This dataset is suitable for:

- **Financial Intelligent Agent Development Teams**: Validate and enhance model reasoning capabilities in complex financial scenarios, optimize deep reasoning in the financial domain, and leverage high-quality CoT datasets to improve problem-solving abilities, meeting diverse business needs.

- **Financial Institution Technical Teams**: Reduce the adaptation costs of intelligent agents, quickly implement applications using real-world business data, and expand institution-specific CoT datasets through standardized methods, enabling technological self-optimization.

- **Academic Researchers**: Access real-world data on multidimensional financial reasoning and regulatory safety, build high-trust evaluation environments, and drive cutting-edge advancements and industry standardization.

## 🛠️ "CoT Cube" Systematic Experiments

**1. CoT Necessity Experiment**: Regardless of task type and difficulty, incorporating CoT consistently enhances model performance, especially in complex reasoning tasks and challenging problems.

| CoT          | Text Gen. | Analysis & Interp. | NLP   | Compliance & Sec. | Math  | Knowledge QA | Average |
|--------------|-----------|---------------------|-------|-------------------|-------|--------------|---------|
| w/o          | 74.55     | 81.36              | 76.71 | 91.25             | 31.71 | 78.32        | 72.32   |
| w/-         | **83.64**| **88.05**          | **77.21** | **92.02**     | **61.15** | **79.01** | **80.18** |

<table>
    <tr>
        <th>Method</th>
        <th>CoT</th>
        <th>FinQA</th>
        <th>Fin-Eva</th>
    </tr>
    <tr>
        <td>Qwen2.5-7B-Instruct</td>
        <td align="center">-</td>
        <td>63.47</td>
        <td>83.70</td>
    </tr>
    <tr>
        <td rowspan="2">Simple</td>
        <td>w/o CoT</td>
        <td>67.65</td>
        <td>84.21</td>
    </tr>
    <tr>
        <td>w/- CoT</td>
        <td><b>68.96</b></td>
        <td><b>85.01</b></td>
    </tr>
    <tr>
        <td rowspan="2">Hard</td>
        <td>w/o CoT</td>
        <td>63.03</td>
        <td>75.80</td>
    </tr>
    <tr>
        <td>w/- CoT</td>
        <td><b>69.31</b></td>
        <td><b>85.96</b></td>
    </tr>
</table>


**2. CoT Synthesizer Experiment**: The effectiveness of reasoning models as CoT synthesizers does not always align with their inherent reasoning performance. In our experiments, the CoT quality distilled from QwQ-Plus surpasses that distilled from DeepSeek-R1.

<table>
  <thead>
    <tr>
      <th rowspan="2">Model</th>
      <th rowspan="2">Dense</th>
      <th colspan="2">Fin-Eva</th>
      <th colspan="2">FinQA</th>
      <th colspan="2">General</th>
    </tr>
    <tr>
      <th>Acc</th>
      <th>Res. Length</th>
      <th>Acc</th>
      <th>Res. Length</th>
      <th>MATH</th>
      <th>GPQA</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>DeepSeek-R1</td>
      <td>❌</td>
      <td><b>91.42</b></td>
      <td><b>770.14</b></td>
      <td><b>75.41</b></td>
      <td>675.46</td>
      <td><b>98.20</b></td>
      <td>61.62</td>
    </tr>
    <tr>
      <td>QwQ-Plus</td>
      <td>✅</td>
      <td>90.99</td>
      <td>627.43</td>
      <td>72.97</td>
      <td><b>1831.49</b></td>
      <td>97.20</td>
      <td>54.55</td>
    </tr>
    <tr>
      <td>Qwen3-235B-A22B</td>
      <td>❌</td>
      <td>90.01</td>
      <td>428.54</td>
      <td>74.54</td>
      <td>1302.86</td>
      <td>94.60</td>
      <td><b>62.12</b></td>
    </tr>
    <tr>
      <td>Qwen2.5-7B-Instruct</td>
      <td>✅</td>
      <td>83.70</td>
      <td>1.00</td>
      <td>63.47</td>
      <td>239.97</td>
      <td>73.20</td>
      <td>37.88</td>
    </tr>
    <tr>
      <td colspan="8"></td>
    </tr>
    <tr>
      <th rowspan="2">Teacher Model</th>
      <th rowspan="2">#Samples/Avg. Length</th>
      <th colspan="2">Fin-Eva</th>
      <th colspan="2">FinQA</th>
      <th colspan="2">General</th>
    </tr>
    <tr>
      <th>Acc</th>
      <th>Res. Length</th>
      <th>Acc</th>
      <th>Res. Length</th>
      <th>MATH</th>
      <th>GPQA</th>
    </tr>
    <tr>
      <td>DeepSeek-R1</td>
      <td>21,040/1564.63</td>
      <td>85.32</td>
      <td><b>754.54</b></td>
      <td>66.52</td>
      <td>1270.96</td>
      <td>80.00</td>
      <td>41.41</td>
    </tr>
    <tr>
      <td>QwQ-Plus</td>
      <td>19,323/1795.99</td>
      <td><b>85.53</b></td>
      <td>702.41</td>
      <td><b>68.79</b></td>
      <td><b>2196.81</b></td>
      <td><b>81.60</b></td>
      <td><b>42.42</b></td>
    </tr>
    <tr>
      <td>Qwen3-235B-A22B</td>
      <td>20,322/1522.92</td>
      <td>85.45</td>
      <td>640.81</td>
      <td>66.43</td>
      <td>1469.85</td>
      <td>80.00</td>
      <td><b>42.42</b></td>
    </tr>
  </tbody>
</table>

**3. CoT Length Experiment**: Refining and shortening CoT can lead to more concise responses from the trained model but may compromise reasoning capabilities. Financial reasoning models require longer CoT for optimal performance.


<table>
  <thead>
    <tr>
      <th rowspan="2">CoT Length</th>
      <th rowspan="2">Avg. Length</th>
      <th colspan="2">Fin-Eva</th>
      <th colspan="2">FinQA</th>
    </tr>
    <tr>
      <th>Acc</th>
      <th>Res. Length</th>
      <th>Acc</th>
      <th>Res. Length</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Long</td>
      <td>1352.16</td>
      <td><b>85.53</b></td>
      <td>702.41</td>
      <td><b>68.79</b></td>
      <td><b>2196.81</b></td>
    </tr>
    <tr>
      <td>Medium</td>
      <td>1248.42</td>
      <td>85.40</td>
      <td><b>742.90</b></td>
      <td>65.13</td>
      <td>1698.63</td>
    </tr>
    <tr>
      <td>Short</td>
      <td>1020.26</td>
      <td>85.19</td>
      <td>574.00</td>
      <td>65.56</td>
      <td>1587.76</td>
    </tr>
  </tbody>
</table>

## 🔥 ​Latest Updates

- **2025.7.25**  **The Agentar-DeepFinance-100K dataset** has been open-sourced. However, the 1K FinRA (FinRA: financial real annotations) high-quality synthetic fine-annotated data , counterfactual synthetic data, and self-corrective rewritten data will be disclosed later due to compliance review reasons. Additionally, the 15K FinCAS (FinCAS: financial compliance and security) safety compliance data, which contains toxic text, has not been open-sourced in accordance with standard open-source practices.🔥🔥🔥
- **2025.7.24** **The Finova Financial Evaluation Benchmark** has been released. Finova evaluates models based on three key dimensions most relevant to real-world scenarios: agent task execution capability, complex reasoning ability, and safety compliance. The Agentar-DeepFinance series CoT datasets provide deep support for evaluating complex reasoning and safety compliance capabilities.🚀🚀🚀
- **2025.7.22** The technical report for **Agentar-Fin-R1**, titled **“Agentar-Fin-R1: Enhancing Financial Intelligence through Domain Expertise, Training Efficiency, and Advanced Reasoning”**, has been released. Agentar-Fin-R1 was trained using a subset of the Agentar-DeepFinance series CoT datasets. These datasets have enabled Agentar-Fin-R1 to achieve state-of-the-art performance across all financial evaluation benchmarks—including Fineva, FinEval, FinanceIQ, and Ant Group’s newly proposed Finova. It has surpassed industry-leading open-source financial large models, as well as general-purpose reasoning models of significantly larger scales such as GPT-o1 and DeepSeek-R1. 🚀🚀🚀
- **2025.7.12** The technical report for **Agentar-DeepFinance-100K**, titled **“Agentar-DeepFinance-100K: A Large-Scale Financial Dataset via Systematic Chain-of-Thought Synthesis Optimization”**, has been released. 🚀🚀🚀

## 🙏 Acknowledgments
- **We would like to thank the following public datasets**: [FinCorpus](https://huggingface.co/datasets/Duxiaoman-DI/FinCorpus), [Finance-Instruct-500K](https://huggingface.co/datasets/Josephgflowers/Finance-Instruct-500k), [FinCUGE](https://huggingface.co/datasets/Maciel/FinCUGE-Instruction), [FinQA](https://arxiv.org/abs/2109.00122), [FinancialData](https://huggingface.co/datasets/csujeong/financial_data), [Quant-Trading-Instruct](https://huggingface.co/datasets/lumalik/Quant-Trading-Instruct)

- **We would like to thank Changsha Digital Tianma Information Technology Co., Ltd. and Digital Tianma (Chongqing) Information Technology Co., Ltd**. for their efforts in overseeing the operation and management of data annotation. They brought together abundant and highly skilled financial industry expert annotation resources, providing strong support for the construction of high-quality financial data.

## 🔐 Data Desensitization Statement
To comply with financial data security and privacy regulations, the publicly released version of this project has undergone additional data cleansing and anonymization processes. As a result, the training outcomes based on the open-source version may exhibit minor differences from the full-version results published in our technical report.

## 📚 Citation

```
@misc{zhao2025deepfinance,
      title={Agentar-DeepFinance-100K: A Large-Scale Financial Dataset via Systematic Chain-of-Thought Synthesis Optimization}, 
      author={Xiaoke Zhao and Zhaowen Zhou and Lin Chen and Lihong Wang and Zhiyi Huang and Kaiyuan Zheng and Yanjun Zheng and Xiyang Du and Longfei Liao and Jiawei Liu and Xiang Qi and Bo Zhang and Peng Zhang and Wei Wang and Zhe Li},
      year={2025},
      eprint={2507.12901},
      archivePrefix={arXiv},
      primaryClass={cs.CE},
      url={https://arxiv.org/abs/2507.12901}, 
}
```

## 🤝 Contact Us

Thank you very much for your interest in the Agentar series! If you would like to leave a message for our research or product team, or if you are interested in collaborating with us to build a high-quality financial CoT dataset, feel free to reach out to us via our official email: [yanchang.zxk@antgroup.com]. Our team is dedicated to providing you with assistance and support.

