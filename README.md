# 📊 AT25-41253: Statistical Machine Learning
## Hands-On Materials for Actuarial Science

**Course:** AT25-41253 - Statistical Machine Learning  
**Program:** Actuarial Science  
**Institution:** Institut Teknologi Sumatera  
**Instructor:** Martin C.T. Manullang  

---

## 📖 Overview

This repository contains hands-on learning materials for the Statistical Machine Learning course (AT25-41253) in the Actuarial Science program at Institut Teknologi Sumatera. The materials are designed specifically for actuarial science students with no prior coding experience, using medical insurance cost prediction as a practical case study.

The course uses a real-world dataset to teach fundamental machine learning concepts, with all explanations in **Bahasa Indonesia** and technical terms in English for better understanding.

---

## 🎯 Learning Objectives

Students will learn to:
- Prepare and preprocess data for machine learning applications
- Understand and implement **Support Vector Machine (SVM)** for regression
- Perform hyperparameter tuning using GridSearchCV
- Evaluate model performance using multiple metrics (R², MAE, RMSE, MAPE)
- Apply machine learning concepts to actuarial problems
- Make data-driven decisions for insurance pricing

---

## 📂 Repository Contents

### **Notebooks**

1. **`week10-1.ipynb`** - Data Preparation (Section 1)
   - Import libraries and load dataset
   - Data exploration and understanding
   - Missing value handling
   - Train-validation split (80-20)
   - Data visualization
   - Checkpoint questions for learning verification

2. **`week10-2.ipynb`** - SVM Training (Section 2)
   - Feature encoding (Label Encoding & One-Hot Encoding)
   - Feature scaling with StandardScaler
   - Baseline SVM model training
   - Model evaluation with multiple metrics
   - Hyperparameter tuning with GridSearchCV
   - Model comparison and selection
   - Comprehensive explanations for actuarial context

3. **`medical_insurance_notebook.ipynb`** - Additional exploratory notebook
4. **`visualisasi_data.ipynb`** - Data visualization examples

### **Data Files**

- **`medical_insurance.csv`** - Main dataset (100,000+ insurance policies)
- **`train_data.csv`** - Training set (80% of data)
- **`validation_data.csv`** - Validation set (20% of data)

### **Dataset Information**

The dataset contains medical insurance information with 52 features including:
- **Demographics:** age, sex, region, marital status, education
- **Health factors:** BMI, smoking status, alcohol frequency, chronic conditions
- **Insurance details:** plan type, network tier, premium amount, claims
- **Target variable:** `annual_medical_cost` (continuous)

**Dataset Source:**
```bibtex
@misc{mosap_abdelghany_2025,
	title={Medical Insurance Cost Dataset},
	url={https://www.kaggle.com/dsv/12853160},
	DOI={10.34740/KAGGLE/DSV/12853160},
	publisher={Kaggle},
	author={mosap abdelghany},
	year={2025}
}
```

---

## 🛠️ Environment Setup

### **Prerequisites**

- **Python 3.8+** (Python 3.10 recommended)
- **Jupyter Notebook** or **VS Code** with Jupyter extension
- **Miniconda** or **Anaconda** (recommended for environment management)

### **Installation Steps**

#### **Option 1: Using Conda (Recommended)**

```bash
# Clone the repository
git clone https://github.com/mctosima/AT25-41253-_-Statistical-Machine-Learning.git
cd "AT25-41253-_-Statistical-Machine-Learning"

# Create a new conda environment
conda create -n sml_course python=3.10 -y

# Activate the environment
conda activate sml_course

# Install required packages
pip install pandas numpy scikit-learn matplotlib seaborn jupyter
```

#### **Option 2: Using pip with venv**

```bash
# Clone the repository
git clone https://github.com/mctosima/AT25-41253-_-Statistical-Machine-Learning.git
cd "AT25-41253-_-Statistical-Machine-Learning"

# Create virtual environment
python -m venv venv

# Activate virtual environment
# On macOS/Linux:
source venv/bin/activate
# On Windows:
venv\Scripts\activate

# Install required packages
pip install pandas numpy scikit-learn matplotlib seaborn jupyter
```

### **Required Packages**

```
pandas>=1.5.0
numpy>=1.23.0
scikit-learn>=1.2.0
matplotlib>=3.6.0
seaborn>=0.12.0
jupyter>=1.0.0
```

---

## 🚀 How to Run

### **1. Start Jupyter Notebook**

```bash
# Activate your environment first
conda activate sml_course  # or: source venv/bin/activate

# Start Jupyter Notebook
jupyter notebook
```

Your browser will open automatically. Navigate to the notebook you want to run.

### **2. Run with VS Code**

1. Open the repository folder in VS Code
2. Install the **Jupyter extension** (ms-toolsai.jupyter)
3. Open any `.ipynb` file
4. Select your Python environment (conda/venv)
5. Run cells sequentially using `Shift + Enter`

### **3. Recommended Learning Path**

Follow this sequence for optimal learning:

```
1. week10-1.ipynb (Data Preparation)
   ↓
2. week10-2.ipynb (SVM Training)
   ↓
3. Practice with your own experiments
```

**Important Notes:**
- ✅ Run cells **sequentially** from top to bottom
- ✅ Read the markdown explanations carefully
- ✅ Answer the checkpoint questions before checking solutions
- ✅ Experiment with code after understanding the concepts

---

## 📊 Key Concepts Covered

### **Machine Learning Fundamentals**
- Supervised learning for regression
- Train-validation split strategy
- Data preprocessing pipelines
- Model evaluation metrics

### **Support Vector Machine (SVM)**
- SVR (Support Vector Regression) theory
- Kernel functions (linear, RBF, polynomial)
- Hyperparameters: C, epsilon, gamma
- Support vectors concept

### **Data Preprocessing**
- Label Encoding for ordinal variables
- One-Hot Encoding for nominal variables
- Feature scaling with StandardScaler
- Handling missing values

### **Model Optimization**
- GridSearchCV for hyperparameter tuning
- Cross-validation strategies
- Overfitting vs underfitting
- Model selection criteria

### **Evaluation Metrics**
- **R² Score** - Coefficient of determination
- **MAE** - Mean Absolute Error (dollar terms)
- **RMSE** - Root Mean Squared Error
- **MAPE** - Mean Absolute Percentage Error

---

## 🎓 Educational Features

### **Beginner-Friendly Design**
- All explanations in Bahasa Indonesia
- No coding background required
- Step-by-step instructions with analogies
- Visual aids and diagrams

### **Interactive Learning**
- Checkpoint questions in notebooks
- Expandable solution sections
- Hands-on code examples
- Real-world actuarial context

### **Actuarial Focus**
- Insurance pricing applications
- Risk management considerations
- Regulatory compliance insights
- Production deployment guidance

---

## 💡 Tips for Students

1. **Don't rush!** Read explanations carefully before running code
2. **Experiment!** Try changing parameters to see what happens
3. **Ask questions!** Use checkpoint questions to test understanding
4. **Take notes!** Document your learnings and observations
5. **Practice!** Try applying concepts to other datasets

### **Common Issues & Solutions**

**Issue:** `ModuleNotFoundError: No module named 'sklearn'`  
**Solution:** Install scikit-learn: `pip install scikit-learn`

**Issue:** Plots not showing in Jupyter  
**Solution:** Add `%matplotlib inline` at the top of notebook

**Issue:** Kernel crashes during GridSearchCV  
**Solution:** Reduce parameter grid size or use fewer cv folds

**Issue:** Warning about emoji glyphs  
**Solution:** Already handled with `warnings.filterwarnings()` in code

---

## 📚 Additional Resources

### **Recommended Reading**
- [Scikit-learn Documentation](https://scikit-learn.org/stable/)
- [Pandas User Guide](https://pandas.pydata.org/docs/user_guide/index.html)
- [Understanding SVMs](https://scikit-learn.org/stable/modules/svm.html)

### **Further Learning**
- XGBoost for ensemble methods
- Deep learning for actuarial applications
- Time series forecasting
- Model deployment strategies

---

## 🤝 Contributing

This is an educational repository for Institut Teknologi Sumatera students. If you find any issues or have suggestions for improvement:

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Submit a pull request

---

## 📧 Contact

**Instructor:** Martin C.T. Manullang  
**Course Code:** AT25-41253  
**Institution:** Institut Teknologi Sumatera  

For questions about the course materials, please contact through official university channels.

---

## 📄 License

This educational material is provided for students of Institut Teknologi Sumatera. Please respect academic integrity policies when using these materials.

---

## 🙏 Acknowledgments

- **Dataset:** mosap abdelghany via Kaggle
- **Institution:** Institut Teknologi Sumatera - Actuarial Science Program
- **Students:** AT25-41253 cohort for valuable feedback

---

**Happy Learning! 🚀📊**

*Last Updated: October 26, 2025*
