# Automated-Detection-of-Peptic-Ulcer-using-Deep-Learning
This project presents a deep learning-based approach for automated detection of peptic ulcers from Wireless Capsule Endoscopy (WCE) images. Peptic ulcer diagnosis traditionally relies on manual inspection of thousands of endoscopic images, which is time-consuming and prone to human error. To address this challenge, this work focuses on building an intelligent system capable of classifying gastrointestinal images into Normal, Ulcer, and Arteriovenous Malformation (AVM) categories.

Feature Engineering and Preprocessing : 
The input consists of WCE images collected from the KAUHC Capsule Endoscopy dataset. Images were resized and normalized to ensure consistency across the dataset. Data augmentation techniques such as rotation, flipping, brightness variation, and contrast adjustment were applied to simulate real-world imaging conditions and improve model generalization. These preprocessing steps helped the model learn robust visual patterns despite variations in lighting, noise, and image quality.

Model Implementation : 
A hybrid CNN–Transformer architecture was implemented to leverage both local and global feature learning. A pre-trained ResNet50 model was used as the CNN backbone to extract low-level and mid-level visual features such as textures, edges, and lesion patterns. These feature maps were then passed to a Transformer block incorporating Multi-Head Attention, enabling the model to capture long-range dependencies and global contextual relationships within the image.

To address dataset imbalance, focal loss was used to assign higher importance to minority classes such as Ulcer and AVM. The model was trained in two phases: initially, the ResNet50 layers were frozen to train the classification head, followed by fine-tuning of the top layers to improve domain-specific feature learning.

Performance : 
The model achieved an overall accuracy of 89% on the validation set. The Normal class showed high precision and recall, indicating reliable identification of healthy tissue. The Ulcer class achieved a recall of 0.89, which is particularly important in medical applications where missing ulcer cases can lead to serious complications. Some misclassification was observed between AVM and Ulcer classes due to their visual similarity under varying imaging conditions.

Explainability : 
To enhance interpretability, saliency maps were generated to visualize regions of the image that contributed most to the model’s predictions. These maps confirmed that the model focuses on clinically relevant areas, improving transparency and trust in the system.

Dataset : 
The study was conducted using the KAUHC Capsule Endoscopy dataset, consisting of 3301 images categorized into three classes:
- Normal (2156 images)
- AVM (673 images)
- Ulcer (472 images)

Technology Stack : 
Python, TensorFlow, Keras, NumPy, Pandas, OpenCV, Matplotlib, Scikit-learn, Google Colab

Future Work : 
Future improvements may include training on larger and more diverse datasets, incorporating lesion localization and segmentation techniques, extending the model to video-level analysis, and deploying the system in real-time clinical environments.
