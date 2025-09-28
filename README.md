# Breast Cancer Prediction using Machine Learning

A machine learning project that predicts whether breast cancer tumors are malignant or benign using logistic regression. This project uses the Wisconsin Diagnostic Breast Cancer (WDBC) dataset to classify breast cancer based on features computed from digitized images of fine needle aspirates (FNA) of breast masses.

## 📊 Dataset Overview

The project uses the **Wisconsin Diagnostic Breast Cancer (WDBC)** dataset, which contains:

- **569 instances** of breast cancer cases
- **32 attributes** (ID, diagnosis, and 30 real-valued features)
- **2 classes**: 
  - **M (Malignant)**: 212 cases
  - **B (Benign)**: 357 cases

### Features Description

The dataset contains 30 real-valued features computed from digitized images of breast mass cell nuclei. For each cell nucleus, 10 features are computed:

1. **Radius** - Mean of distances from center to points on the perimeter
2. **Texture** - Standard deviation of gray-scale values
3. **Perimeter** - Cell nucleus perimeter
4. **Area** - Cell nucleus area
5. **Smoothness** - Local variation in radius lengths
6. **Compactness** - Perimeter² / area - 1.0
7. **Concavity** - Severity of concave portions of the contour
8. **Concave Points** - Number of concave portions of the contour
9. **Symmetry** - Cell nucleus symmetry
10. **Fractal Dimension** - "Coastline approximation" - 1

For each of these 10 features, three measurements are provided:
- **Mean** (features 3-12)
- **Standard Error** (features 13-22)  
- **Worst** (mean of the three largest values, features 23-32)

## 🤖 Machine Learning Algorithm

This project implements **Logistic Regression** for binary classification to predict whether a breast tumor is malignant or benign.

### Why Logistic Regression?
- Excellent for binary classification problems
- Provides probabilistic outputs
- Computationally efficient
- Interpretable results
- Well-suited for medical diagnosis applications

## 🛠️ Technologies Used

- **Python 3.12+**
- **NumPy** - Numerical computations
- **Pandas** - Data manipulation and analysis
- **Matplotlib** - Data visualization
- **Seaborn** - Statistical data visualization
- **Scikit-learn** - Machine learning algorithms and preprocessing
- **Jupyter Notebook** - Interactive development environment

## 📋 Prerequisites

- Python 3.12 or higher
- pip or uv package manager

## 🚀 Installation

1. Clone the repository:
```bash
git clone https://github.com/PK-SANGAMESWAR/breast-cancer-prediction.git
cd breast-cancer-prediction
```

2. Install dependencies using uv (recommended):
```bash
uv sync
```

Or using pip:
```bash
pip install numpy pandas matplotlib seaborn scikit-learn jupyter ipykernel
```

## 📖 Usage

### Running the Jupyter Notebook

1. Start Jupyter Notebook:
```bash
jupyter notebook
```

2. Open `breastcancer.ipynb` in your browser

3. Run all cells to execute the complete analysis

### Running the Main Script
```bash
python main.py
```

## 📁 Project Structure

```
breast-cancer-prediction/
├── README.md                           # Project documentation
├── main.py                            # Main Python script
├── breastcancer.ipynb                 # Jupyter notebook with full analysis
├── pyproject.toml                     # Project configuration and dependencies
├── uv.lock                           # Lock file for reproducible builds
├── .python-version                   # Python version specification
├── breast+cancer+wisconsin+diagnostic.zip  # Compressed dataset
└── breast+cancer+wisconsin+diagnostic/     # Dataset directory
    ├── wdbc.data                     # Main dataset file
    └── wdbc.names                    # Dataset description and attributes
```

## 🔬 Machine Learning Workflow

The project follows a standard machine learning pipeline:

1. **Data Loading**: Import the WDBC dataset from `wdbc.data`
2. **Data Exploration**: Analyze dataset structure and characteristics
3. **Data Preprocessing**: 
   - Handle categorical diagnosis column (M/B → 1/0)
   - Remove ID column (not useful for prediction)
   - Feature scaling using StandardScaler
4. **Train-Test Split**: Split data into training (typically 80%) and testing (20%) sets
5. **Model Training**: Train logistic regression model on training data
6. **Prediction**: Make predictions on test data
7. **Evaluation**: Assess model performance using various metrics
8. **Results Analysis**: Analyze prediction accuracy and model performance

## 📈 Key Features

- **High-dimensional Feature Analysis**: Works with 30 different cell nucleus characteristics
- **Binary Classification**: Predicts malignant vs benign tumors
- **Feature Scaling**: Implements proper normalization for optimal model performance
- **Medical Domain Application**: Real-world healthcare machine learning application
- **Comprehensive Analysis**: Includes data exploration, preprocessing, and model evaluation

## 🎯 Medical Context

This project addresses a critical healthcare challenge:

- **Early Detection**: Helps in early identification of malignant breast tumors
- **Diagnostic Support**: Provides automated analysis of fine needle aspirate (FNA) images
- **Accuracy**: The original research achieved 97.5% accuracy using optimal feature selection
- **Clinical Relevance**: Based on real medical data from University of Wisconsin hospitals

## 📊 Expected Results

The model provides:
- **Binary predictions**: 0 (Benign) or 1 (Malignant)
- **Probability scores**: Confidence level for each prediction
- **Performance metrics**: Accuracy, precision, recall, and F1-score
- **Confusion matrix**: Detailed breakdown of prediction results

## 🔍 Dataset Citation

**Wisconsin Diagnostic Breast Cancer (WDBC)**

**Creators:**
- Dr. William H. Wolberg, General Surgery Dept., University of Wisconsin
- W. Nick Street, Computer Sciences Dept., University of Wisconsin  
- Olvi L. Mangasarian, Computer Sciences Dept., University of Wisconsin

**Source:** UCI Machine Learning Repository
**Date:** November 1995

**References:**
- Street, W.N., Wolberg, W.H., and Mangasarian, O.L. (1993). Nuclear feature extraction for breast tumor diagnosis. IS&T/SPIE 1993 International Symposium on Electronic Imaging: Science and Technology, volume 1905, pages 861-870, San Jose, CA.

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/new-feature`)
3. Make your changes
4. Commit your changes (`git commit -am 'Add some feature'`)
5. Push to the branch (`git push origin feature/new-feature`)
6. Create a new Pull Request

## 📝 License

This project is open source and available under the [MIT License](LICENSE).

## 👨‍💻 Author

**P.K. Sangameswar**
- Machine Learning Engineer
- Healthcare AI Applications

## 🔗 Links

- [Original Dataset](http://archive.ics.uci.edu/ml/datasets/Breast+Cancer+Wisconsin+%28Diagnostic%29)
- [University of Wisconsin Research](http://www.cs.wisc.edu/~olvi/uwmp/cancer.html)

---

*This project demonstrates the application of machine learning in medical diagnosis, specifically for breast cancer detection using cell nucleus characteristics from fine needle aspirate images.*