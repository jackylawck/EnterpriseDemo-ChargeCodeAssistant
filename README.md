# 🏗️ Enterprise Demo: Smart Charge Code Inquiry System
### 企業智能扣帳方查詢系統 (合規與 AI 管治開源展示版)

[![CI/CD Pipelines](https://img.shields.io/badge/DevSecOps-GitHub_Actions-2088FF.svg?logo=github)](https://github.com/jackylawck/EnterpriseDemo-ChargeCodeAssistant/actions)
[![ISO 42001](https://img.shields.io/badge/Compliance-ISO_42001_AIMS-success.svg)](GOVERNANCE_AND_COMPLIANCE.md)
[![Zero Data Retention](https://img.shields.io/badge/Privacy-Zero_Data_Retention-orange.svg)](GOVERNANCE_AND_COMPLIANCE.md)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

本專案為企業級合規語意檢索工具之開源原型展示（Demo）。透過本地向量語意分析與結構化資料比對技術，協助團隊迅速檢索內部扣帳指引，釐定工程突發情境對應之費用分類代號，並示範無伺服器持久化存儲的合規 AI 治理架構。

This repository demonstrates an enterprise-grade compliance query architecture. Leveraging local semantic embeddings and structured spreadsheet alignment, the system assists operational teams in identifying applicable charge codes while adhering to strict zero-data-retention AI governance frameworks.

👉 **[Live System Demo | 點擊此處直接開啟系統展示](https://jackylawck.github.io/EnterpriseDemo-ChargeCodeAssistant/)**

---

## 💡 Architecture & Key Features | 架構設計與核心特點

1. **Zero Data Retention at Rest (100% 本地記憶體銷毀)**  
   Uploaded guideline datasets (`.xlsx`) reside exclusively in volatile browser session memory. All data is completely purged immediately upon tab closure or page refresh, ensuring zero backend persistence.
   上傳之指引文件只暫存於使用者瀏覽器工作階段（Session Memory），關閉分頁即刻徹底清除，不寫入任何後端硬碟或雲端資料庫。

2. **Air-Gapped Embedding (隔絕外部大模型 API)**  
   Semantic feature extraction is processed entirely locally via open-source multi-lingual embedding models (`sentence-transformers`). It strictly prohibits egress to external LLM APIs (e.g., OpenAI), eradicating commercial IP exfiltration risks.
   全程使用本地端開源 Embedding 模型進行特徵提取與比對，無需調用外部公共大模型，根除商業機密外流風險。

3. **Deterministic Output & Zero Hallucination (高解釋性與零幻覺)**  
   Instead of generative text, the system utilizes Dense Vector Matching (FAISS) to map fuzzy queries directly to source spreadsheet rows, providing exact line-number citations and confidence scores.
   結果直接鎖定來源檔案行號，完全杜絕生成式 AI 的編造事實（Hallucination）問題。

---

## 🛡️ ISO Compliance & AI Governance | 國際標準與管治對齊

This project structurally adheres to the following core controls:
本系統在底層設計上嚴格遵從以下國際標準：

* **ISO/IEC 42001:2023 (AIMS)**
  * **A.6.2 (Data Minimization):** Implemented via stateless volatile runtime. (實踐「無資料保留」架構)
  * **A.8.2 (Explainability):** 100% trace-back to source documentation. (每一筆結果均具備原始出處對照)
  * **A.8.3 (Human-in-the-Loop):** Explicitly declared as a Decision Support Tool. (定位為決策輔助工具)
* **ISO/IEC 27001:2022 (ISMS)**
  * **A.8.12 (Data Leakage Prevention):** Architecture is isolated from third-party generative endpoints. (切斷第三方 API 連接)

Please refer to the [Governance and Compliance Framework](GOVERNANCE_AND_COMPLIANCE.md) for full regulatory applicability mapping (including EU AI Act & GDPR exemptions).
詳細法規適用性矩陣請參閱管治合規文件。

---

## ⚙️ Enterprise DevSecOps | 企業級自動化安全防線

This repository utilizes advanced GitHub Actions pipelines to enforce strict software supply chain security:
本專案已建置完整之 DevSecOps CI/CD 流程：

* **CodeQL Advanced Security:** Deep semantic code scanning for vulnerabilities. (進階程式碼安全掃描)
* **Bandit SAST:** Static Application Security Testing blocking medium/high-severity Python vulnerabilities. (攔截中高風險之 Python 靜態漏洞)
* **Dependency Review:** Blocks Pull Requests containing known vulnerable packages or prohibited licenses (e.g., AGPL-3.0). (供應鏈依賴安全阻擋機制)
* **AI Issue Triage:** Utilizes GitHub Models for automated, prompt-injection-resistant issue summarization. (具備防護指令注入能力之 AI 總結機器人)
* **Super-Linter:** Enforces code quality and formatting standards across Python and YAML files. (強制執行代碼品質規範)

---

## 🚀 Quick Start | 本地執行

To run this demo locally:
如需於本地環境啟動本展示系統：

```bash
# 1. Clone the repository
git clone [https://github.com/jackylawck/EnterpriseDemo-ChargeCodeAssistant.git](https://github.com/jackylawck/EnterpriseDemo-ChargeCodeAssistant.git)

# 2. Install dependencies
pip install -r requirements.txt

# 3. Launch the Streamlit application
streamlit run app.py

```

---

## 📜 Disclaimer | 免責聲明

This repository is an open-source technical showcase created for demonstrating AI governance and compliance architecture. It does NOT contain any proprietary corporate data or confidential information. All tested scenarios and terminology are sanitized, generic construction industry examples. This system is not intended to provide binding legal or financial auditing advice.

本專案僅供系統架構、AI 管治與技術研發展示用途，**絕無包含任何特定企業之內部機密資料**。所有測試數據及術語均為經脫敏處理之通用營造業範例。本系統不提供具法律約束力之財務或審計決定。

```

```
