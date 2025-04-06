# Exploring CNNs with PyTorch: CIFAR-10 Classifier
**Muhammad Ali**

I tested three Convolutional Neural Networks (CNNs) on the CIFAR10 dataset. These networks are **SimpleCNN**, **CustomCNN1**, and **CustomCNN2**. Each one classifies images into ten categories such as cars, ships, and animals. I also used **RandomHorizontalFlip** and **RandomCrop** data augmentation to flip some images and randomly crop others, making each model more robust by showing it many different image variations.

---

## SimpleCNN
- **Layers:** Two convolutional layers.  
  - First has 16 filters  
  - Second has 32 filters  
- After each convolution, I reduce the feature map size.  
- Finally, there are two fully connected layers for classification.  
- **Key Points:**  
  - Trains quickly and is easy to set up  
  - Learns fewer features  
  - Reaches around 70% accuracy

---

## CustomCNN1
- **Depth:** Three blocks, each with two convolutional layers  
  - Filters go from 64 → 128 → 256  
  - Feature size is reduced after each block  
- **Regularization:** Dropout is added to prevent overfitting  
- **Performance:**  
  - Higher accuracy and lower validation loss compared to SimpleCNN

---

## CustomCNN2
- **Depth:** Three blocks, each with three convolutional layers (total of nine)  
- **Regularization:** Extra dropout after the second block and before the final layers  
- **Performance:**  
  - Longer training time  
  - Achieved higher accuracy and lower validation loss than both SimpleCNN and CustomCNN1

---

## Conclusion
- SimpleCNN is a good basic model but limited in capacity.  
- CustomCNN1 adds more layers and dropout for a stronger balance.  
- CustomCNN2 goes even further with nine convolutional layers and extra dropout, achieving the best performance of the three.  
- If you want higher accuracy, you can train for more epochs or try additional regularization.  
- I first tested each network as is, then conducted three tests after finalizing CustomCNN1 and CustomCNN2. Averaging those results showed **CustomCNN2** leading in accuracy.  
- If I had more time, I would have explored more architectures and hyperparameter tuning for even better results.

---

### Final Average Results

**Simple CNN (2 layers)**  
- Final test: `0.8104`  
- Validation Loss: `0.7667`  
- Accuracy: **72.99%**

**CustomCNN1**  
- Final Test Evaluation  
- Validation Loss: `0.4922`  
- Accuracy: **83.39%**

**CustomCNN2**  
- Final Test Evaluation  
- Validation Loss: `0.4273`  
- Accuracy: **86.58%**
