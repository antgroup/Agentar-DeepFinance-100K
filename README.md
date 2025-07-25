<div align="center">

# Agentar-DeepFinance-100K

<div>
A Large-Scale Financial Dataset via Systematic Chain-of-Thought Synthesis Optimization
</div>
</div>

<div>
<br>

<div align="center">

[![Data](https://img.shields.io/badge/Data-4d5eff?style=for-the-badge&logo=huggingface&logoColor=ffffff&labelColor)](https://huggingface.co/datasets/zwhe99/DeepMath-103K)
[![GitHub Stars](https://img.shields.io/github/stars/zwhe99/DeepMath?style=for-the-badge&logo=github&logoColor=white&label=Stars&color=000000)](https://github.com/zwhe99/DeepMath)
[![arXiv](https://img.shields.io/badge/arXiv-2504.11456-b31b1b.svg?style=for-the-badge)](https://arxiv.org/abs/2504.11456)
</div>

</div>

<div align="center">

[**中文**](README_zh.md) | **EN**

</div>


## :fire: ​News

- **2025.7.25** Agentar-DeepFinance-100K open source release! The 15K Financial Safety and Compliance (FinCAS) Dataset has not been relased due to the presence of toxic text 🔥🔥🔥
- **2025.7.12** Our technical report "Agentar-DeepFinance-100K: A Large-Scale Financial Dataset via Systematic Chain-of-Thought Synthesis Optimization" has been released 🚀🚀🚀



## :book: Introduction

![简介](.assets/intro.png)

Recent advancements in large language models (LLMs) have demonstrated remarkable general reasoning capabilities, holding significant potential for applications in the financial domain, a field that requires robust and reliable reasoning. It has been demonstrated that distilling high-quality chain-of-thought (CoT) rationales from advanced general reasoning models offers a promising and efficient path to the financial reasoning model. However, existing CoT synthesis methods suffer from shallow CoT sampling, leaving the question of how to construct a well-designed knowledge space for finance reasoning unexplored. To this end, we make the following improvements:


**(1) Comprehensive CoT Synthesis Pipeline:** Beginning with the curated seed corpora, our methodology integrates the Multi-perspective Knowledge Extraction (MKE) strategy and the Self-Corrective Rewriting (SCR) mechanism for CoT sampling. On the one hand, this pipeline demonstrates enhanced capabilities in extracting exhaustive domain knowledge for financial reasoning. On the other hand, it enables the sampling of more complex and challenging questions, leading to more intricate reasoning trajectories.

**(2) "CoT Cube" Systematic Investigation:** We conducted a systematic investigation regarding critical factors influencing CoT effectiveness, including necessity, length, and synthesizers. It provides guidance for constructing high-quality financial CoTs.

**(3) Industry-expert Annotated Scenario QA:** To bridge the gap with real-world user interactions, we systematically synthesized industry scenario questions that reflect the financial capabilities required in practical settings, with annotations provided by domain experts.

Building on these systematic synthesis optimizations, we publicly release AntDT-DeepFinance-300K, hoping to advance the research in financial reasoning models.


## :rocket: Comprehensive CoT Synthesis Pipeline

![pipeline](.assets/framework.png)

**1. Multi-Perspective Knowledge Extraction：** This method aims to achieve comprehensive and exhaustive financial reasoning knowledge modeling:

- `Q2A (Direct Curation)`: Directly extract well-structured question-answer pairs from the seed corpus.
- `A2Q (Counterfactual Augmentation)`: Enhance the causal connectivity of key knowledge points through counterfactual perturbations.
- `T2Q (CoT Knowledge Mining)`: Mine implicit reasoning dependencies within CoTs.

**2. Self-Corrective Rewriting：** A common practice in existing methodologies is to discard QA pairs that lack correctly sampled answers, thereby ensuring the overall accuracy of the dataset. However, these discarded QA pairs often involve intricate reasoning processes, which could serve as valuable resources for enhancing model capabilities. We introduce Self-Corrective Rewriting (SCR) to transform flawed reasoning trajectories into effective learning opportunities through appropriate correction mechanisms.

![ablation](.assets/ablation.png)

## 🛠️ “CoT Cube” Systematic Investigation

**1. CoT Necessity**：Incorporating CoT consistently improves model performance regardless of task type and difficulty, particularly in complex reasoning tasks (e.g., math) and difficult problems.

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


**2. CoT Synthesizer：** The effectiveness of a reasoning model as a CoT synthesizer does not always align with its intrinsic reasoning performance.

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

**3. CoT Length：** Distilling CoTs with reduced length allows the trained model to provide more concise responses, but may also hurt performance. Financial reasoning requires long CoTs.

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

## 🙏 Acknowledgements

This work can not be done without the help of the following works:

- **Public Dataset**: [FinCorpus](https://huggingface.co/datasets/Duxiaoman-DI/FinCorpus), [Finance-Instruct-500K](https://huggingface.co/datasets/Josephgflowers/Finance-Instruct-500k), [FinCUGE](https://huggingface.co/datasets/Maciel/FinCUGE-Instruction), [FinQA](https://arxiv.org/abs/2109.00122), [FinancialData](https://huggingface.co/datasets/csujeong/financial_data), [Quant-Trading-Instruct](https://huggingface.co/datasets/lumalik/Quant-Trading-Instruct)


## 📚 Citation

```
@article{zhao2025agentar,
  title={Agentar-DeepFinance-300K: A Large-Scale Financial Dataset via Systematic Chain-of-Thought Synthesis Optimization},
  author={Zhao, Xiaoke and Zhou, Zhaowen and Chen, Lin and Wang, Lihong and Huang, Zhiyi and Zheng, Kaiyuan and Zheng, Yanjun and Du, Xiyang and Liao, Longfei and Liu, Jiawei and others},
  journal={arXiv preprint arXiv:2507.12901},
  year={2025}
}
```

## 🤝 Contact Us

非常感谢您对通义点金系列的关注！如果您有兴趣向我们的研究团队或产品团队留言，欢迎通过我们的官方邮箱或者扫码加入钉群与我们联系：[CFLUE@alibabacloud.com](mailto:CFLUE@alibabacloud.com)。我们的团队将竭诚为您提供帮助和支持。

