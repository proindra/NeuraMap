<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:8E2DE2,100:4A00E0&height=200&section=header&text=ML%20WorkFlow&fontSize=42&fontColor=ffffff&animation=fadeIn&fontAlignY=38&desc=From%20raw%20data%20to%20deployed%20intelligence&descAlignY=58&descSize=16" width="100%"/>

![Python](https://img.shields.io/badge/Python-3.11-4A00E0?style=for-the-badge&logo=python&logoColor=white)
![Status](https://img.shields.io/badge/Status-Reference%20Map-8E2DE2?style=for-the-badge)
![Made%20with](https://img.shields.io/badge/Made%20with-%E2%9C%A8-black?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-informational?style=for-the-badge)

</div>

<br/>

## 🗺️ The Pipeline

```mermaid
flowchart TD
    A(["🧬 DATA SCIENCE"]) --> B["📥 1. Data Collection"]
    B --> C["🧹 2. Data Preparation"]

    subgraph PREP[" "]
        direction LR
        C1["Data Cleaning"]
        C2["Missing Values"]
        C3["Duplicates"]
        C4["Data Transformation"]
    end
    C --> PREP

    PREP --> D["🔍 3. EDA — Exploratory Data Analysis"]

    subgraph EDA[" "]
        direction LR
        D1["Statistics"]
        D2["Visualization"]
        D3["Correlation"]
        D4["Outlier Analysis"]
    end
    D --> EDA

    EDA --> E["🛠️ 4. Feature Engineering"]

    subgraph FE[" "]
        direction LR
        E1["Feature Selection"]
        E2["Feature Creation"]
        E3["Encoding / Scaling"]
    end
    E --> FE

    FE --> F["🤖 5. Choose ML Model"]

    subgraph MODEL[" "]
        direction TB

        SUP["Supervised Learning"]
        UNS["Unsupervised Learning"]
        SEMI["Semi-Supervised Learning"]
        RL["Reinforcement Learning"]

        SUP --> CONT["Continuous Target"]
        SUP --> CAT["Categorical Target"]
        UNS --> TNA["Target Not Available"]
        SEMI --> SNA["Few Labeled + Many Unlabeled"]
        RL --> RNA["Reward-based Learning"]

        CONT --> REG["Regression"]
        CAT --> CLF["Classification"]
        TNA --> CLU["Clustering"]

        subgraph SEMIA[" "]
            direction LR
            S1["Self-Training"]
            S2["Label Propagation"]
            S3["Semi-Supervised SVM"]
        end
        SNA --> SEMIA

        subgraph RLA[" "]
            direction LR
            RE1["Q-Learning"]
            RE2["Deep Q-Network"]
            RE3["Policy Gradient"]
        end
        RNA --> RLA

        subgraph REGA[" "]
            direction LR
            RG1["Linear Regression"]
            RG2["Polynomial Regression"]
            RG3["🎒 Bagging: Random Forest"]
            RG4["🚀 Boosting: AdaBoost"]
            RG5["🚀 Boosting: Gradient Boost"]
            RG6["🚀 Boosting: XGBoost"]
        end
        REG --> REGA

        subgraph CLFA[" "]
            direction LR
            CF1["Logistic Regression"]
            CF2["SVM"]
            CF3["Naive Bayes"]
            CF4["KNN"]
            CF5["Decision Tree"]
            CF6["🎒 Bagging: Random Forest"]
            CF7["🚀 Boosting: AdaBoost"]
            CF8["🚀 Boosting: Gradient Boost"]
            CF9["🚀 Boosting: XGBoost"]
        end
        CLF --> CLFA

        subgraph CLUA[" "]
            direction LR
            CL1["K-Means"]
            CL2["Hierarchical"]
            CL3["DBSCAN"]
        end
        CLU --> CLUA
    end
    F --> MODEL

    MODEL --> G["🏋️ 6. Model Training"]
    G --> H["📊 7. Model Evaluation"]

    subgraph EVAL[" "]
        direction TB

        subgraph EVSUP["Supervised"]
            direction TB

            subgraph EVREG["Regression"]
                direction LR
                H4["RMSE"]
                H4B["MAE"]
                H4C["R² Score"]
                H4D["MSE"]
            end

            subgraph EVCLF["Classification"]
                direction LR
                H1["Accuracy"]
                H2["Precision / Recall"]
                H3["F1 Score"]
                H5["ROC-AUC"]
                H6["Confusion Matrix"]
            end
        end

        subgraph EVUNS["Unsupervised"]
            direction LR
            U1["Silhouette Score"]
            U2["Davies-Bouldin Index"]
            U3["Inertia / WCSS"]
        end

        subgraph EVSEMI["Semi-Supervised"]
            direction LR
            SM1["Accuracy on Labeled Subset"]
            SM2["Pseudo-Label Confidence"]
        end

        subgraph EVRL["Reinforcement"]
            direction LR
            RLE1["Cumulative Reward"]
            RLE2["Average Return"]
            RLE3["Convergence Rate"]
        end
    end
    H --> EVAL

    EVAL --> I["🎛️ 8. Hyperparameter Tuning"]
    I --> J["🔮 9. Prediction"]
    J --> K["🚀 10. Deployment & Monitoring"]

    classDef stage fill:#4A00E0,stroke:#8E2DE2,stroke-width:2px,color:#fff,font-weight:bold,rx:10,ry:10
    classDef sub fill:#1a1a2e,stroke:#8E2DE2,stroke-width:1px,color:#e0e0e0,rx:6,ry:6
    classDef root fill:#000,stroke:#8E2DE2,stroke-width:3px,color:#fff,font-weight:bold,rx:20,ry:20
    classDef supervised fill:#1a1a2e,stroke:#E53935,stroke-width:1.5px,color:#fff,rx:6,ry:6
    classDef unsupervised fill:#1a1a2e,stroke:#1E88E5,stroke-width:1.5px,color:#fff,rx:6,ry:6
    classDef bagging fill:#1a2e1a,stroke:#43A047,stroke-width:2px,color:#fff,font-weight:bold,rx:6,ry:6
    classDef boosting fill:#2e2410,stroke:#FB8C00,stroke-width:2px,color:#fff,font-weight:bold,rx:6,ry:6
    classDef semi fill:#1a1a2e,stroke:#8E24AA,stroke-width:1.5px,color:#fff,rx:6,ry:6
    classDef rl fill:#1a1a2e,stroke:#00897B,stroke-width:1.5px,color:#fff,rx:6,ry:6

    class A root
    class B,C,D,E,F,G,H,I,J,K stage
    class C1,C2,C3,C4,D1,D2,D3,D4,E1,E2,E3 sub
    class SUP,CONT,CAT,REG,RG1,RG2,CLF,CF1,CF2,CF3,CF4,CF5,H1,H2,H3,H4,H4B,H4C,H4D,H5,H6 supervised
    class UNS,TNA,CLU,CL1,CL2,CL3,U1,U2,U3 unsupervised
    class SEMI,SNA,S1,S2,S3,SM1,SM2 semi
    class RL,RNA,RE1,RE2,RE3,RLE1,RLE2,RLE3 rl
    class RG3,CF6 bagging
    class RG4,RG5,RG6,CF7,CF8,CF9 boosting
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
