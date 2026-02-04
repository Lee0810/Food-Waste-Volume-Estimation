# Food-Waste-Volume-Estimation

This folder contains the complete implementation of a food waste estimation system using YOLOv8 and monocular depth estimation. The project includes dataset preparation, model training, ablation studies, food detection, classification, and volume estimation.

#### Jupyter Notebooks

0\.    **GPU\_Setup:** This notebook checks and configures the GPU environment. It verifies CUDA availability, PyTorch installation, and ensures the system is ready for training and inference.

1. **Split\&Convert\_Dataset:** This notebook prepares the dataset for the project. It splits the dataset into training and validation sets and converts the data into a format compatible with YOLOv8 classification and detection.
2. **Train\_Yolov8\_classification:** This notebook trains the baseline YOLOv8 classification model without a neck module and neck module. The results from this model are used as the reference for later ablation experiments.
3. **TrainStarYolov8:** This notebook trains YOLOv8 classification models with the Star Block integrated into the backbone and the C2-f star. These experiments evaluate the effect of the Star Block on feature extraction.
4. **TrainAtentionYolov8:** This notebook trains YOLOv8 classification models enhanced with attention mechanisms such as SPPF module, channel attention and spatial attention. These models are part of the ablation study.
5. **Train\_Yolov8\_Detection:** This notebook trains the YOLOv8 detection model using the UEC-Food-100 dataset. The trained model is used to locate food regions in images.
6. **Result of Ablation Experiment:** This notebook collects and analyses the results of all ablation experiments. It includes training loss, validation loss, Top-1 accuracy, and Top-5 accuracy for different model variants.
7. **Volume\_Estimation:** This notebook implements the food waste volume estimation process. It combines food detection, monocular depth estimation, and relative scale calibration using a reference plate to compute a relative food volume index.


#### Image File
1. **plate.jpg:** This image is used as a reference object for scale estimation. The plate diameter is assumed to represent a known real-world size for pixel-to-centimetre conversion.

#### YAML File
**yolov8-cls.yaml:** This YAML is used to train our ablation experiments models

#### Python File
**block.py:** This is the Python file with the implementation of Star Block, and the C2f-star code. 

#### Folders
1. FoodWasteVolume\_results: This folder stores the output files of the food waste volume estimation, including CSV results and calculated volume indices.
2. MiDaS: This folder contains the MiDaS monocular depth estimation model and related files used to generate depth maps from RGB images.
3. DetectFood: This folder stores trained YOLOv8 detection models and detection inference results.
4. Result\_CLS\_No\_Neck: This folder contains training logs, model weights, and results for YOLOv8 classification models without a neck module.
5. Result\_CLS\_Neck: This folder contains training logs, model weights, and results for YOLOv8 classification models with a neck module, including Star Block and attention-based models.
