# Automated CTI-to-MITRE ATT&CK Extraction Pipeline

An automated Cyber Threat Intelligence (CTI) pipeline that ingests unstructured adversary incident reports, extracts MITRE ATT&CK tactics and techniques using Google Gemini and strict Pydantic schemas, and compiles valid MITRE ATT&CK Navigator heat map layers.

---

## 🎯 Project Overview
Mapping unstructured cyber threat bulletins to the MITRE ATT&CK framework is traditionally a labor-intensive, manual process prone to analyst subjectivity. This tool demonstrates an automated, deterministic pipeline designed to:
- Ingest unstructured incident reporting (sample case study: **Scattered Spider / G1015**).
- Structure threat intelligence into validated JSON schemas using LLM function calling and Pydantic constraints.
- Output production-ready layer files for the MITRE ATT&CK Navigator with confidence-weighted scoring and contextual citations.

---

## 🏗️ Architecture & Technologies
- **Python**: Core workflow execution and layer structure builder.
- **Google Gemini API**: Extraction engine for semantic parsing of adversary behavior.
- **Pydantic**: Strict data modeling to enforce schema validation and eliminate hallucinations.
- **MITRE ATT&CK Navigator**: Matrix visualization (Enterprise Matrix v15+).

---

## 📂 Repository Contents
| File | Description |
| :--- | :--- |
| `CTI_to_MITRE_ATT&CK_Extractor.ipynb` | Google Colab notebook containing the end-to-end ingestion and extraction pipeline. |
| `attack_layer.json` | Generated Navigator layer file populated with technique IDs, scores, and evidence citations. |
| `Scattered_Spider__Automated_Analysis.svg` | Exported vector visualization of the resulting threat matrix. |

---

## 🚀 How to Run

1. Open `CTI_to_MITRE_ATT&CK_Extractor.ipynb` in Google Colab.
2. Add your Gemini API key to your Colab **Secrets** tab with the name `GEMINI_API_KEY`.
3. Run the notebook cells sequentially to extract adversary techniques and generate `attack_layer.json`.
4. Open the [MITRE ATT&CK Navigator](https://mitre-attack.github.io/attack-navigator/), click **Open Existing Layer** -> **Upload from local file**, and select `attack_layer.json` to inspect the live heat map.
