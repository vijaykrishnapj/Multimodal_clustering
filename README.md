# Multimodal_clustering
                    ┌───────────────────────────────────────┐
                    │        MULTIMODAL CLUSTERING          │
                    └───────────────────────────────────────┘
                                   /            \
                                  /              \
                                 /                \
                                /                  \
                               /                    \
             ┌───────────────────────┐      ┌────────────────────────┐
             │     TEXT PIPELINE     │      │     IMAGE PIPELINE     │
             └───────────────────────┘      └────────────────────────┘
                    |                                  |
                    |                                  |
     ┌───────────────────────────┐        ┌───────────────────────────┐
     │   1. Load BBC Documents   │        │   1. Load CIFAR-10 Images │
     └───────────────────────────┘        └───────────────────────────┘
                    |                                  |
     ┌───────────────────────────┐        ┌───────────────────────────┐
     │ 2. Text Preprocessing     │        │ 2. Preprocessing (Resize, │
     │    • Lowercase            │        │    Normalize)             │
     │    • Remove noise         │        └───────────────────────────┘
     │    • Tokenize             │                      |
     │    • POS filtering        │        ┌───────────────────────────┐
     │    • Lemmatization        │        │ 3. Deep Feature Extraction│
     │    • Stopword removal     │        │    MobileNetV2 (CNN)      │
     └───────────────────────────┘        └───────────────────────────┘
                    |                                  |
     ┌───────────────────────────┐        ┌───────────────────────────┐
     │   3. TF-IDF Vectorization │        │ 4. KMeans Clustering      │
     │     (1-gram, 2-gram,      │        │    (Image Feature Vectors)│
     │      3-gram)              │        └───────────────────────────┘
     └───────────────────────────┘                      |
                    |                                  |
     ┌───────────────────────────┐        ┌───────────────────────────┐
     │ 4. Multiple Clustering    │        │ 5. PCA 2D Visualisation   │
     │    Algorithms:            │        └───────────────────────────┘
     │    • KMeans               │
     │    • Agglomerative        │
     │    • DBSCAN               │
     │    • Spectral             │
     │    • GMM                  │
     └───────────────────────────┘
                    |
     ┌───────────────────────────┐
     │ 5. Best Model Selection   │
     │    (Silhouette Score)     │
     └───────────────────────────┘
                    |
     ┌───────────────────────────┐
     │ 6. Topic Extraction       │
     │    (Top TF-IDF Keywords)  │
     └───────────────────────────┘
                    |
           ┌───────────────────────────┐
           │ Combined Multimodal Output│
           │  • Text clusters + names  │
           │  • Image clusters         │
           │  • Visual PCA plots       │
           └───────────────────────────┘
