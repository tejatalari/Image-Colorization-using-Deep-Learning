

# Image Colorization Using U-Net Autoencoders

## Table of Contents

- [Project Overview](#project-overview)
- [Dataset](#dataset)
- [Model Architecture](#model-architecture)
- [Installation](#installation)
- [Usage](#usage)
- [Results](#results)
- [Future Work](#future-work)
- [Contributing](#contributing)
- [License](#license)

## Project Overview

This project involves using U-Net Autoencoders for image colorization, transforming grayscale images into their colored counterparts. The model learns to add colors to images by training on pairs of grayscale and colored images.

## Dataset

The dataset used for this project consists of colored images that are converted to grayscale for the input to the model. The corresponding colored images are used as the ground truth for training.

### Dataset Preparation

- **Grayscale Images**: Used as input to the model.
- **Colored Images**: Used as target output for training.

### Dataset Sources

- Publicly available datasets such as [CIFAR-10](https://www.cs.toronto.edu/~kriz/cifar.html) or [ImageNet](http://www.image-net.org/) can be used.
- Custom datasets can also be created by collecting colored images and converting them to grayscale.

## Model Architecture

The model is based on the U-Net architecture, an encoder-decoder model with skip connections that effectively captures spatial context in images, making it suitable for tasks like image colorization.

### Key Components

- **Encoder**: Captures the spatial features of the input grayscale image.
- **Bottleneck**: A compressed representation of the features.
- **Decoder**: Reconstructs the image from the encoded features and adds color.
- **Skip Connections**: Connects layers from the encoder to the decoder, helping retain spatial information.

### Model Summary

- **Encoder**: Multiple Conv2D layers with ReLU activation and MaxPooling2D layers.
- **Bottleneck**: A dense layer representing the compressed features.
- **Decoder**: Conv2DTranspose layers to upsample the features back to the original image size.
- **Output Layer**: A Conv2D layer with three channels (for RGB) and a sigmoid activation function.

## Installation

To run this project locally, follow these steps:

1. Clone the repository:
    ```bash
    git clone https://github.com/your-username/image-colorization-with-unet-auto-encoders.git
    ```
2. Navigate to the project directory:
    ```bash
    cd image-colorization-with-unet-auto-encoders
    ```
3. Create and activate a virtual environment (optional but recommended):
    ```bash
    python3 -m venv venv
    source venv/bin/activate
    ```
4. Install the required packages:
    ```bash
    pip install -r requirements.txt
    ```

## Usage

1. **Prepare the Data**:
    ```bash
    python prepare_data.py --input_dir path/to/colored/images --output_dir path/to/save/grayscale/images
    ```
2. **Train the Model**:
    ```bash
    python train.py --train_dir path/to/grayscale/images --target_dir path/to/colored/images
    ```
3. **Evaluate the Model**:
    ```bash
    python evaluate.py --test_dir path/to/test/images
    ```
4. **Colorize New Images**:
    ```bash
    python colorize.py --input_image path/to/grayscale/image.png --output_image path/to/save/colored/image.png
    ```

## Results

The model's performance can be evaluated based on the visual quality of the colorized images. Metrics such as Mean Squared Error (MSE) and Peak Signal-to-Noise Ratio (PSNR) can also be used for quantitative assessment.

### Example Colorizations

- **Grayscale Image 1**:
    - Input: ![Grayscale](path/to/grayscale_image1.png)
    - Output: ![Colorized](path/to/colorized_image1.png)
- **Grayscale Image 2**:
    - Input: ![Grayscale](path/to/grayscale_image2.png)
    - Output: ![Colorized](path/to/colorized_image2.png)

## Future Work

- **Model Improvement**: Experiment with different architectures and loss functions to improve the quality of colorization.
- **Data Augmentation**: Apply data augmentation techniques to increase the robustness of the model.
- **Real-Time Application**: Develop a real-time application for live image colorization.

## Contributing

Contributions are welcome! If you’d like to contribute, please fork the repository and use a feature branch. Pull requests are warmly welcome.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.


 
