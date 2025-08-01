# 🍽️ Voxel51 + HPI Food Waste Hackathon 

## 📚 Overview

This repository documents our data processing pipeline, dataset creation, and project goals for training computer vision models to recognize food waste and infer nutritional information. The resulting dataset is structured in a Voxel51-compatible format to support downstream applications in food waste reduction and nutritional analytics.

---

## 📊 Dataset Pipeline

### 1. Dataset 1: Baseline Dataset (Internal or Provided Dataset)

* This dataset forms the base structure.
* Contains images with metadata such as file path, ingredient name, and quantity.

### 2. Dataset 2: Hugging Face Dataset

* **Source**: `Dldermann/food-waste-dataset-v2`

#### Key Preprocessing Steps:

* Original metadata is in German, including column names and ingredient values.
* German column names were translated into English.
* Ingredient values were translated into English using a custom mapping.
* Schema was aligned to match Dataset 1 for successful merging.

#### Outcome:

* The processed Dataset 2 was merged with Dataset 1 and converted into a unified Voxel51-compatible dataset.

### 3. Dataset 3: New Data Collection

* Contains newly collected photos of food waste.
* Each photo is labeled with food item name and weight embedded in the filename.

#### Parsing and Field Generation:

* Folder names and filenames were used to derive metadata.
* A parsing script extracted:

  * **Ingredient name**
  * **Return quantity (weight)**
* These parsed values were stored as fields in the Voxel51 dataset schema.
* Final dataset was aligned with Dataset 1 and merged.

---

## 🚀 Use Cases

* Train visual AI models to detect food items and estimate quantity.
* Enable personalized meal planning based on visual input.
* Generate nutrition insights from food images for healthcare and diet monitoring.
* Build automated logging tools for kitchens and care institutions.
* Support waste reduction by classifying and tracking discarded food items.

---

## 🌟 Project Goals

* **🍽️ Visual Recognition of Complex Dishes**
  Train AI models to visually recognize food — even in complex, mixed, or partially consumed meals.

* **🧫 Precision Nutrition for Personalized Meal Plans**
  Extract accurate nutritional data from food images to enable truly personalized dietary recommendations.

* **🤖 Automation for Kitchens and Care Staff**
  Automate food tracking processes to reduce the manual workload for culinary teams and care providers.

* **⚠️ Early Detection of Malnutrition Risks**
  Use AI insights from food consumption patterns to identify and mitigate risks of malnutrition early.

---

## 📁 Folder Structure (Optional)

```bash
.
├── data/                        # All datasets (raw + processed)
├── notebooks/                  # Preprocessing + demo notebooks
├── scripts/                    # Helper scripts for parsing + merging
├── voxel51_dataset/           # Final Voxel51-compatible dataset
├── README.md
```

---

Let me know if you want a setup guide or code examples for Voxel51 integration.

