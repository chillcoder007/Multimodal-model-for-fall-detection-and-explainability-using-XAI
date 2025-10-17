# Multimodal-model-for-fall-detection-and-explainability-using-XAI
This project delivers a real-time, robust, and transparent fall detection system designed for older adults and vulnerable individuals at risk of injury from falls. Leveraging a multimodal approach, the system fuses data from wearable sensors (such as accelerometers) with visual input from cameras. 
## Features
- **Multimodal data fusion:** Combines time-series sensor data and visual camera information for greater detection reliability.
- **Deep learning architecture:** Uses 1D and 2D convolutional neural networks for feature extraction and classification.
- **Late fusion integration:** Retains unique patterns from each modality until the final stage for improved decision-making.
- **Explainable AI integration:** Employs LIME (Local Interpretable Model-Agnostic Explanations) for user-friendly and transparent output explanations.
- **Real-time notifications:** Provides immediate alerts when a fall is detected.
- **User-centric design:** Accessible interface for users and caregivers using affordable, readily available hardware.
## Dataset
- **UP-Fall Detection Dataset:** Includes wearable sensor records, camera images, and activity labels from simulated daily activities and fall scenarios.

## Installation

1. Clone the repository:
git clone https://github.com/your-username/multimodal-fall-detection-xai.git
cd multimodal-fall-detection-xai

2. Install dependencies:
pip install -r requirements.txt

3. Download the dataset (instructions in `docs/dataset.md`).

## Usage

1. Preprocess your dataset:
 ```
 python preprocess.py
 ```

2. Train the model:
 ```
 python train.py --config configs/train_config.yaml
 ```

3. Run fall detection on new data:
 ```
 python detect.py --input path/to/new_data
 ```

4. Visualize explainability outputs:
 ```
 python explain.py --event event_id
 ```

## Model Architecture

- **Sensor Pathway:** 1D CNN layers with max pooling and batch normalization.
- **Camera Pathways:** 2D CNN layers for each camera with max pooling, batch normalization, and flattening.
- **Fusion:** Concatenation of last flatten layers from all pathways.
- **Fully Connected Layers:** Two FC layers with dropout for regularization.
- **Softmax Output:** Binary classification (Fall / No Fall) with probabilities.
- **Explainability:** LIME applied post-classification for explanation overlays and feature attribution.

## Results
- **Accuracy:** ~99.56% on validation/test sets.
- **Precision, Recall, F1:** All above 0.99 for most activities; 0.77 to 0.85 for falling events.
- **Confusion Matrix and LIME explanations** included in `results/` for reference.

## Security
- Follows strong encryption (AES-256) and secure access practices for sensitive participant data.

## References

- World Health Organization statistics on falls
- UP-Fall Detection Dataset
- Local Interpretable Model-Agnostic Explanations (LIME)
- Related literature (see `docs/literature.md` for a full survey)

## Future Work

- Integration of audio signals as an additional modality
- LSTM modules for enhanced temporal modeling
- Exploration of other explainability tools such as SHAP or integrated gradients
