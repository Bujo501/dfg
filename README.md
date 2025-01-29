# **Algorithm for CNN-BiLSTM Model**

## **Input:**  
   - A grayscale image of shape **(256, 64, 1)**  

## **Step 1: Feature Extraction (CNN Layers)**  
1. Apply **Conv2D** with `32 filters`, `kernel size = (3,3)`, `padding='same'`  
2. Apply **Batch Normalization**  
3. Apply **ReLU Activation**  
4. Apply **MaxPooling2D** `(pool size = (2,2))`  

5. Apply **Conv2D** with `64 filters`, `kernel size = (3,3)`, `padding='same'`  
6. Apply **Batch Normalization**  
7. Apply **ReLU Activation**  
8. Apply **MaxPooling2D** `(pool size = (2,2))`  
9. Apply **Dropout** `(rate=0.2)`  

10. Apply **Conv2D** with `128 filters`, `kernel size = (3,3)`, `padding='same'`  
11. Apply **Batch Normalization**  
12. Apply **ReLU Activation**  
13. Apply **MaxPooling2D** `(pool size = (2,1))`  
14. Apply **Dropout** `(rate=0.2)`  

## **Step 2: Reshape for Sequence Processing**  
15. Reshape the output to `(64, 1024)`, making it a sequence of 64 steps with 1024 features each.  

## **Step 3: Sequence Learning (BiLSTM Layers)**  
16. Apply a **Dense Layer** with `64 units`  
17. Apply a **Bidirectional LSTM** layer with `512 units`  
18. Apply another **Bidirectional LSTM** layer with `512 units`  

## **Step 4: Output Layer**  
19. Apply a **Dense Layer** with `30 units` (number of output classes)  
20. Apply **Softmax Activation** to generate probability scores  

## **Output:**  
   - A sequence output of shape **(64, 30)** representing `64 time steps` with `30 possible classes`
