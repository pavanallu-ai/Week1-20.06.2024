# MERAI NEWAGE PVT.LTD.
``` mermaid
graph TB
    subgraph "Frontend Layer"
        UI[Streamlit Dashboard]
        DASH[Dash Analytics]
        GRAF[Grafana Monitoring]
    end
    
    subgraph "Load Balancer Tier"
        LB[Load Balancer]
        HPA[Auto-Scaling]
    end
    
    subgraph "API Gateway Cluster"
        GW1[API Gateway 1]
        GW2[API Gateway 2]
        GW3[API Gateway 3]
        AUTH[Authentication Service]
    end
    
    subgraph "Core Services"
        DTG[Digital Twin Generator]
        OPM[Outcome Predictor]
        AE[Analytics Engine]
        FEEDBACK[Feedback Loop Service]
    end
    
    subgraph "Model Layer"
        GPT[GPT Transformer]
        BILSTM[BiLSTM Hybrid]
        FUSION[Attention-Based Fusion]
        SUPPORT[Support Models]
    end
    
    subgraph "Data Layer - Clearly Defined Roles"
        PG[(PostgreSQL<br/>Transactional Data)]
        MONGO[(MongoDB<br/>Semi-structured/Logs)]
        REDIS[(Redis<br/>Cache/Sessions)]
        S3[(S3<br/>Files/Models/Backups)]
    end
    
    UI --> LB
    DASH --> LB
    GRAF --> LB
    
    LB --> GW1
    LB --> GW2
    LB --> GW3
    HPA --> GW1
    HPA --> GW2
    HPA --> GW3
    
    GW1 --> AUTH
    GW2 --> AUTH
    GW3 --> AUTH
    
    AUTH --> DTG
    AUTH --> OPM
    AUTH --> AE
    
    DTG --> FEEDBACK
    FEEDBACK --> DTG
    
    DTG --> GPT
    OPM --> BILSTM
    OPM --> FUSION
    AE --> SUPPORT
    
    GPT --> PG
    BILSTM --> MONGO
    FUSION --> REDIS
    SUPPORT --> S3
```
2nd 
``` mermaid
graph TD
    subgraph "Input Processing"
        PATIENT[Patient Data]
        TRIAL_META[Trial Metadata]
        PROMPT[Prompt Engineering]
        CONTEXT_HIST[Historical Context]
    end
    
    subgraph "GPT Model"
        ENCODER[Transformer Encoder]
        DECODER[Transformer Decoder]
        ATTENTION[Multi-Head Attention]
    end
    
    subgraph "Generation Process with Feedback"
        CONTEXT[Context Building]
        GENERATE[Sequence Generation]
        VALIDATE[Output Validation]
        FEEDBACK_CHECK[Feedback Analysis]
        REFINEMENT[Refinement Process]
        QUALITY_GATE[Quality Gate]
    end
    
    subgraph "Feedback Sources"
        HUMAN_FB[Human Feedback]
        AUTO_FB[Automated Validation]
        CLINICAL_FB[Clinical Expert Review]
    end
    
    subgraph "Output"
        SYNTHETIC[Synthetic EHR]
        TRAJECTORY[Patient Trajectory]
        OUTCOMES[Predicted Outcomes]
        CONFIDENCE[Confidence Scores]
    end
    
    PATIENT --> PROMPT
    TRIAL_META --> PROMPT
    CONTEXT_HIST --> PROMPT
    PROMPT --> CONTEXT
    
    CONTEXT --> ENCODER
    ENCODER --> ATTENTION
    ATTENTION --> DECODER
    
    DECODER --> GENERATE
    GENERATE --> VALIDATE
    VALIDATE --> FEEDBACK_CHECK
    
    HUMAN_FB --> FEEDBACK_CHECK
    AUTO_FB --> FEEDBACK_CHECK
    CLINICAL_FB --> FEEDBACK_CHECK
    
    FEEDBACK_CHECK --> REFINEMENT
    REFINEMENT --> QUALITY_GATE
    
    QUALITY_GATE -->|Pass| SYNTHETIC
    QUALITY_GATE -->|Pass| TRAJECTORY
    QUALITY_GATE -->|Pass| OUTCOMES
    QUALITY_GATE -->|Pass| CONFIDENCE
    
    QUALITY_GATE -->|Fail| REFINEMENT
    REFINEMENT --> GENERATE
```
