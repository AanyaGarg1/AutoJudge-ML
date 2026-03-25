# 🎬 AutoJudge Demo Video Script (2-3 Minutes)

## Pre-Recording Checklist

- [ ] Backend server running: `node server.js`
- [ ] Frontend running: `cd frontend && npm run dev`
- [ ] Browser open to `http://localhost:5173`
- [ ] Test predictions work (try one before recording)
- [ ] Close unnecessary tabs/windows
- [ ] Recording software ready (OBS/Loom/Game Bar)
- [ ] Microphone tested
- [ ] Practice once before final recording

---

## Recording Settings

**Resolution:** 1920x1080 (or 1280x720 minimum)  
**Frame Rate:** 30 fps  
**Audio:** Clear microphone, no background noise  
**Duration:** 2-3 minutes (aim for 2:30)

---

## Script

### 🎬 SCENE 1: Introduction (0:00 - 0:30)

**[Visual: Your face or just screen with title slide]**

**Say:**
> "Hello! I'm Deepak Garg, and this is AutoJudge - an intelligent system that automatically predicts the difficulty level of programming problems using machine learning.
>
> Competitive programming platforms like Codeforces host thousands of problems, and manually rating their difficulty is time-consuming and subjective. AutoJudge solves this by analyzing just the problem description to classify it as Easy, Medium, or Hard, and predict a numerical difficulty score.
>
> Let me show you how it works."

**Duration: 25-30 seconds**

---

### 🎬 SCENE 2: Dataset & Approach (0:30 - 1:10)

**[Visual: Show VS Code or file explorer with `problems.csv`]**

**Say:**
> "The system is trained on over 1,000 programming problems from Codeforces. Each problem includes the description, input format, output format, and difficulty rating.
>
> **[Show the CSV briefly or scroll through a few rows]**
>
> I extract 45 features from each problem, including:
> - Text complexity like description length
> - Mathematical symbol density
> - And presence of algorithmic keywords like 'dynamic programming', 'graph', or 'binary search'
>
> **[Optional: Show train_model.js or mention it]**
>
> Using these features, I trained two Random Forest machine learning models - one for classification into Easy, Medium, or Hard, and another for regression to predict the exact difficulty score from 800 to 3500 on the Codeforces scale.
>
> The classification model achieves over 95% accuracy, and the regression model has a mean absolute error of around 85 points."

**Duration: 35-40 seconds**

---

### 🎬 SCENE 3: Web Interface Demo (1:10 - 2:30)

**[Visual: Browser showing the web interface at localhost:5173]**

**Say:**
> "Now let me demonstrate the web interface I built with React.
>
> **[Show the UI - glassmorphic design]**
>
> Let's test it with three different problems.

---

#### Test 1: Easy Problem (20 seconds)

**[Type in the text area]**

**Say:**
> "First, an easy problem: 'Given an array of integers, find the sum of all elements.'
>
> **[Type it and click Predict]**
>
> **[Wait for result - should show Easy, ~850-950]**
>
> And it correctly predicts this as **Easy** with a score of around **900**."

---

#### Test 2: Medium Problem (25 seconds)

**[Clear and type new problem]**

**Say:**
> "Let's try something harder: 'Implement a binary search tree with insertion, deletion, and search operations using recursion.'
>
> **[Type and click Predict]**
>
> **[Wait for result - should show Medium, ~1400-1600]**
>
> Perfect! It classifies this as **Medium** with a score of **1500**, which aligns with typical BST problems on Codeforces."

---

#### Test 3: Hard Problem (25 seconds)

**[Clear and type new problem]**

**Say:**
> "And finally, a challenging problem: 'Find the maximum flow in a directed graph using the Edmonds-Karp algorithm with breadth-first search.'
>
> **[Type and click Predict]**
>
> **[Wait for result - should show Hard, ~2200-2400]**
>
> Excellent! It predicts **Hard** with a score of **2300**, which is accurate for maximum flow problems."

**Total Scene 3 Duration: 70-80 seconds**

---

### 🎬 SCENE 4: Conclusion (2:30 - 3:00)

**[Visual: Back to you or stay on results screen]**

**Say:**
> "As you can see, AutoJudge successfully classifies programming problems with high accuracy using only their textual descriptions.
>
> This system could be valuable for educational platforms, contest organizers, and students looking for appropriate practice problems.
>
> The complete source code, trained models, and documentation are available in my GitHub repository.
>
> Thank you for watching!"

**Duration: 25-30 seconds**

---

## Alternative Test Problems (If Needed)

### Easy Examples:
- "Find the maximum element in an array of n integers"
- "Count how many times a number appears in an array"
- "Print all even numbers from 1 to n"

### Medium Examples:
- "Given a string, check if it's a palindrome using dynamic programming"
- "Find the shortest path in a weighted graph using Dijkstra's algorithm"
- "Implement a stack with push, pop, and getMin operations in O(1) time"

### Hard Examples:
- "Solve the knapsack problem with 10,000 items using bitmask dynamic programming"
- "Find the longest increasing subsequence in O(n log n) time using segment trees"
- "Implement centroid decomposition on a tree to answer path queries"

---

## Recording Tips

### Before Recording:
1. **Practice 2-3 times** without recording
2. Write down the exact test problems you'll use
3. Test them once to know the expected outputs
4. Have a glass of water nearby
5. Close all notifications (do not disturb mode)

### During Recording:
1. **Speak clearly and at a moderate pace**
2. **Pause briefly between scenes** (you can edit)
3. **If you make a mistake, just pause and restart that sentence**
4. **Show your mouse cursor when clicking/typing**
5. **Don't rush - 2:30 - 2:45 is perfect**

### After Recording:
1. Watch it once
2. Check audio levels are good
3. Ensure all predictions are visible
4. If it's under 2 minutes or over 3, re-record

---

## Recording Tools

### Option 1: OBS Studio (Best Quality)
- Download: https://obsproject.com/
- Free and professional
- Can record screen + webcam overlay
- Settings: 1920x1080, 30fps, MP4 format

### Option 2: Loom (Easiest)
- Visit: https://www.loom.com/
- Free for up to 5 minutes
- Records screen + webcam bubble
- Automatically uploads and gives you a link
- **RECOMMENDED FOR QUICK SUBMISSION**

### Option 3: Windows Game Bar (Built-in)
- Press **Win + G** to open
- Click record button
- Simple but works
- Saves to Videos/Captures folder

### Option 4: ShareX (Advanced)
- Download: https://getsharex.com/
- Free and feature-rich
- Good for screen recording

---

## Upload Instructions

### YouTube (Recommended)
1. Go to youtube.com
2. Click "Create" → "Upload video"
3. Select your video file
4. **Set visibility to "Unlisted"** (not public, not private)
5. Add title: "AutoJudge - Programming Problem Difficulty Prediction"
6. Copy the link and add to README.md

### Google Drive
1. Upload video to Google Drive
2. Right-click → "Get link"
3. **Set to "Anyone with the link can view"**
4. Copy link and add to README.md

### Loom (Easiest)
1. Record directly in Loom
2. It automatically gives you a shareable link
3. Copy and add to README.md

---

## Post-Recording Checklist

- [ ] Video is 2-3 minutes long
- [ ] All 3 test predictions are clearly visible
- [ ] Audio is clear
- [ ] Uploaded to YouTube/Drive/Loom
- [ ] Link copied
- [ ] Link added to README.md in the "Demo Video" section
- [ ] Link tested (open in incognito to verify it works)

---

## Quick Timeline Reference

```
0:00 ├─ Introduction & Problem Statement
0:30 ├─ Dataset & Model Approach
1:10 ├─ Web UI Demo
     │  ├─ Easy Problem (1:10-1:30)
     │  ├─ Medium Problem (1:30-1:55)
     │  └─ Hard Problem (1:55-2:20)
2:20 └─ Conclusion & Thank You
2:45    (End)
```

---

## Example Final Structure

1. **Intro** → "Hi, I'm Deepak, this is AutoJudge..."
2. **Show Data** → Open problems.csv, explain features
3. **Explain Models** → Random Forest, 95% accuracy
4. **Demo Time** → Open browser, test 3 problems
5. **Wrap Up** → "Thank you, check GitHub"

---

## 🎥 YOU'RE READY!

Just follow this script, speak naturally, and you'll have a great demo video!

**Estimated Time to Record:** 15-30 minutes (including practice)

Good luck! 🚀
