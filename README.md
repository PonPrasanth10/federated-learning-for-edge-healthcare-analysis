Project Overview: Secure Federated Learning for Medical Diagnostics
1. Core Objective
To build a decentralized, privacy-preserving machine learning pipeline that allows multiple hospitals to train a shared breast cancer diagnostic model without ever sharing raw patient data.

2. Technical Pipeline Layers
Federated Core (Phase 1): Uses the FedAvg algorithm to synchronize local model updates across 5 simulated hospital clients using the UCI Breast Cancer dataset.
Differential Privacy (Phase 2): Injects calibrated Gaussian noise and performs per-sample gradient clipping. This provides a mathematical guarantee (Epsilon  ϵ≈5.0 ) that individual patient records cannot be leaked from the model weights.
Secure Aggregation (Phase 3): Implements Additive Secret Sharing (SMPC). Model updates are split into random shards so the central server can compute the global average without ever 'seeing' a specific hospital's local model.
Heterogeneity Management (Phase 4): Uses K-Means Clustering to group clients with similar data distributions (Non-IID), allowing for specialized models that perform better on skewed local data.
3. Performance Summary
Metric	Baseline	Private (DP+SMPC)
Accuracy	~97-98%	~92-95%
Security	None	Cryptographically Blind
Privacy	Vulnerable	 ϵ -Differential Privacy
4. Key Innovation
The project successfully addresses the Privacy-Utility Trade-off, maintaining high diagnostic accuracy while implementing a 'Defense-in-Depth' strategy that protects data at rest, in transit, and during computation.

