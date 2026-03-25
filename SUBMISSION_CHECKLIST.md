# AutoJudge Project Submission Checklist

## 📋 Pre-Submission Checklist

Use this checklist to ensure you have everything ready for submission.

---

## ✅ 1. Complete Source Code

### Data Preprocessing
- [ ] `generate_dataset.py` - Python data generation script ✓
- [ ] `generate_dataset.js` - JavaScript data generation script ✓
- [ ] `problems.csv` - Generated dataset (1000+ samples) ✓

### Feature Extraction
- [ ] Feature extraction function in `train_model_python.py` (lines 30-87) ✓
- [ ] Feature extraction function in `train_model.js` ✓
- [ ] 45 features implemented (text complexity, vocabulary, math density, keywords) ✓

### Classification Model (Easy/Medium/Hard)
- [ ] `train_model_python.py` - Python Random Forest Classifier ✓
- [ ] `train_model.js` - JavaScript Random Forest Classifier ✓
- [ ] Model saved as `classifier_model.pkl` (Python) ✓
- [ ] Model saved in `model.json` (JavaScript) ✓

### Regression Model (Difficulty Score)
- [ ] Python Random Forest Regressor in `train_model_python.py` ✓
- [ ] JavaScript Random Forest Regressor in `train_model.js` ✓
- [ ] Model saved as `regressor_model.pkl` (Python) ✓
- [ ] Model saved in `model.json` (JavaScript) ✓

### Web UI Code
- [ ] `frontend/src/App.jsx` - Main React component ✓
- [ ] `frontend/src/App.css` - Glassmorphic styling ✓
- [ ] `server.js` - Backend Express API ✓
- [ ] Prediction endpoint `/predict-difficulty` implemented ✓

---

## ✅ 2. README.md

Your README.md should include:

- [ ] **Project Overview** - Clear description of AutoJudge ✓
- [ ] **Dataset Used** - Description of data sources and statistics ✓
- [ ] **Approach and Models Used** - Random Forest classification & regression ✓
- [ ] **Evaluation Metrics** - Accuracy, MAE, RMSE, Confusion Matrix ✓
- [ ] **Steps to Run Locally** - Installation and execution instructions ✓
- [ ] **Web Interface Explanation** - Features and usage guide ✓
- [ ] **Demo Video Link** - 2-3 minute video (TO BE ADDED) ⚠️
- [ ] **Your Name and Details** - Author information (TO BE ADDED) ⚠️

**Action Required:**
1. Open `README.md`
2. Search for `[Your Name Here]` and replace with your actual name
3. Search for `[Insert YouTube/Drive Link Here]` and add your demo video link
4. Add any other personal details (email, LinkedIn, etc.)

---

## ✅ 3. Saved Trained Models

### Python Models
- [ ] Train models: Run `python train_model_python.py`
- [ ] Verify `classifier_model.pkl` exists
- [ ] Verify `regressor_model.pkl` exists
- [ ] Verify `python_metrics.json` exists

### JavaScript Models
- [ ] Train models: Run `node train_model.js`
- [ ] Verify `model.json` exists (should be ~25MB)
- [ ] Verify `metrics.json` exists

**Commands to Run:**
```bash
# Python (recommended for submission)
pip install -r requirements.txt
python train_model_python.py

# JavaScript (already done)
node train_model.js
```

---

## ✅ 4. Demo Video (MANDATORY)

Create a **2-3 minute** demo video showing:

### Video Structure:
1. **Introduction (20-30 seconds)**
   - "Hi, I'm [Your Name], presenting AutoJudge"
   - Brief problem statement explanation

2. **Model Approach (40-50 seconds)**
   - Show dataset file (`problems.csv`)
   - Explain features: "We extract 45 features including text complexity, mathematical density, and algorithmic keywords"
   - Show model training: Run `python train_model_python.py` (speed up if needed)
   - Show accuracy: "We achieved 95%+ accuracy and MAE of ~87 points"

3. **Web UI Demo (60-80 seconds)**
   - Start backend: `node server.js`
   - Start frontend: `cd frontend && npm run dev`
   - Test Easy problem: "Find sum of array" → Shows Easy, 850
   - Test Medium problem: "Binary search tree with recursion" → Shows Medium, 1450
   - Test Hard problem: "Maximum flow Edmonds-Karp" → Shows Hard, 2300

4. **Conclusion (20 seconds)**
   - "Thank you! This system can help educational platforms and competitive programming sites"

### Recording Tools:
- **OBS Studio** (Free, professional)
- **Loom** (Easy, shareable link)
- **Windows Game Bar** (Win + G)
- **Camtasia** (Paid, editing features)

### Upload Options:
- YouTube (Unlisted)
- Google Drive (Public link)
- Loom (Direct link)

**Action Required:**
- [ ] Record demo video
- [ ] Upload to YouTube/Drive/Loom
- [ ] Add link to README.md

---

## ✅ 5. Project Report (report.pdf)

You have a template: `REPORT_TEMPLATE.md`

### Steps to Complete Report:

1. **Fill in Personal Details**
   - Replace `[Your Full Name]`, `[Your Roll Number]`, `[Course Name]`

2. **Add Actual Metrics**
   - Run training and copy metrics from console
   - Update Section 6 (Results & Evaluation)
   - Insert actual confusion matrix numbers
   - Insert actual MAE/RMSE values

3. **Add Figures/Screenshots**
   - Confusion matrix heatmap (can create in Excel/Python)
   - Predicted vs Actual scatter plot
   - Web interface screenshots (3 examples: Easy, Medium, Hard)
   - Training output screenshot

4. **Convert to PDF**
   
   **Option A: Using Pandoc (Best Quality)**
   ```bash
   # Install pandoc first: https://pandoc.org/installing.html
   pandoc REPORT_TEMPLATE.md -o report.pdf --pdf-engine=xelatex
   ```
   
   **Option B: VS Code Extension**
   - Install "Markdown PDF" extension
   - Right-click `REPORT_TEMPLATE.md` → "Markdown PDF: Export (pdf)"
   
   **Option C: Online Tool**
   - Visit https://www.markdowntopdf.com/
   - Upload `REPORT_TEMPLATE.md`
   - Download as `report.pdf`
   
   **Option D: Google Docs/Word**
   - Copy content to Google Docs
   - Format properly (headings, tables, etc.)
   - Insert screenshots
   - Export as PDF

5. **Verify Report Contents**
   - [ ] 4-8 pages in length
   - [ ] All 9 sections included
   - [ ] Personal details filled
   - [ ] Actual metrics inserted
   - [ ] Screenshots/figures included
   - [ ] Properly formatted
   - [ ] Named as `report.pdf`

---

## ✅ 6. Final Repository Structure

Your final GitHub repository should look like this:

```
AutoJudge-ML/
├── README.md                       ✓ Complete with your details
├── report.pdf                      ⚠️ TO BE CREATED
├── requirements.txt                ✓
├── package.json                    ✓
├── .gitignore                      ✓
│
├── Data Files
│   ├── problems.csv                ✓
│   ├── cf_problems.json            ✓
│   └── selected_problems.json      ✓
│
├── Python ML (Recommended for Submission)
│   ├── train_model_python.py       ✓ Complete training script
│   ├── predict.py                  ✓ Prediction script
│   ├── generate_dataset.py         ✓ Data generation
│   ├── classifier_model.pkl        ⚠️ Run training to generate
│   ├── regressor_model.pkl         ⚠️ Run training to generate
│   └── python_metrics.json         ⚠️ Run training to generate
│
├── JavaScript ML (Alternative)
│   ├── train_model.js              ✓
│   ├── server.js                   ✓ Backend API
│   ├── model.json                  ✓ Trained models
│   └── metrics.json                ✓
│
└── frontend/                       ✓ React Web UI
    ├── src/
    │   ├── App.jsx
    │   ├── App.css
    │   └── main.jsx
    ├── index.html
    ├── package.json
    └── vite.config.js
```

---

## ✅ 7. Testing Before Submission

### Test 1: Fresh Clone Test
```bash
# Clone your repo in a new location
git clone https://github.com/AanyaGarg1/AutoJudge-ML.git test-clone
cd test-clone

# Test Python setup
pip install -r requirements.txt
python train_model_python.py
python predict.py --demo

# Test JavaScript setup
npm install
cd frontend && npm install && cd ..
node server.js
# In another terminal: cd frontend && npm run dev
```

### Test 2: Check All Files Exist
- [ ] README.md exists and is complete
- [ ] report.pdf exists (4-8 pages)
- [ ] Trained models exist (`.pkl` files or `model.json`)
- [ ] Web UI runs without errors
- [ ] Demo video link works

### Test 3: Run Locally
- [ ] Backend starts: `node server.js`
- [ ] Frontend starts: `cd frontend && npm run dev`
- [ ] Predictions work correctly
- [ ] UI is responsive and looks good

---

## ✅ 8. GitHub Repository

### Repository Setup
- [ ] Repository is public (or shared with evaluator)
- [ ] Repository name: `AutoJudge-ML` or similar
- [ ] Has proper `.gitignore` (exclude `node_modules/`, `*.pkl`, etc.)

### Commit Everything
```bash
git add .
git commit -m "Final submission: Complete AutoJudge ML project"
git push origin main
```

### Important Files to Include:
- [ ] All source code files
- [ ] README.md
- [ ] report.pdf
- [ ] requirements.txt
- [ ] package.json files
- [ ] Trained model files (`.pkl` or `.json`)
- [ ] Dataset (problems.csv)

### Optional but Good to Include:
- [ ] Screenshots folder with web UI images
- [ ] Demo video (if small enough, otherwise just link in README)
- [ ] LICENSE file (MIT recommended)

---

## ✅ 9. Common Mistakes to Avoid

❌ **Don't Submit Without:**
- Demo video (mandatory!)
- Actual trained models
- Completed README with YOUR name
- Report.pdf file

❌ **Don't:**
- Leave placeholder text like "[Your Name]" in files
- Include node_modules in Git
- Submit without testing locally first
- Have broken links in README

✅ **Do:**
- Test everything locally before submission
- Use clear commit messages
- Include all metrics in report
- Make demo video clear and concise

---

## ✅ 10. Quick Pre-Submission Commands

Run these commands to prepare everything:

```bash
# 1. Install dependencies
pip install -r requirements.txt
npm install
cd frontend && npm install && cd ..

# 2. Train Python models (generates .pkl files)
python train_model_python.py

# 3. Test Python prediction
python predict.py --demo

# 4. Verify JavaScript models exist
ls model.json metrics.json

# 5. Test web UI
# Terminal 1:
node server.js

# Terminal 2:
cd frontend
npm run dev

# 6. Create report.pdf from template
# (Use one of the methods in Section 5)

# 7. Record demo video
# (Use OBS/Loom - see Section 4)

# 8. Update README
# Add your name and demo video link

# 9. Final commit
git add .
git commit -m "Final submission ready"
git push
```

---

## ✅ 11. Submission Deadline Reminder

**Important Dates:**
- Submission deadline: [CHECK YOUR ASSIGNMENT]
- Demo video required: 2-3 minutes
- Report required: 4-8 pages

**What to Submit:**
1. GitHub repository link
2. Demo video link (in README, but also submit separately if required)
3. Ensure repository has README.md and report.pdf

---

## 📞 Need Help?

**Common Issues:**

1. **Python models not training?**
   - Run: `pip install -r requirements.txt`
   - Check Python version: `python --version` (need 3.8+)

2. **Frontend not starting?**
   - Run: `cd frontend && npm install`
   - Check Node version: `node --version` (need 16+)

3. **Can't create PDF report?**
   - Use online tool: https://www.markdowntopdf.com/
   - Or copy to Google Docs and export

4. **Demo video too large?**
   - Upload to YouTube (unlisted)
   - Use Loom (free, up to 5 min)
   - Compress with Handbrake

---

## ✅ Final Check

Before submitting, verify:
- [ ] ✅ All code files present
- [ ] ✅ README.md complete with your details
- [ ] ✅ report.pdf created (4-8 pages)
- [ ] ✅ Trained models saved
- [ ] ✅ Demo video recorded and linked
- [ ] ✅ Tested locally - everything works
- [ ] ✅ Repository pushed to GitHub
- [ ] ✅ Repository is public/accessible

---

## 🎉 You're Ready!

Once all items are checked, you're ready to submit!

**Good luck with your submission! 🚀**
