<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:8E2DE2,100:4A00E0&height=200&section=header&text=NeuraMap&fontSize=42&fontColor=ffffff&animation=fadeIn&fontAlignY=38&desc=From%20raw%20data%20to%20deployed%20intelligence&descAlignY=58&descSize=16" width="100%"/>

![Python](https://img.shields.io/badge/Python-3.11-4A00E0?style=for-the-badge&logo=python&logoColor=white)
![Status](https://img.shields.io/badge/Status-Reference%20Map-8E2DE2?style=for-the-badge)
![Made%20with](https://img.shields.io/badge/Made%20with-%E2%9C%A8-black?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-informational?style=for-the-badge)


**Deep dive:** [Machine Learning Workflow](https://github.com/proindra/ML-WorkFlow/blob/main/MachineLearningWorkFlow.md)
**&** [Deep Learning Workflow](https://github.com/proindra/ML-WorkFlow/blob/main/DeepLearningWorkFlow.md)
**Evaluation:** [ML Model Evaluation](https://github.com/proindra/ML-WorkFlow/blob/main/MLModelEvaluation.md)
**Transforms:** [Attention Mechanism](https://erdem.pl/2021/05/introduction-to-attention-mechanism)

</div>
<br/>

## 🗺️ The Pipeline
```mermaid
flowchart TD
    A(["📊 DATA"]) --> STR["Structured Data\n(tables, numbers)"]
    A --> UNS["Unstructured Data\n(text, documents, speech)"]

    %% ======================= STRUCTURED DATA PATH =======================
    STR --> B["1. Data Collection"]
    B --> C["2. Data Preparation"]

    subgraph PREP[" "]
        direction LR
        C1["Data Cleaning"]
        C2["Missing Values"]
        C3["Duplicates"]
        C4["Data Transformation"]
    end
    C --> PREP

    PREP --> D["3. EDA — Exploratory Data Analysis"]

    subgraph EDA[" "]
        direction LR
        D1["Statistics"]
        D2["Visualization"]
        D3["Correlation"]
        D4["Outlier Analysis"]
    end
    D --> EDA

    EDA --> E["4. Feature Engineering"]

    subgraph FE[" "]
        direction LR
        E1["Feature Selection"]
        E2["Feature Creation"]
        E3["Encoding / Scaling"]
    end
    E --> FE

    FE --> F["5. Choose ML | DL Model"]

    F --> G["6. Model Training"]
    G --> H["7. Model Evaluation"]

    H --> I["8. Hyperparameter Tuning"]
    I --> J["9. Prediction"]
    J --> K["10. Deployment & Monitoring"]

    %% ======================= UNSTRUCTURED DATA / NLP PATH =======================
    UNS --> NLP["NLP"]

    NLP --> TPREP["Text Preparation"]
    NLP --> TEDA["Text EDA"]

    subgraph TPREPA[" "]
        direction LR
        TP1["Tokenization"]
        TP2["Stopwords"]
        TP3["Stemming"]
        TP4["Lemmatization"]
    end
    TPREP --> TPREPA

    subgraph TEDAA[" "]
        direction LR
        TE1["Word Frequency"]
        TE2["Word Clouds"]
        TE3["Text Statistics"]
        TE4["Class Distribution"]
    end
    TEDA --> TEDAA

    TPREPA --> FREP["Feature Representation"]

    subgraph FREPA[" "]
        direction LR
        FR1["Bag of Words"]
        FR2["TF-IDF"]
        FR3["Word2Vec"]
        FR4["Embeddings"]
    end
    FREP --> FREPA

    FREPA --> NLPMODEL["ML | DL | NLP Model"]


    classDef stage fill:#4A00E0,stroke:#8E2DE2,stroke-width:2px,color:#fff,font-weight:bold,rx:10,ry:10
    classDef sub fill:#1a1a2e,stroke:#8E2DE2,stroke-width:1px,color:#e0e0e0,rx:6,ry:6
    classDef root fill:#000,stroke:#8E2DE2,stroke-width:3px,color:#fff,font-weight:bold,rx:20,ry:20
    classDef split fill:#000,stroke:#FFD54F,stroke-width:2.5px,color:#fff,font-weight:bold,rx:14,ry:14
    classDef supervised fill:#1a1a2e,stroke:#E53935,stroke-width:1.5px,color:#fff,rx:6,ry:6
    classDef unsupervised fill:#1a1a2e,stroke:#1E88E5,stroke-width:1.5px,color:#fff,rx:6,ry:6
    classDef bagging fill:#1a2e1a,stroke:#43A047,stroke-width:2px,color:#fff,font-weight:bold,rx:6,ry:6
    classDef boosting fill:#2e2410,stroke:#FB8C00,stroke-width:2px,color:#fff,font-weight:bold,rx:6,ry:6
    classDef semi fill:#1a1a2e,stroke:#8E24AA,stroke-width:1.5px,color:#fff,rx:6,ry:6
    classDef rl fill:#1a1a2e,stroke:#00897B,stroke-width:1.5px,color:#fff,rx:6,ry:6
    classDef nlp fill:#1a1a2e,stroke:#FFD54F,stroke-width:1.5px,color:#fff,rx:6,ry:6
    classDef nlpStage fill:#4A0E70,stroke:#FFD54F,stroke-width:2px,color:#fff,font-weight:bold,rx:10,ry:10

    class A root
    class STR,UNS split
    class B,C,D,E,F,G,H,I,J,K stage
    class C1,C2,C3,C4,D1,D2,D3,D4,E1,E2,E3 sub
    class SUP,CONT,CAT,REG,RG1,RG2,CLF,CF1,CF2,CF3,CF4,CF5,H1,H2,H3,H4,H4B,H4C,H4D,H5,H6 supervised
    class UNSL,TNA,CLU,CL1,CL2,CL3,U1,U2,U3 unsupervised
    class SEMI,SNA,S1,S2,S3,SM1,SM2 semi
    class RL,RNA,RE1,RE2,RE3,RLE1,RLE2,RLE3 rl
    class RG3,CF6 bagging
    class RG4,RG5,RG6,CF7,CF8,CF9 boosting
    class NLP,TPREP,TEDA,FREP,NLPMODEL,NLPEVAL,NLPPRED nlpStage
    class TP1,TP2,TP3,TP4,TE1,TE2,TE3,TE4,FR1,FR2,FR3,FR4,NCLS,NCLU,NSIM nlp
```
<br/>

<div align="center">

![line](https://user-images.githubusercontent.com/74038190/212284100-561aa473-3905-4a80-b561-0d28506553ee.gif)

</div>

<br/>

<div align="center">
<sub>⭐ If this map helped map out your own ML journey, consider starring the repo.</sub>
</div>

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:4A00E0,100:8E2DE2&height=100&section=footer" width="100%"/>
