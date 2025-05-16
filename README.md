# Brain Tumor Segmentation using UNet

![Brain Tumor Segmentation](https://img.shields.io/badge/Medical%20Imaging-Brain%20Tumor%20Segmentation-blue)
![PyTorch](https://img.shields.io/badge/PyTorch-2.0+-red)
![Streamlit](https://img.shields.io/badge/Streamlit-1.30+-green)
![License](https://img.shields.io/badge/License-MIT-yellow)

A deep learning application for automatic segmentation of brain tumors from MRI scans using a UNet neural network architecture. This web-based tool allows users to upload NIfTI format brain MRI scans and receive instant tumor segmentation results with comprehensive analysis and visualization options.

## Features

- **Advanced Tumor Segmentation**: Using state-of-the-art UNet architecture trained on BraTS2020 dataset
- **Interactive Visualization**: Explore MRI scans with multiple view orientations (Axial, Sagittal, Coronal)
- **Detailed Tumor Metrics**: Quantitative analysis including size, shape, location, and morphology
- **AI-Powered Clinical Interpretations**: Optional clinical assessment using Google's Gemini AI (requires API key)
- **User-Friendly Interface**: Built with Streamlit for an intuitive and responsive experience
- **Versatile Visualization Options**: Multiple overlay styles and confidence mapping

## Table of Contents

- [Installation](#installation)
- [Usage](#usage)
- [Technical Details](#technical-details)
- [Features In-Depth](#features-in-depth)
- [AI Explanations](#ai-explanations)
- [Sample Data](#sample-data)
- [Project Structure](#project-structure)
- [Contributing](#contributing)
- [License](#license)

## Installation

### Prerequisites

- Python 3.8+
- pip package manager

### Setup

1. Clone this repository:
   ```bash
   git clone https://github.com/yourusername/brain-tumor-segmentation.git
   cd brain-tumor-segmentation
   ```

2. Install required dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Run the application:
   ```bash
   streamlit run App.py
   ```

The application should now be running on your local machine at `http://localhost:8501`.

## Usage

### Basic Operation

1. **Launch the application** by running `streamlit run App.py`
2. **Upload an MRI scan** in NIfTI format (.nii or .nii.gz), or use the provided sample data
3. **Select the view orientation** (Axial, Sagittal, or Coronal)
4. **Navigate through slices** using the slider
5. **Adjust segmentation parameters** in the sidebar if needed
6. **View results** including segmentation overlay and metrics
7. **Download** images or reports for further use

### Advanced Options

- **Adjust the segmentation threshold** to fine-tune tumor detection sensitivity
- **Select different normalization methods** to optimize for different MRI acquisition parameters
- **Change overlay styles** for better visualization
- **Enable batch processing** for analyzing multiple slices simultaneously

## Technical Details

### Model Architecture

The application uses a UNet model with the following characteristics:
- **Architecture**: Standard U-Net with encoder-decoder and skip connections
- **Input**: 2D MRI slices (normalized)
- **Output**: Probabilistic segmentation maps
- **Training Data**: BraTS2020 dataset (Multimodal Brain Tumor Segmentation Challenge)

### Image Processing Pipeline

1. **Loading**: NIfTI files are loaded using nibabel
2. **Preprocessing**: Slices are extracted and normalized
3. **Inference**: The model processes the slice and produces a segmentation mask
4. **Postprocessing**: Results are analyzed for metrics calculation and visualization

## Features In-Depth

### Tumor Metrics

The application calculates comprehensive metrics including:
- **Size**: Area in pixels, percentage of slice occupied
- **Dimensions**: Width, height, estimated diameter
- **Shape Analysis**: Perimeter, circularity index
- **Location**: Center coordinates, bounding box

### Visualization Options

- **Contour Overlay**: Highlighting tumor boundaries on the original image
- **Heatmap Overlay**: Color-coded visualization of tumor regions
- **Confidence Map**: Visualization of the model's prediction confidence
- **Multiple color schemes**: hot, viridis, jet, cool

## AI Explanations

The application optionally integrates with Google's Gemini API to provide AI-powered clinical interpretations of the segmentation results.

### Setting Up Gemini Integration

1. Obtain a Google Gemini API key from the [Google AI Studio](https://ai.google.dev/)
2. In the application sidebar, expand "🔑 AI Explanation Settings"
3. Enter your API key and click "Activate API"
4. Enable "Show AI Clinical Explanation" in the sidebar options

The AI will analyze the tumor characteristics and provide clinical insights including:
- Potential diagnosis and differential considerations
- Relevant observations about tumor morphology
- Suggested next steps in clinical evaluation

## Sample Data

The application includes synthetic sample brain MRI data for testing and demonstration purposes. This can be accessed by checking the "Use sample data instead" option on the main interface.

## Project Structure

```
brain-tumor-segmentation/
├── App.py                # Main application file
├── requirements.txt      # Python dependencies
├── logo.png              # Application logo
├── checkpoint-epoch-29.pt # Pre-trained model weights
└── README.md             # This documentation
```

## Contributing

Contributions to improve the application are welcome! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Acknowledgments

- BraTS challenge organizers for the inspiration and training data concepts
- PyTorch team for the deep learning framework
- Streamlit team for the web application framework

---

**Note**: This application is intended for research and educational purposes only and should not be used for clinical diagnosis without proper validation and expert medical oversight.
