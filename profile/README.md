## ChatLean: Simplifying Formal Proof-Generating Models with ChatGPT and Basic Searching Techniques

**ChatLean** includes the codes from **"[Simplifying Formal Proof-Generating Models with ChatGPT and Basic Searching Techniques](https://link.springer.com/chapter/10.1007/978-3-031-92605-1_14)"**.
Our research focuses on automated theorem proving (ATP) using simple search algorithms and large language models (LLM).

This project is comprised of three repositories (`b-search`, `d-search`, `AMC12_2023_Lean`), containing the following details:

- **`b-search`**: the execution code and experimental results for a model utilizing our `b-search' proof search algorithm, based on the breadth-first search algorithm
- **`d-search`**: the execution code and experimental results for a model utilizing our `d-search' proof search algorithm, based on the depth-first search algorithm
- **`AMC12_2023_Lean`**: the dataset containing the 2023 AMC12 problems, formalized in Lean.

For a more detailed description, please refer to our paper: **[Paper Link](https://arxiv.org/pdf/2502.03321)**.

<!--
**ChatLean**은 **"[ChatLean: Simplifying Formal Proof-Generating Models with ChatGPT](Link)"** 에서 실험하고 있는 코드를 포함하고 있습니다.  
우리 연구는 간단한 검색 알고리즘(search algorithms)과 Large Language Model(LLM)을 활용하여 자동 정리 증명(automated theorem proving)을 다루고 있습니다.

본 프로젝트는 세 개의 저장소(`b-search`, `d-search`, `AMC12_2023_Lean`)로 구성되어 있으며, 각 저장소에는 다음과 같은 내용을 포함하고 있습니다:  

- **`b-search`**: breadth-first search 기반 증명 검색 모델의 실행 코드 및 실험 결과  
- **`d-search`**: depth-first search 기반 증명 검색 모델의 실행 코드 및 실험 결과  
- **`AMC12_2023_Lean`**: 2023년 AMC12 문제들을 Lean 형식으로 formalization한 데이터셋. 

더 자세한 내용은 **[논문 링크](Link)** 를 참고하세요.
For a detailed description, please refer to our paper.
-->

## Result

Here, we present only the main result comparing our model with other state-of-the-art models on the miniF2F dataset.

* Pass@k rates on miniF2F

  Model|Baseline|# of <br />Attempts (k)|# of <br />Tactics (n)|Sample Budget|Pass@k
  :---|:---:|:---:|:---:|:---:|:---:
  PACT|similar to GPT-3|1|8|1 $\times$ 8 $\times$ 512|24.6 \%
  Lean Expert iteration|similar to GPT-3|1|8|1 $\times$ 8 $\times$ 512|29.6 \%
  ReProver|ByT5|1|64|1 $\times$ 64 $\times -$|26.5 \%
  DS-Prover|ByT5|1|$-$|$-$|29.8 \%
  HyperTree||64|48|64 $\times$ 5000|41.0 \%
  Llemma-7b|Code Llama 7b|1|32|1 $\times$ 32 $\times$ 100|26.23 \%
  COPRA <br />(GPT-4 Turbo + retrieval)|GPT-4 Turbo|1|1|1 $\times$ 60|26.64 \%
  COPRA + One-Shot + Informal-One-Shot <br />(GPT-4 Turbo + retrieval + informal proof)|GPT-4 Turbo|1|1|1 $\times$ 100|29.92 \%
  bChatLean|GPT-4 Turbo|1|64|1 $\times$ 64 $\times -$|29.10 \%
  dChatLean|GPT-4 Turbo|50|1|50 $\times$ 1 $\times -$|23.77 \%
  dChatLean+|GPT-4 Turbo|50|1|50 $\times$ 1 $\times -$|25.00 \%
  bChatLean & dChatLean+|GPT-4 Turbo|1 & 50|64 & 1|(1 $\times$ 64 $\times -$)<br />+(50 $\times$ 1 $\times -$)|31.15 \%

* Below are the results of applying our search methods to other models or datasets.

  <details>
    <summary> Our search methods with Llemma on miniF2F </summary>
      
    |Model|Pass rate
    |:---:|:---:
    |Llemma|26.23 \%
    |bLlemLean|26.64 \%
    |dLlemLean|22.54 \%
    |dLlemLean+|21.31 \%
    |bLlemLean & dLlemLean|27.46 \%
    |bLlemLean & dLlemLean+|28.28 \%
    
  </details>
  
  <details>
    <summary> Pass rates of bChatLean & dChatLean+ on ProofNet by topic </summary>
      
    |Topic|Theorems|Proved|Pass rate
    |:---:|:---:|:---:|:---:
    |Analysis|88|14|15.91 \%
    |Abstract Algebra|162|21|12.96 \%
    |Linear Algebra|28|3|10.71 \%
    |Topology|60|6|10.00 \%
    |Examinations|12|2|16.67 \%
    |Total|350|46|13.14 \%
    
  </details>

* Additional ablation studies from our paper are available in the repository, organized by search method.

