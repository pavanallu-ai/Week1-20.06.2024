# MERAI NEWAGE PVT.LTD.
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
