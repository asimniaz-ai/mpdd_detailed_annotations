# MPDD Dataset Detailed Annotations

This repository contains detailed annotations for the MVTec dataset, which has been traditionally used for unsupervised anomaly detection tasks. These annotations aim to enhance the existing MVTec dataset by providing **detailed descriptions** of the anomalies in the images, including **types**, **locations (bounding boxes)**, **sizes**, and **descriptions**.

---
## Contents

- **Annotations**: JSON files containing detailed descriptions for each image in the MPDD dataset.
- **Code**: Scripts and tools for loading and visualizing the annotations (to be added in future updates).

---

## Purpose

These annotations are designed to support:

1. **Anomaly Localization**: Providing bounding box coordinates for the precise localization of anomalies.
2. **Model Training**: Enabling models to learn both anomaly detection and localization.
3. **Evaluation**: Offering ground truth data for accurate performance evaluation of anomaly detection models.
4. **Dataset Enhancement**: Elevating the usability of the MPDD dataset for fine-grained anomaly detection and localization tasks.

---

## Benefits for Large Language Models (LLMs)

These detailed annotations bridge the gap between **vision and language models**, enabling the following:

1. **Multimodal Learning**: Align textual descriptions with visual data for training **vision-language models** like CLIP or MiniGPT-4. information.
2. **Improved Explainability**: Enable LLMs to generate textual explanations for detected anomalies, improving interpretability.
3. **Query-Based Analysis**: Researchers can interact with LLMs using natural language queries (e.g., "Find defects larger than 5000 pixels in bolts") to retrieve relevant results.
4. **Synthetic Data Generation**: Allow LLMs to create new scenarios or simulate anomalies based on these annotations.
5. **Benchmarking and Validation**: The detailed annotations allow LLMs to assist in validating anomaly detection models by comparing predicted outputs with ground truth descriptions.

By combining your annotations with LLMs, researchers can enhance multimodal learning and develop more intelligent, explainable, and interactive anomaly detection frameworks.

---

## License

The annotations in this repository are made available under the Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License (CC BY-NC-SA 4.0). Please refer to the original MPDD dataset license for further usage terms.

---

## Citation

If you use this dataset in your scientific work, please cite the original MPDD dataset as follows:

@INPROCEEDINGS{9631567,
  author={Jezek, Stepan and Jonak, Martin and Burget, Radim and Dvorak, Pavel and Skotak, Milos},
  booktitle={2021 13th International Congress on Ultra Modern Telecommunications and Control Systems and Workshops (ICUMT)}, 
  title={Deep learning-based defect detection of metal parts: evaluating current methods in complex conditions}, 
  year={2021},
  volume={},
  number={},
  pages={66-71},
  doi={10.1109/ICUMT54235.2021.9631567}
}


### Additional Citation for the Annotations

If you use the detailed annotations provided in this repository, please also cite this work:

> **Asim Niaz, Muhammad Umraiz, Kwang Nam Choi** (2024). MPDD Dataset Detailed Annotations for Anomaly Detection. Retrieved from [[GitHub Repository URL](https://github.com/asimniaz-ai/mpdd_detailed_annotations)].

---

## How to Use the Annotations

The annotations in this repository are stored in a JSON format, and each entry contains the following fields:

- **class**: The class of the object (e.g., "connector").
- **anomaly**: The type of anomaly (e.g., "parts_mismatch").
- **image**: The name of the image file (e.g., "004.png").
- **num_anomalies**: The number of anomalies in the image.
- **size_anomalies**: The total size of the anomalies in pixels.
- **coordinates**: A list of bounding boxes for each anomaly. Each bounding box contains the following keys:
  - `min_row`: The minimum row (y-coordinate) of the bounding box.
  - `min_col`: The minimum column (x-coordinate) of the bounding box.
  - `max_row`: The maximum row (y-coordinate) of the bounding box.
  - `max_col`: The maximum column (x-coordinate) of the bounding box.
- **description**: A textual description of the anomaly in the image.

---

## Example Annotation

Below is an example of a detailed annotation for the MPDD dataset:

```json
{
    "connector": [
        {
            "class": "connector",
            "anomaly": "parts_mismatch",
            "image": "004.png",
            "num_anomalies": 1,
            "size_anomalies": 18879,
            "coordinates": [
                {
                    "min_row": 470,
                    "min_col": 767,
                    "max_row": 675,
                    "max_col": 891
                }
            ],
            "description": "Anomaly of type 'parts_mismatch' found in connector images. Image name: 004.png. Number of anomalies: 1, Size of anomalies: 18879 pixels."
        }
    ]
}
