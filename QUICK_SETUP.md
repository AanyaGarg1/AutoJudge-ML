# AutoJudge: Quick Setup Guide

## 🚀 Quick Start (5 Minutes)

This guide will get your project running locally in 5 minutes.

---

## Prerequisites

- **Node.js** v16+ ([Download](https://nodejs.org/))
- **Git** ([Download](https://git-scm.com/downloads))

Check installations:
```bash
node --version    # Should be v16+
python --version  # Should be 3.8+
git --version
```

---

## Step 1: Clone Repository (30 seconds)

```bash
git clone https://github.com/AanyaGarg1/AutoJudge-ML.git
cd AutoJudge-ML
```

---

## Step 2: Install Dependencies (2 minutes)

### Backend (Node.js)
```bash
npm install
```

### Frontend (React)
```bash
cd frontend
npm install
cd ..
```

### Python (ML Training)
```bash
pip install -r requirements.txt
```

Or if you have both Python 2 and 3:
```bash
pip3 install -r requirements.txt
```

---

## Step 3: Train Models (1 minute)

### Option A: Python Models (Recommended)
```bash
python train_model_python.py
```

This will:
- Load dataset from `problems.csv`
- Extract 45 features per problem
- Train Random Forest Classifier
- Train Random Forest Regressor
- Show evaluation metrics in console
- Save models as `classifier_model.pkl` and `regressor_model.pkl`

### Option B: JavaScript Models (Alternative)
```bash
node train_model.js
```

This saves models in `model.json`.

---

## Step 4: Run Application (30 seconds)

You need **two terminal windows**:

### Terminal 1 - Backend Server
```bash
node server.js
```

You should see:
```
Server running at http://localhost:3000
Models loaded successfully!
```

### Terminal 2 - Frontend Dev Server
```bash
cd frontend
npm run dev
```

You should see:
```
  ➜  Local:   http://localhost:5173/
```

---

## Step 5: Test the Application (1 minute)

1. Open browser to **http://localhost:5173**
2. Enter a problem description, for example:
   - **Easy:** "Find the sum of all elements in an array"
   - **Medium:** "Implement binary search tree with insertion and search"
   - **Hard:** "Find maximum flow in a graph using Edmonds-Karp algorithm"
3. Click **"Predict Difficulty"**
4. See the predicted class and score!

---

## 🎯 Quick Test Commands

### Test Python Prediction Script
```bash
python predict.py --demo
```

This runs 3 test cases and shows predictions.

### Test Interactive Mode
```bash
python predict.py --interactive
```

Enter problems interactively and get predictions.

---

## 📁 Project Structure Overview

```
AutoJudge-ML/
│
├── README.md                    # Complete documentation
├── SUBMISSION_CHECKLIST.md      # What you need to submit
├── QUICK_SETUP.md              # This file
├── report.pdf                   # Project report (YOU NEED TO CREATE)
│
├── Python ML Scripts
│   ├── train_model_python.py   # Train models
│   ├── predict.py              # Make predictions
│   ├── generate_dataset.py     # Generate data
│   └── requirements.txt        # Python dependencies
│
├── JavaScript Backend
│   ├── server.js               # Express API server
│   ├── train_model.js          # JS model training
│   ├── model.json              # Trained models (25MB)
│   └── package.json            # Node dependencies
│
├── Data
│   └── problems.csv            # Training dataset (1000+ samples)
│
└── frontend/                   # React Web UI
    ├── src/
    │   ├── App.jsx            # Main component
    │   └── App.css            # Styling
    └── package.json            # Frontend dependencies
```

---

## 🐛 Troubleshooting

### Issue: "Cannot find module 'pandas'"
**Solution:**
```bash
pip install -r requirements.txt
```

### Issue: "Port 3000 already in use"
**Solution:** Kill the process or change port in `server.js`:
```javascript
const PORT = 3001;  // Change from 3000
```

### Issue: "Model file not found"
**Solution:** Train the models first:
```bash
python train_model_python.py
```

### Issue: Frontend shows CORS error
**Solution:** Make sure backend is running on port 3000 first.

### Issue: npm install fails
**Solution:**
```bash
npm cache clean --force
npm install
```

---

## ✅ Verify Everything Works

Run this checklist:

- [ ] Backend starts: `node server.js` ✓
- [ ] Frontend starts: `cd frontend && npm run dev` ✓
- [ ] Can access http://localhost:5173 ✓
- [ ] Predictions work correctly ✓
- [ ] Python script runs: `python predict.py --demo` ✓

---

## 🎬 Next Steps for Submission

1. **Update README.md**
   - Add your name
   - Add demo video link

2. **Create report.pdf**
   - Use `REPORT_TEMPLATE.md` as base
   - Add your metrics and screenshots
   - Convert to PDF (4-8 pages)

3. **Record demo video**
   - 2-3 minutes
   - Show training, web UI, predictions
   - Upload to YouTube/Drive

4. **Push to GitHub**
   ```bash
   git add .
   git commit -m "Final submission"
   git push
   ```

5. **Review SUBMISSION_CHECKLIST.md**
   - Ensure all items are checked

---

## 📞 Support

If you encounter issues:

1. Check `SUBMISSION_CHECKLIST.md` section 11 (Common Issues)
2. Ensure all prerequisites are installed
3. Try running commands one by one
4. Check console for error messages

---

## 🚀 You're All Set!

The project is ready to run. Focus on:
- Creating your `report.pdf`
- Recording your demo video
- Adding your personal details to README

**Good luck! 🎉**
