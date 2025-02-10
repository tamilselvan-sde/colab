





graph TD
    %% Data Ingestion & Preprocessing
    A[MQTT (EV Battery Sensors)] --> B[Apache Flink (Stream Processing)]
    B --> C[Azure Data Lake (Raw & Processed Data)]
    C --> D[Feast (Feature Storage)]
    
    %% Model Training & Experiment Tracking
    D --> E[Kubeflow Pipelines + DeepSpeed (LSTM)]
    E --> F[Ray Tune (Hyperparameter Tuning)]
    F --> G[MLflow (Experiment Tracking)]
    G --> H[Pinecone (Vector Search - Anomaly Detection)]
    G --> I[DynamoDB (Metadata Storage)]
    
    %% Model Packaging & Deployment
    G --> J[ONNX + TensorRT (Model Optimization)]
    J --> K[FluxCD/ArgoCD (CI/CD Deployment)]
    K --> L[TinyML + Azure IoT Edge (Edge Inference)]
    
    %% Monitoring & Auto-Retraining
    L --> M[Prometheus + Grafana (Monitoring)]
    M --> N[Evidently AI (Drift Detection)]
    N --> O[Kubeflow Pipelines (Auto Retraining)]
    O --> G  %% Feedback loop to MLflow for retraining
