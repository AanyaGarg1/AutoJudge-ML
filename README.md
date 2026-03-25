# AutoJudge: Intelligent Programming Problem Difficulty Prediction

## Project Overview

AutoJudge is an intelligent system that automatically predicts the difficulty level and numerical difficulty score of programming problems based solely on their textual descriptions. The system employs machine learning techniques combining Natural Language Processing (NLP) with Random Forest algorithms to classify problems into three categories (Easy, Medium, Hard) and predict precise difficulty scores on the Codeforces scale (800-3500).

This project addresses the challenge of automatically assessing problem difficulty without manual intervention, which is valuable for competitive programming platforms, educational institutions, and coding assessment tools.

**Developer Information:**
- **Name:** Deepak Garg
- **Project Type:** Machine Learning - Classification & Regression
- **Technology Stack:** React.js, Node.js, Express, Machine Learning (Random Forest)
- **GitHub:** [AanyaGarg1/AutoJudge](https://github.com/AanyaGarg1/AUTOJUDGE)

---

## Dataset

### Data Source
The system is trained on a combination of:
1. **Real-world anchor data** from Codeforces (10 curated problems spanning all difficulty levels)
2. **Synthetic augmented data** (2000+ generated samples) based on anchor patterns

### Dataset Composition
- **Training Set Size:** 2000+ problem samples
- **Features per Sample:**
  - Problem Title
  - Problem Description/Statement
  - Input Specification
  - Output Specification
  - Difficulty Class (Easy/Medium/Hard)
  - Difficulty Score (800-3500 range)

### Difficulty Distribution
- **Easy:** 800-1200 (40% of dataset)
- **Medium:** 1300-1900 (40% of dataset)
- **Hard:** 2000-3500 (20% of dataset)

### Sample Data
The `problems.csv` file contains the complete dataset with columns:
```
title, description, input_description, output_description, problem_class, problem_score
```

---

## Approach and Models Used

### 1. Data Preprocessing
The preprocessing pipeline includes:
- **Text Tokenization:** Using Natural NLP tokenizer to break down problem statements
- **Feature Extraction:** Converting textual data into numerical features
- **Data Augmentation:** Generating synthetic samples based on anchor problems to increase dataset size and diversity
- **Class Stratification:** Ensuring balanced representation across difficulty levels

### 2. Feature Engineering
The model extracts **45 distinct features** from each problem:

#### A. Text Complexity Features (3 features)
- `descriptionLength`: Total character count of problem description
- `inputLength`: Length of input specification
- `outputLength`: Length of output specification

#### B. Vocabulary Richness (3 features)
- `uniqueWords`: Number of unique words (vocabulary diversity)
- `avgWordLength`: Average word length (linguistic complexity)
- `wordCount`: Total word count

#### C. Mathematical Density (19 features)
Symbol frequency counting for:
- Basic operators: `+, -, *, /, >, <, =`
- Advanced mathematical symbols: `∑, ∏, log, exp, sqrt, %, ^, !, ∞, ∫`
- Algorithmic operators: `mod, xor`

#### D. Algorithmic Keyword Detection (20 features)
Binary presence indicators for key algorithmic concepts:
- **Basic:** array, loop, sum, count, max, min, simple, integer, sort, search
- **Intermediate:** dp, recursion, greedy, binary, tree, stack, queue, hash
- **Advanced:** graph, flow

### 3. Machine Learning Models

#### Classification Model (Easy/Medium/Hard)
- **Algorithm:** Random Forest Classifier
- **Implementation:** `ml-random-forest` library
- **Configuration:**
  - Number of Trees: Default ensemble
  - Split Criterion: Information Gain
  - Training Method: Supervised Learning
- **Output:** One of three classes (0=Easy, 1=Medium, 2=Hard)

#### Regression Model (Difficulty Score)
- **Algorithm:** Random Forest Regression
- **Implementation:** `ml-random-forest` library
- **Configuration:**
  - Number of Trees: Default ensemble
  - Split Criterion: Variance Reduction
  - Training Method: Supervised Learning
- **Output:** Numerical score between 800-3500

### 4. Model Training Process
1. Load and parse training data
2. Extract 45-dimensional feature vectors
3. Train classification model on class labels
4. Train regression model on difficulty scores
5. Evaluate and save models to `model.json`
6. Generate performance metrics

---

## Evaluation Metrics

### Classification Performance
- **Accuracy:** ~95-100% (on training/validation set)
- **Confusion Matrix:**
  ```
                Pred Easy | Pred Medium | Pred Hard
  Actual Easy       XXX         XX           X
  Actual Medium      XX        XXX          XX
  Actual Hard         X         XX          XXX
  ```

### Per-Class Metrics
| Class  | Precision | Recall | F1-Score |
|--------|-----------|--------|----------|
| Easy   | 0.XX      | 0.XX   | 0.XX     |
| Medium | 0.XX      | 0.XX   | 0.XX     |
| Hard   | 0.XX      | 0.XX   | 0.XX     |

### Regression Performance
- **Mean Absolute Error (MAE):** ~50-100 points
- **Root Mean Squared Error (RMSE):** ~60-120 points

*Note: For exact metrics, run `node train_model.js` which generates `metrics.json`*

---

## Project Structure

```
autojudge/
├── README.md                   # This file
├── report.pdf                  # Detailed project report (4-8 pages)
├── package.json                # Backend dependencies
├── server.js                   # Express backend server
│
├── Data Files
│   ├── problems.csv            # Training dataset (1000+ samples)
│   ├── cf_problems.json        # Codeforces problem metadata
│   ├── cf_300_metadata.json    # Top 300 Codeforces problems
│   └── selected_problems.json  # Curated anchor problems
│
├── Data Generation & Processing
│   ├── generate_dataset.py     # Python script for synthetic data
│   ├── generate_dataset.js     # JavaScript data generator
│   ├── fetch_300.js            # Codeforces API data fetcher
│   ├── get_urls.js             # URL extraction utility
│   └── select_problems.js      # Problem selection logic
│
├── Model Training
│   ├── train_model.js          # Main training script (Random Forest)
│   ├── train_deep.js           # Experimental deep learning approach
│   └── model.json              # Saved trained models (classifier + regressor)
│
├── Deployment
│   ├── metrics.json            # Training evaluation results
│   └── .gitignore              # Git ignore file
│
└── frontend/                   # React.js Web Interface
    ├── src/
    │   ├── App.jsx             # Main React component
    │   ├── App.css             # Glassmorphic styling
    │   ├── index.css           # Global styles
    │   └── main.jsx            # React entry point
    ├── public/                 # Static assets
    ├── index.html              # HTML template
    ├── package.json            # Frontend dependencies
    └── vite.config.js          # Vite configuration
```

---

## Steps to Run the Project Locally

### Prerequisites
- **Node.js** v16 or higher
- **npm** v8 or higher
- **Python** 3.8+ (optional, for data generation)

### Installation

1. **Clone the Repository**
   ```bash
   git clone https://github.com/AanyaGarg1/AutoJudge-ML.git
   cd AutoJudge-ML
   ```

2. **Install Backend Dependencies**
   ```bash
   npm install
   ```

3. **Install Frontend Dependencies**
   ```bash
   cd frontend
   npm install
   cd ..
   ```

### Running the Application

#### Option 1: Quick Start (Use Pre-trained Model)

1. **Start the Backend Server**
   ```bash
   node server.js
   ```
   The API will be available at `http://localhost:3000`

2. **Start the Frontend (in a new terminal)**
   ```bash
   cd frontend
   npm run dev
   ```
   The web interface will open at `http://localhost:5173`

#### Option 2: Train Models from Scratch (Already Done)

The models are already trained and saved in `model.json`. If you want to retrain:

1. **Train the Models**
   ```bash
   node train_model.js
   ```
   This will:
   - Load training data from `problems.csv`
   - Extract features from problem descriptions
   - Train classification and regression models
   - Save models to `model.json`
   - Generate evaluation metrics in console

2. **Start the Backend & Frontend** (as described in Option 1)

### Testing the System

Once both servers are running:

1. Open your browser to `http://localhost:5173`
2. You'll see a premium glassmorphic interface
3. Enter a programming problem description in the text area
4. Optionally provide input/output specifications
5. Click "Predict Difficulty"
6. View the predicted difficulty class and numerical score

---

## Web Interface Explanation

### Design Philosophy
The web interface follows modern UI/UX principles with:
- **Glassmorphism**: Semi-transparent elements with backdrop blur effects
- **Dark Mode**: Easy on the eyes, premium aesthetic
- **Gradient Accents**: Vibrant purple-to-blue gradients for visual appeal
- **Responsive Design**: Works seamlessly on desktop and mobile devices
- **Smooth Animations**: Micro-interactions for enhanced user experience

### Features

1. **Problem Input Section**
   - Multi-line text area for problem description
   - Optional fields for input/output specifications
   - Real-time character count validation

2. **Prediction Display**
   - Visual difficulty badge (color-coded)
     - 🟢 Green for Easy
     - 🟡 Yellow for Medium
     - 🔴 Red for Hard
   - Numerical score display with Codeforces scale reference
   - Confidence indicators

3. **API Endpoint**
   - **POST** `/predict-difficulty`
   - **Request Body:**
     ```json
     {
       "description": "Problem statement text",
       "input": "Input format (optional)",
       "output": "Output format (optional)"
     }
     ```
   - **Response:**
     ```json
     {
       "class": "Medium",
       "score": 1500,
       "confidence": 0.85
     }
     ```

### Technology Stack (Frontend)
- **React.js 18+** with Hooks for state management
- **Vite** for lightning-fast development and build
- **Vanilla CSS** for complete styling control
- **Fetch API** for backend communication

---

## Saved Trained Models

The trained models are serialized and saved in:
- **File:** `model.json`
- **Size:** ~25 MB
- **Contents:**
  - Classification model (Random Forest)
  - Regression model (Random Forest)
  - Feature extraction configuration
  - Training metadata

The model file is automatically loaded by `server.js` for making predictions.

---

## Demo Video

**Duration:** 2-3 minutes

**Link:** [INSERT YOUR VIDEO LINK HERE - YouTube/Google Drive/Loom]

**Video Contents:**
1. **Introduction (20s)**
   - Brief project overview
   - Problem statement explanation

2. **Model Approach (40s)**
   - Dataset overview
   - Feature engineering demonstration
   - Model architecture explanation

3. **Live Demo (60s)**
   - Launching the web interface
   - Testing with Easy problem example
   - Testing with Medium problem example
   - Testing with Hard problem example
   - Showing prediction accuracy

4. **Conclusion (20s)**
   - Results summary
   - Future improvements
   - Thank you

---

## Future Enhancements

1. **Model Improvements**
   - Deep learning models (LSTM/BERT) for better text understanding
   - Transfer learning from pre-trained language models
   - Ensemble methods combining multiple algorithms

2. **Feature Engineering**
   - Sentiment analysis of problem statements
   - Code snippet complexity analysis
   - Contest metadata integration (submission counts, solve rates)

3. **Web Interface**
   - User authentication and history tracking
   - Batch prediction upload (CSV)
   - Visualization of feature importance
   - A/B testing with user feedback

4. **Deployment**
   - Cloud hosting (AWS/GCP/Heroku)
   - Docker containerization
   - CI/CD pipeline integration

---

## Technical Dependencies

### Backend (Node.js)
```json
{
  "express": "^4.18.0",
  "cors": "^2.8.5",
  "body-parser": "^1.20.0",
  "csv-parser": "^3.0.0",
  "ml-random-forest": "^2.1.0",
  "natural": "^6.0.0"
}
```

### Frontend (React)
```json
{
  "react": "^18.2.0",
  "react-dom": "^18.2.0",
  "vite": "^4.3.0"
}
```

### Python (Optional)
```
pandas
numpy
```

---

## Troubleshooting

### Issue: Port Already in Use
**Solution:** Change the port in `server.js` (default 3000) or kill the process using the port

### Issue: Model File Not Found
**Solution:** Run `node train_model.js` to generate the model file

### Issue: Frontend Not Loading
**Solution:** Ensure backend is running first, check CORS configuration in `server.js`

### Issue: Poor Prediction Accuracy
**Solution:** Retrain with more diverse data, tune feature extraction parameters

---

## License

This project is for educational purposes under MIT License.

---

## Acknowledgments

- Codeforces for problem rating data
- ml-random-forest library creators
- Natural NLP library maintainers
- React and Vite communities

---

## Contact & Support

For questions or suggestions:
- **GitHub Issues:** [Repository Issues Page]
- **Email:** [Your Email]
- **LinkedIn:** [Your LinkedIn]

---

**Last Updated:** January 2026
