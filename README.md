graph TB
    Start([Start System]) --> Config[Initialize Configurations]
    
    subgraph Data_Preparation [DATA PREPARATION PHASE]
    Config --> Row1A[Scrape Website]
    Row1A --> Row1B[Clean Data]
    Row1B --> Row1C[Store JSON]
    Row1C --> Row2A[Generate Embeddings]
    Row2A --> Row2B[Store in ChromaDB]
    end
    
    subgraph Interaction [USER INTERACTION PHASE]
    Row2B --> Row3A[Receive Query]
    Row3A --> Row3B[Semantic Search]
    Row3B --> Row4A[Rank Top-N Matches]
    end
    
    subgraph AI_Insights [AI INSIGHTS PHASE]
    Row4A --> Row5A[Gemini API Analysis]
    Row5A --> End([Display Results])
    end

    %% Node Styles
    style Start fill:#FFD700,stroke:#B8860B,color:#000
    style End fill:#FFD700,stroke:#B8860B,color:#000
    style Config fill:#FFD700,stroke:#B8860B,color:#000
    style Row1A fill:#FFD700,stroke:#B8860B,color:#000
    style Row1B fill:#FFD700,stroke:#B8860B,color:#000
    style Row1C fill:#FFD700,stroke:#B8860B,color:#000
    style Row2A fill:#FFD700,stroke:#B8860B,color:#000
    style Row2B fill:#FFD700,stroke:#B8860B,color:#000
    style Row3A fill:#FFD700,stroke:#B8860B,color:#000
    style Row3B fill:#FFD700,stroke:#B8860B,color:#000
    style Row4A fill:#FFD700,stroke:#B8860B,color:#000
    style Row5A fill:#FFD700,stroke:#B8860B,color:#000

    %% Subgraph Styles
    style Data_Preparation fill:#333,stroke:#FFD700,color:#FFD700
    style Interaction fill:#333,stroke:#FFD700,color:#FFD700
    style AI_Insights fill:#333,stroke:#FFD700,color:#FFD700
