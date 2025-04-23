# 🖼️ Image Captioning Generator

This project is an end-to-end **Image Captioning Generator** that combines **Natural Language Processing (NLP)** and **Computer Vision (CV)** to generate textual descriptions of images using the **Flickr 8K dataset**. It uses a **CNN-LSTM** architecture, where CNN (DenseNet201) extracts features from the image, and LSTM generates contextually relevant captions.

## 📂 Dataset

- **Dataset Used:** [Flickr 8K](https://www.kaggle.com/datasets/adityajn105/flickr8k)  
- Consists of 8,000 images, each with 5 human-annotated captions.  
- Used only the images and `Flickr8k.token.txt` file for training.

## 🔧 Technologies & Tools

- **Languages:** Python  
- **Libraries:** TensorFlow, Keras, NLTK, NumPy, Matplotlib, Pillow  
- **Model:** DenseNet201 (CNN for image feature extraction) + LSTM (RNN for caption generation)

## 🧠 Model Architecture

- **Feature Extraction:**  
  - Used **DenseNet201** pretrained on ImageNet (`no_top=True`)  
  - Extracted 1920-dimensional image features using the `GlobalAveragePooling2D` layer.

- **Text Processing:**  
  - Cleaned and tokenized captions using **NLTK**  
  - Built a vocabulary and word-to-index mappings  
  - Applied padding for sequence input

- **Caption Generator (Decoder):**  
  - LSTM-based sequence model that takes extracted features and partial captions to generate the next word  
  - Used **Embedding**, **LSTM**, **Dense**, and **Add** layers for modeling

## 🔁 Training Process

- **Loss Function:** Categorical Crossentropy  
- **Optimizer:** Adam  
- **Epochs:** 10  
- **Performance:** Reached loss ~2.19 at epoch 9 (on local system)  
- **Training Strategy:** Teacher forcing for faster convergence

## 🧪 Testing

- Generated captions using:
  - **Greedy Search**
  - (Optionally) Beam Search for better results

## 📊 Example Output

> **Image:** A man riding a surfboard on a wave  
> **Predicted Caption:** *"a man is riding a wave on a surfboard"*

## 📁 Folder Structure


## 🚀 How to Run

1. **Download the Dataset:** Place images and caption text file in `dataset/`.
2. **Extract Features:**  
