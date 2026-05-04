# VoiceStressDistress

## Description

This repository contains an anonymized dataset of voice features and associated metadata collected as part of the **Colive Voice study**, investigating:  *Voice changes associated with stress and distress in people living with diabetes*

The dataset is linked to the article:
**“Voice changes associated with stress and distress in people living with diabetes: Results from the Colive Voice study”**
*(submitted to PLOS Digital Health)*

---

## Dataset Overview

The dataset includes **voice features extracted from audio recordings** of participants with diabetes, along with associated clinical and self-reported measures.

### Feature categories

Each participant has features from four domains:

* **Prosody** (e.g., pitch, energy, rhythm)
* **Phonation** (e.g., voice stability, jitter, shimmer)
* **Articulation** (e.g., speech clarity, formants)
* **Phonological** (e.g., speech patterns)

---

## Files

### Metadata

* `metadata_female.pkl`
* `metadata_male.pkl`

Each contains:

| Column           | Description                                |
| ---------------- | ------------------------------------------ |
| `participant_id` | Anonymized participant identifier          |
| `stress`         | Self-reported stress level (ordinal scale) |
| `language`       | Recording language                         |
| `age`            | Participant age                            |
| `typediabetes`   | Type of diabetes                           |
| `hba1c`          | 1 if above 7, 0 else                       |
| `paid_score`     | PAID score grouped in categories           |

---

### Voice Features

For each sex (female / male) and feature type:

* `prosody_1_*.pkl`
* `phonation_1_*.pkl`
* `articulation_1_*.pkl`
* `phonological_1_*.pkl`

Each file contains:

* `participant_id`
* extracted voice features

---

## Data Structure

* Each participant is identified by a **shared anonymized ID (`participant_id`)**
* Feature datasets can be merged with metadata using this ID:

```python
import pandas as pd

metadata = pd.read_pickle("metadata_female.pkl")
prosody = pd.read_pickle("prosody_1_female.pkl")

df = prosody.merge(metadata, on="participant_id")
```

---

## Study Context

This dataset was designed to explore:

* the relationship between **stress** and **voice characteristics**
* the impact of **diabetes-related distress**
* differences across **sex** and **speech feature domains**

Voice features were extracted using signal processing methods (e.g., DisVoice toolkit).

---

## Ethical Considerations

This dataset contains sensitive human data (health and voice-derived features).
Users must:

* use the data responsibly
* avoid any attempt at re-identification
* comply with applicable ethical and legal standards

---

## License

This dataset is released under the **Creative Commons CC0 1.0 Universal license**.

---

## 📌 Citation

If you use this dataset, please cite:

```text
Voice changes associated with stress and distress in people living with diabetes:
Results from the Colive Voice study (PLOS Digital Health, under review)
```

---

## Contact

For questions or collaborations, please contact the authors of the study.

---

