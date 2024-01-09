# Comparing Face Recognition Algorithms and Methods (K-NN, PCA< LDA, SVM, LeNet5)

## Dataset
**Olivetti faces dataset (AT&T Laboratories Cambridge)**

"*There are ten different images of each of 40 distinct subjects. For some subjects, the images were taken at different times, varying the lighting, facial expressions (open / closed eyes, smiling / not smiling) and facial details (glasses / no glasses). All the images were taken against a dark homogeneous background with the subjects in an upright, frontal position (with tolerance for some side movement).*"

The original dataset consisted of 92 x 112, while the version available here consists of 64x64 images.

- Classes: 40
- Samples per class: 10
- Samples total: 400
- Dimensionality: 4096 (64x64 pixels)
- Pixel values: real, between 0 and 1
  
## Results
|   Model  | Scenario 1 | Scenario 2 | Scenario 3 |
| -------- | -------- | -------- | -------- |
| K-NN     | 73%      | 88%      | 89%      |
| PCA      | 72%      | 88%      | 89%      |
| LDA      | 73%      | 90%      | **97%**  |
| SVM      | **76%**  | **90%**  | 95%      |
| LeNet5 (with data augmentation)   | 3%  | 77%  | 88%      |

- Scenario 1: 20% of the images for training and 80% for testing
- Scenario 2: 50% of the images for training and 50% for testing
- Scenario 3: 80% of the images for training and 20% for testing

**Conclusion**:

On all scenarios and the overall accuracy, we can see that LDA, and SVM perform better on this task.

The accuracy is increased when we increase more training data as in scenario 2 and 3 where we use 5 images and 8 images for each class.

Looking at the confusion matrix for all models in all scenarios, there are no models that exhibit a strong bias towards a specific class (all scores are equal to 0 for that class), indicating that they perform well across all classes.