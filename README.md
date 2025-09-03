## 📝 Description

This project implements a lightweight, rule-based computer vision system to detect and classify defects in biscuit-shaped objects using only classical image processing techniques — no machine learning or deep learning was used. The method is designed for use under fixed lighting conditions, ensuring consistent thresholding and morphology-based analysis.

Three main types of defects are detected:

🟢 Intact Biscuits: Full circles with no internal cracks

🔴 Cracked Biscuits: Full circles containing internal contour breaks

🟡 Partial Biscuits: Incomplete or undersized circular shapes

⚫ Burned Biscuits: Over-darkened biscuits identified through intensity-based filtering

A combination of morphological operations and contour analysis is used to isolate and classify these defects. The method is fast, interpretable, and suited for low-resource or real-time applications.

<img width="559" height="812" alt="output" src="https://github.com/user-attachments/assets/25b22e51-62d3-4756-9ca2-6a7a931f81a3" />


## 🧠 Key Techniques

Piecewise Intensity Thresholding
Instead of a single global threshold, multiple intensity ranges were used to better segment biscuit regions under variable lighting. A secondary threshold was applied to exclude dark (burned) regions.

Burn Detection via XOR
Burned biscuits were identified by performing an XOR between:

A piecewise mask of all biscuits

A mask of only non-burned (lighter) regions
This isolates over-darkened (burned) biscuits effectively.

Crack Detection
Full circles are evaluated for cracks by analyzing internal contours on inverted masks. If the internal contour area exceeds a threshold, the biscuit is marked as cracked.

Partial Detection
Based on circularity and radius checks. Biscuits that are too small or deviate significantly from a circular shape are labeled partial.

## 🛠 Technologies Used

- Python
- OpenCV
- NumPy
- Matplotlib (for visualization)

## ⏱️ Time Constraint

⚠️ Note: This was an in-class machine vision task completed in under 2.5 hours.
The focus was on demonstrating robust problem-solving using only morphological and rule-based methods, with no learning-based models.
