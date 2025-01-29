| **Layer Name**            | **Type**                 | **Output Shape**        | **Param #**  |
|--------------------------|-------------------------|------------------------|-------------|
| **input**               | InputLayer              | (None, 256, 64, 1)     | 0           |
| **conv1**               | Conv2D (32 filters)     | (None, 256, 64, 32)    | 320         |
| **batch_normalization**  | BatchNormalization      | (None, 256, 64, 32)    | 128         |
| **activation**          | ReLU Activation         | (None, 256, 64, 32)    | 0           |
| **max1**                | MaxPooling2D            | (None, 128, 32, 32)    | 0           |
| **conv2**               | Conv2D (64 filters)     | (None, 128, 32, 64)    | 18,496      |
| **batch_normalization_1**| BatchNormalization      | (None, 128, 32, 64)    | 256         |
| **activation_1**        | ReLU Activation         | (None, 128, 32, 64)    | 0           |
| **max2**                | MaxPooling2D            | (None, 64, 16, 64)     | 0           |
| **dropout**             | Dropout                 | (None, 64, 16, 64)     | 0           |
| **conv3**               | Conv2D (128 filters)    | (None, 64, 16, 128)    | 73,856      |
| **batch_normalization_2**| BatchNormalization      | (None, 64, 16, 128)    | 512         |
| **activation_2**        | ReLU Activation         | (None, 64, 16, 128)    | 0           |
| **max3**                | MaxPooling2D            | (None, 64, 8, 128)     | 0           |
| **dropout_1**           | Dropout                 | (None, 64, 8, 128)     | 0           |
| **reshape**             | Reshape                 | (None, 64, 1024)       | 0           |
| **dense1**              | Dense (64 units)        | (None, 64, 64)         | 65,600      |
| **lstm1**               | Bidirectional LSTM (512)| (None, 64, 512)        | 657,408     |
| **lstm2**               | Bidirectional LSTM (512)| (None, 64, 512)        | 1,574,912   |
| **dense2**              | Dense (30 units)        | (None, 64, 30)         | 15,390      |
| **softmax**             | Softmax Activation      | (None, 64, 30)         | 0           |
| **Total Parameters**    |                         |                        | **2,406,878** |
| **Trainable Parameters**|                         |                        | **2,406,430** |
| **Non-Trainable Params**|                         |                        | **448** |
