# Bias-in-Ai
This project investigates gender-profession bias in pre-trained language models using the Bias-in-Bios dataset. The repository includes baseline and mitigated models, interpretable analyses, and WEAT effect size evaluation.

## Repository Structure
- `notebook.ipynb` – Full Colab notebook with all steps and visualizations
- `requirements.txt` – Python dependencies for reproducibility
- `README.md` – Project overview and results
- `outputs/` – Saved evaluation metrics, plots, and misclassified examples

## Methods
1. **Data Loading & Preprocessing**
   - Loaded Bias-in-Bios dataset
   - Conducted basic EDA and sanity checks

2. **Baseline Classification**
   - Encoded text with `SentenceTransformer`
   - Logistic Regression trained on embeddings
   - Evaluated accuracy, confusion matrices, demographic parity gap

3. **Error Analysis**
   - Identified misclassified samples
   - Grouped errors by profession

4. **Heuristic Simulations**
   - Availability heuristic: synthetic sentences with skewed gender terms
   - Anchoring heuristic: sentences with gendered prompts
   - Analyzed model predictions for bias tendencies

5. **Mitigation Experiments**
   - Counterfactual data augmentation (swapping gendered terms)
   - Class reweighting
   - Retrained models and evaluated mitigation effectiveness

6. **Interpretability**
   - SHAP LinearExplainer to understand embedding contributions
   - Coefficients linked to heuristics

7. **WEAT Analysis**
   - Male/female terms vs. Science/Arts terms
   - Computed effect size for baseline and mitigated models

## Results Summary
| Model           | Overall Accuracy | Male Accuracy | Female Accuracy | Demographic Parity Gap | WEAT Effect Size |
|-----------------|----------------|---------------|----------------|-----------------------|-----------------|
| Baseline        | 0.974          | 0.984         | 0.962          | 0.009                 | 0.0168          |
| CDA + Weighted  | 0.964          | 0.983         | 0.942          | 0.018                 | 0.0168          |

## Tools & Dependencies
- Python, Pandas, NumPy
- scikit-learn
- sentence-transformers
- matplotlib, seaborn
- SHAP

## Usage
1. Clone repository:  
   ```bash
   git clone https://github.com/jekeziem/Bias-in-AI.git
   cd Bias-in-AI
