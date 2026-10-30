# 🌐 Enterprise AI Governance & Global Compliance Statement
### 企業級 AI 管治與全球法規合規聲明 (Bilingual)

This document outlines the AI governance framework, privacy architecture, and global regulatory applicability for the **Enterprise Demo: Smart Charge Code Inquiry System**. It is maintained by the project author to ensure transparency, accountability, and compliance with international standards.
本文件旨在闡明「企業智能扣帳方查詢系統（展示版）」之 AI 管治架構、隱私保護設計以及全球法規之適用性，確保系統具備高度透明度、問責制並符合國際標準。

---

## 1. 系統法律定位與架構宣告 (System Legal Positioning & Architectural Declaration)

**Not a Generative AI / 非生成式人工智能系統：**
This system is strictly classified as a **Deterministic Semantic Retrieval System** powered by a local Machine Learning embedding model (Sentence Transformers). It DOES NOT possess generative capabilities, does not autonomously create new content, and operates fundamentally as an advanced search engine with zero hallucination risk.
在法律與技術定位上，本系統為**「確定性語意檢索系統」**。系統僅運用本地機器學習模型提取特徵向量進行距離比對，**不具備生成式內容（Generative Content）能力**，無自主編造內容（AI Hallucination）之風險。

**Zero Data Retention & Privacy by Design / 零數據留存與預設隱私：**
The system is built on a stateless runtime architecture. User inputs and uploaded datasets exist solely within volatile session memory and are completely destroyed upon session termination. No databases, logging servers, or third-party cloud storage are used.
系統採無狀態（Stateless）架構，所有上傳之資料僅存於揮發性會話記憶體（Volatile Memory），網頁關閉即全量銷毀，徹底隔絕資料外洩可能。

---

## 2. 全球法規適用性矩陣 (Global Regulatory Applicability Matrix)

The following matrix assesses the system against major global frameworks, applying exemptions where structurally justified to avoid unnecessary regulatory bloat.
以下矩陣評估本系統在全球主流監管框架下之適用性，並依據系統架構事實，排除不適用之法規以避免過度承諾（Over-commitment）。

| Regulatory Framework (法規/框架) | Applicability (適用性) | Legal Justification & Governance Strategy (法理依據與管治策略) |
| :--- | :---: | :--- |
| **🇪🇺 EU Artificial Intelligence Act (EU AI Act)** | **Minimal / No Risk (極微風險)** | **Exempt from High-Risk obligations.** The tool does not fall under Annex III (e.g., biometric, critical infra, HR screening). It is a basic text-matching utility with transparent operation.<br>*不屬於高風險清單，僅為內部文字輔助工具，不受嚴格之合規評估與註冊限制。* |
| **🇪🇺 EU GDPR** <br> (Regulation 2016/679) | **Compliant / Exempt (合規 / 豁免)** | **No PII Processing.** The system is designed for corporate operational terminology. Through "Data Protection by Design" (Art. 25), it inherently processes no personal data.<br>*系統不收集亦不處理歐盟居民之個人身分識別資訊 (PII)，自帶豁免屬性。* |
| **🇨🇳 國家網信辦 (CAC)** <br> 《生成式人工智能服務管理暫行辦法》 | **Not Applicable (不適用)** | **Non-Generative & Internal Demo.** The system does not provide generative text/image services to the public within Mainland China. It operates purely as a deterministic local retrieval script.<br>*本系統非「向境內公眾提供生成式人工智能服務」，且無內容生成能力，依法無需進行算法備案與安全評估。* |
| **🇭🇰 香港《個人資料(私隱)條例》** <br> (Cap. 486 PDPO) | **Fully Compliant (完全合規)** | **Data Minimization.** No persistent storage aligns perfectly with Data Protection Principle 2 (Retention) and Principle 4 (Security).<br>*無持久化資料庫，符合保障資料原則第2原則（保留）與第4原則（保安），絕無私隱外洩風險。* |

---

## 3. ISO 國際標準對齊實踐 (ISO Standards Alignment Practice)

The architecture maps directly to the control requirements of the following ISO standards:
本專案在底層設計上，已直接對齊以下國際標準之核心控制措施：

### 🛡️ ISO/IEC 42001:2023 - Artificial Intelligence Management System (AIMS)
* **A.6.2 (Data Minimization):** Fully realized via session-based volatile memory. (資料僅限單次 Session 存在)
* **A.8.2 (Transparency & Explainability):** Search results explicitly cite the exact row from the source spreadsheet. No "black-box" reasoning. (結果 100% 回溯原始試算表行數，無黑箱決策)
* **A.8.3 (Human Oversight):** Explicitly declared as a Decision Support Tool. Humans retain full authority over financial/contractual determinations. (定位為輔助工具，人類掌握最終決策權)

### 🔐 ISO/IEC 27001:2022 - Information Security Management System (ISMS)
* **A.8.12 (Data Leakage Prevention):** Architecture is completely "air-gapped" from external LLM endpoints (e.g., OpenAI, Anthropic). No network egress for user payload. (切斷第三方 API 呼叫，數據不出境)
* **A.8.24 (Use of Cryptography) & CI/CD Security:** Enforced via DevSecOps pipelines (Bandit SAST, CodeQL, Dependency Review) blocking vulnerable supply chain components. (自動化安全掃描防線阻擋漏洞)

### 👁️ ISO/IEC 27701:2019 - Privacy Information Management (PIMS)
* **By-Design De-identification:** The operational scope structurally prohibits the collection of PII. The environment acts as an ephemeral sandbox, fulfilling extreme privacy preservation. (從業務邏輯層面隔絕 PII，實踐極致隱私保護)

---

## 4. 最終免責聲明與人工介入 (Disclaimer & Human-in-the-Loop)

**For Demonstration Purposes Only:**
This repository constitutes an open-source technical showcase created by **Jacky Law**. It demonstrates software architecture and AI governance principles. It is NOT intended to provide binding legal, financial, or auditing advice. 

**Human Accountability:**
In any real-world deployment, all generated code matches must be verified by authorized personnel. The author assumes no liability for operational misinterpretations or compliance breaches resulting from independent forks or modifications of this codebase.

**免責與問責聲明：**
本專案為架構展示性質之開源原型，非具約束力之法務或審計系統。任何實際應用場景中，扣帳代號與責任之判定均須經由人類主管（Human-in-the-loop）核對。專案作者對任何衍生分叉（Fork）或非授權部署所引發之商業損失概不負責。

---
*Last Updated: 2026-10 | Governance Lead: Jacky Law*
