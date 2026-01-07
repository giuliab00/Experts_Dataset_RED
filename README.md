# **Dataset Overview**

This repository contains datasets of **human–robot conversational interactions**, annotated with different **mental states**. The materials are organized across five JSON files.

---

## **Contents**

- **`anonymous_transcript.json`**  
  Contains the **human conversation transcripts** between user and a robot.  
  - **Participants are anonymized**: all users are referred to as **Alice** or **Bob**.  
  - Each entry includes:
    - **`sample`**: A dialogue snippet.  
    - **`phase`**: The task phase (e.g., *pre*, *mandala*, *postmandala*).
    - **`match`**: To be ignored, usefull to reconstruct the subset of the human-transcribed samples.

- **`expert1_dataset.json`**  
  Contains annotations by **Expert 1**, mapping transcript IDs to emotional/behavioral categories.

- **`expert2_dataset.json`**  
  Contains annotations by **Expert 2**, following the same schema as Expert 1 but with potentially different categorizations.

- **`intersection_dataset.json`**  
  Contains the **overlap of annotations** where Expert 1 and Expert 2 agree. 

- **`union_dataset.json`**  
  Contains the **union of annotations** from Expert 1 and Expert 2, merging their perspectives into broader coverage.
---

## **Dataset Structure**

The annotation-based datasets (`expert1_dataset.json`, `expert2_dataset.json`, `intersection_dataset.json`, `union_dataset.json`) follow this structure:

```json
{
  "mental_state": [
    "transcript_id",
    "transcript_id",
    ...
  ]
}
```

The transcript file (`anonymous_transcript.json`) has this structure:

```json
{
  "transcript_id": {
    "sample": "string (dialogue snippet)",
    "phase": "string (task phase)"
  }
}
```

---

### **Key Components**

1. **`transcript_id`**: Unique identifier linking annotations back to the raw dialogue.  
2. **`sample`**: A multi-turn conversation between the **User** (Alice/Bob) and the **Robot** (Pepper).  
3. **`phase`**: The task context of the interaction.  
4. **`category`**: The emotional/behavioral label assigned by experts.  

