# 🧠 Alzheimer's Disease Risk Predictor

A Streamlit web app that estimates a person's risk of Alzheimer's disease from demographic, lifestyle, medical-history, clinical and cognitive data, using a tuned **XGBoost** classifier trained on **2,149 patient records**.

> ⚠️ **Disclaimer:** For research and educational use only. This is **not** a diagnostic tool and does not replace evaluation by a qualified healthcare professional.

## 🚀 Live Demo
**[Open the app](ADD-YOUR-STREAMLIT-LINK-HERE)**

## 🎯 Objective
Build a binary classifier that predicts whether a patient is at **higher or lower risk** of Alzheimer's disease, and deploy it as an easy-to-use web form that returns a risk label and probability.

## 📊 Dataset
- **Records:** 2,149 patients
- **Input features:** 32
- **Target:** Alzheimer's diagnosis (0 = No, 1 = Yes)
- **Source:** [ADD DATASET LINK, e.g. Kaggle]

| Feature group | Features |
|---|---|
| Demographics | Age, Gender, Ethnicity, EducationLevel |
| Lifestyle | BMI, Smoking, AlcoholConsumption, PhysicalActivity, DietQuality, SleepQuality |
| Medical history | FamilyHistoryAlzheimers, CardiovascularDisease, Diabetes, Depression, HeadInjury, Hypertension |
| Clinical measurements | SystolicBP, DiastolicBP, CholesterolTotal, CholesterolLDL, CholesterolHDL, CholesterolTriglycerides |
| Cognitive & functional | MMSE, FunctionalAssessment, MemoryComplaints, BehavioralProblems, ADL |
| Symptoms | Confusion, Disorientation, PersonalityChanges, DifficultyCompletingTasks, Forgetfulness |

## 🏆 Model Performance (held-out test set)

| Metric | Score |
|---|---|
| Accuracy | 94.4% |
| Precision | 93.8% |
| Recall | 90.1% |
| F1-score | 91.9% |
| ROC-AUC | 0.950 |

- **Algorithm:** XGBoost, tuned with GridSearchCV (5-fold cross-validation)
- **Top predictors:** MemoryComplaints, BehavioralProblems, MMSE, ADL, FunctionalAssessment
- **Reading the results:** Recall of 90.1% means about 1 in 10 true Alzheimer's cases is missed, which matters in a screening setting.

## 🖥️ App Features
- Interactive form with sliders and dropdowns for all 32 inputs
- Predicted **risk label** (higher / lower) with **probability score** and progress bar
- Model name, test accuracy and ROC-AUC shown at the top
- Built-in medical disclaimer

## 📁 Project Structure
```
├── app.py              # Streamlit app: input form + prediction
├── best_model.pkl      # Trained XGBoost classifier
├── scaler.pkl          # Fitted StandardScaler (kept for pipeline consistency)
├── model_info.json     # Feature list, scaling flag, test metrics
├── requirements.txt    # Python dependencies
└── README.md
```

## ⚙️ Run Locally
```bash
git clone https://github.com/YOUR-USERNAME/YOUR-REPO-NAME.git
cd YOUR-REPO-NAME
python3 -m venv venv
source venv/bin/activate        # Windows: venv\Scripts\activate
pip install -r requirements.txt
streamlit run app.py
```
The app opens at http://localhost:8501.

## ☁️ Deploy on Streamlit Community Cloud
1. Push all files to the **root** of a GitHub repository.
2. Go to [share.streamlit.io](https://share.streamlit.io) and sign in with GitHub.
3. Click **Create app**, choose your repo and the `main` branch.
4. Set **Main file path** to `app.py` and click **Deploy**.

## 🧰 Tech Stack
Python · Pandas · NumPy · Scikit-learn · XGBoost · Joblib · Streamlit

## ⚠️ Limitations
- Predictions are statistical estimates, not clinical diagnoses.
- Trained on a single dataset of 2,149 records, so performance may not carry over to other populations.
- Input values should stay within the ranges shown in the form (for example, age 60–90).

## 🔮 Future Improvements
- Add SHAP explanations for each individual prediction
- Validate on an external dataset
- Add imaging (MRI) features
- Predict disease stage, not only presence

## 👤 Author
Rushikesh Kasar · [GitHub]([https://github.com/YOUR-USERNAME](https://github.com/Kasar-Rushikesh/alzheimers-risk-predictor/new/main?filename=README.md)) 
· [LinkedIn](https://www.linkedin.com/in/rushikesh-kasar)

<img width="960" height="504" alt="Screenshot 2026-10-24 125527" src="https://github.com/user-attachments/assets/ffa00c77-cf8b-4855-a543-577eebea04e2" />

<img width="960" height="504" alt="Screenshot 2026-10-24 125542" src="https://github.com/user-attachments/assets/de76c5da-2515-4a7e-ab90-3aaffa50af25" />


<img width="960" height="504" alt="Screenshot 2026-10-24 125555" src="https://github.com/user-attachments/assets/7af641e6-dc86-43cf-abac-e047b2226997" />

<img width="960" height="504" alt="Screenshot 2026-10-24 125607" src="https://github.com/user-attachments/assets/005dacec-bf93-473b-bcae-ec939422a40c" />
<img width="960" height="504" alt="Screenshot 2026-10-24 125618" src="https://github.com/user-attachments/assets/4d072eef-0c7f-45d3-9e0c-3cbbb281756f" />
