# WARP.md

This file provides guidance to WARP (warp.dev) when working with code in this repository.

## Project Overview

This is a machine learning project for breast cancer prediction using logistic regression. The project uses the Wisconsin Diagnostic Breast Cancer (WDBC) dataset to classify breast tumors as malignant or benign based on 30 cell nucleus features computed from digitized fine needle aspirate (FNA) images.

## Key Commands

### Environment Setup
```bash
# Install dependencies using uv (recommended)
uv sync

# Or using pip
pip install numpy pandas matplotlib seaborn scikit-learn jupyter ipykernel
```

### Running the Project
```bash
# Start Jupyter Notebook
jupyter notebook

# Run the main Python script
python main.py
```

### Development Commands
```bash
# Open the main analysis notebook
jupyter notebook breastcancer.ipynb

# Check Python version (requires 3.12+)
python --version
```

## Architecture & Structure

### Dataset Details
- **Source**: Wisconsin Diagnostic Breast Cancer (WDBC) dataset
- **Location**: `breast+cancer+wisconsin+diagnostic/wdbc.data`
- **Format**: CSV without headers (569 rows, 32 columns)
- **Features**: ID, Diagnosis (M/B), 30 numerical features
- **Target**: Binary classification (Malignant=1, Benign=0)

### Feature Engineering
The dataset contains 30 features organized as:
- **10 base measurements** of cell nucleus characteristics (radius, texture, perimeter, area, smoothness, compactness, concavity, concave_points, symmetry, fractal_dimension)
- **3 statistical variants** of each measurement: Mean (3-12), Standard Error (13-22), Worst/Largest (23-32)

### ML Pipeline Architecture
1. **Data Loading**: Read from `wdbc.data` file (no headers, manual column assignment needed)
2. **Data Preprocessing**: 
   - Drop ID column (first column)
   - Encode diagnosis: M→1, B→0
   - Feature scaling with StandardScaler
3. **Model Training**: Logistic Regression (binary classification)
4. **Evaluation**: Standard classification metrics

### File Structure
- `breastcancer.ipynb`: Main analysis notebook with complete ML pipeline
- `main.py`: Minimal Python entry point
- `breast+cancer+wisconsin+diagnostic/`: Dataset directory
  - `wdbc.data`: Main dataset (569 samples, 32 features)
  - `wdbc.names`: Dataset documentation and feature descriptions
- `pyproject.toml`: Project configuration with dependencies

## Development Notes

### Data Handling Specifics
- **No Headers**: The CSV file has no column headers - they must be added programmatically
- **Mixed Data Types**: ID (string), Diagnosis (categorical M/B), Features (numerical)
- **Target Encoding**: Diagnosis column needs manual encoding (M=malignant=1, B=benign=0)
- **Feature Scaling**: Essential due to different scales across the 30 numerical features

### Medical Context
- **Domain**: Healthcare/Medical diagnosis
- **Application**: Automated breast cancer screening support
- **Dataset Origin**: University of Wisconsin hospitals (real clinical data)
- **Accuracy Benchmark**: Original research achieved 97.5% accuracy with optimal feature selection

### Dependencies
- **Core ML**: scikit-learn (LogisticRegression, train_test_split, StandardScaler)
- **Data Processing**: pandas, numpy
- **Visualization**: matplotlib, seaborn
- **Environment**: Jupyter notebook for interactive analysis

### Performance Expectations
- **Model Type**: Binary logistic regression classifier
- **Input**: 30-dimensional feature vector
- **Output**: Probability score + binary prediction (0/1)
- **Typical Accuracy**: High (90%+) due to dataset quality and feature engineering