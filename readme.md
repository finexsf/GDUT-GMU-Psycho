# Chinese Psychological Counseling Dialogue Dataset for Fine-grained Suicide Risk Assessment

A real-world Chinese psychological counseling dialogue dataset with fine-grained suicide risk annotations and temporal cue labeling.

![License](https://img.shields.io/badge/license-CC_BY--NC_4.0-blue)

![Language](https://img.shields.io/badge/language-Chinese-red)

![Task](https://img.shields.io/badge/task-Suicide_Risk_Assessment-green)

---

# Overview

This repository contains a real-world Chinese psychological counseling dialogue dataset collected from psychological assistance hotline counseling records during actual crisis intervention processes.

The dataset is intended to support research on:

- Suicide risk detection
- Fine-grained suicide risk classification
- Temporal cue modeling
- Mental health NLP
- Long-context conversational modeling
- Crisis intervention research
- Large language model fine-tuning

Unlike social media based datasets, the conversations in this dataset originate from real counseling and crisis intervention scenarios, preserving:

- Multi-turn dialogue structures
- Emotional progression
- Temporal expressions
- Context-dependent suicide risk signals
- Real psychological counseling interactions

---

# Dataset Structure

The dataset mainly consists of:

```text
├── conv_XXXX.txt
├── label.txt
└── README.md
```

---

# Dialogue Format

Each dialogue file contains a multi-turn conversation in JSON format.

Example:

```json
[
  {
    "role": "human",
    "content": "最近压力特别大，经常睡不着。"
  },
  {
    "role": "gpt",
    "content": "能和我说说最近发生了什么吗？"
  }
]
```

Roles include:

- `human` : caller / patient
- `gpt` : psychological counselor / hotline responder

---

# Annotation Format

The `label.txt` file contains line-level suicide risk annotations and temporal cue annotations.

Example:

```json
  "conv_1397": [
    {
      "class": "4",
      "suicide_row": "每次那种痛苦劲儿一上来，我就总想着干脆从高处跳下去算了。但说到底还是没那个胆量，只能凑到窗户跟前往下瞅两眼，最后再默默把窗子关好。这也是我目前最苦恼的一点，明明日子过得挺顺心、挺美满的，心里头却总是莫名其妙地堵得慌。",
      "time_row": "每次那种痛苦劲儿一上来，我就总想着干脆从高处跳下去算了。但说到底还是没那个胆量，只能凑到窗户跟前往下瞅两眼，最后再默默把窗子关好。这也是我目前最苦恼的一点，明明日子过得挺顺心、挺美满的，心里头却总是莫名其妙地堵得慌。",
      "keyword": "现在",
      "suicide_line_idx": 34,
      "time_line_idx": 34
    },
    ……
  ]
```

---

# Annotation Fields

| Field            | Description                                             |
| ---------------- | ------------------------------------------------------- |
| class            | Suicide risk category                                   |
| suicide_row      | Dialogue sentence containing suicide-related expression |
| time_row         | Sentence containing temporal cue                        |
| keyword          | Extracted temporal keyword                              |
| suicide_line_idx | Line index of suicide-related sentence                  |
| time_line_idx    | Line index of temporal cue                              |
| human_verified   | Whether annotation is manually verified                 |

---

# Label Definition

The dataset uses a fine-grained suicide risk stratification framework.

| Class | Description                                |
| ----- | ------------------------------------------ |
| 1     | Low or no suicide risk                     |
| 2     | Historical suicide-related expression      |
| 3     | Recent suicide-related behavior            |
| 4     | Active suicidal ideation                   |
| 5     | Short-term suicide planning                |
| 6     | Imminent suicide risk or ongoing self-harm |

---

# Temporal Cue Annotation

A key contribution of this dataset is the explicit annotation of temporal cues related to suicide risk progression and urgency.

The annotations explicitly identify:

- Temporal expressions
- Time-sensitive suicidal intent
- Risk progression
- Urgency-related language

Examples of temporal expressions include:

- “最近”
- “这几天”
- “每天”
- “半个月”
- “今晚”
- “现在”
- “前阵子”

These temporal signals are important for assessing:

- Risk escalation
- Immediate intervention needs
- Persistence of suicidal ideation

---

# Annotation Pipeline

The dataset was annotated using a semi-automatic annotation framework combining:

- Rule-based candidate extraction
- Large language model assisted labeling
- Human verification and correction

The annotation workflow includes:

- Suicide-related utterance detection
- Temporal cue extraction
- Risk level assignment
- Manual quality verification

---

# Data Source

The dataset was collected from real-world psychological assistance hotline counseling records from the Guangzhou Psychological Crisis Intervention Center during 2023.

All data were anonymized and de-identified for academic research purposes only.

---

# Ethical Statement

This dataset contains sensitive mental health related content.

By using this dataset, users agree:

- Not to attempt re-identification
- Not to use the dataset for harmful purposes
- Not to use the dataset for direct clinical diagnosis
- To comply with applicable ethical and legal regulations

The dataset is intended only for academic and research use.

---

# Citation

If you use this dataset in your research, please cite:

```bibtex
@dataset{chinese_suicide_dialogue_dataset,
  title={Chinese Psychological Counseling Dialogue Dataset for Fine-grained Suicide Risk Assessment},
  year={2026},
  author={Anonymous}
}
```

---

# License

This dataset is released under:

\- CC BY-NC 4.0

---

# Disclaimer

This dataset is intended solely for academic research purposes.

The authors are not responsible for any misuse of the dataset or downstream system decisions.