# **Assignment C: Random Forest Algorithms**



1. ### **What is a "Random Forest Algorithm"?**



Random Forest is a powerful machine learning algorithm that builds multiple decision trees and combines their outputs to improve accuracy and reduce overfitting. It’s widely used for both classification and regression tasks because of its robustness and ability to handle large datasets with many features. Random Forest reduces overfitting by averaging the predictions of multiple diverse trees, which allows their individual errors and noise to cancel each other out.



### **2. What are Ensemble Methods?**



Ensemble methods aggregate predictions from several models to reduce errors and improve robustness. We combine ***many*** **weak learning models** into ***one*** **strong learning model**. It is mainly used in classification, regression, anomaly detection, and even ranking tasks.



### **3. What is Bagging?**



* **Bagging** stands for **Bootstrap Aggregating.**
* It’s an **ensemble method** where multiple models (usually decision trees) are trained in parallel on different random samples of the dataset.
* The final prediction is made by **combining their outputs** (majority vote for classification, average for regression).



### **4. How does Bagging work?**



1. **Bootstrap Sampling**



* From the original dataset of size 𝑛,  we randomly draw 𝑛 samples **with replacement.**
* This means some data points may appear multiple times in one sample, while others may be left out.
* Each model gets a slightly different dataset to train on.



2\. **Train Multiple Models**



* Each model (e.g., a decision tree) is trained on its own bootstrap sample.
* Because the samples differ, the models learn slightly different patterns.



3\. **Aggregate Predictions**



* **For classification:** each model votes, and the majority class is chosen.
* **For regression:** predictions are averaged across models.



### **5. How is Random Forest different from a Single decision tree?**



A single decision tree is like **one person making a decision based on a list of criteria**, whereas a Random Forest is like **a large committee of those people voting to reach a more stable and accurate consensus**.



### **6. What is Feature Randomness? Why use it?**



In a standard **Decision Tree**, the algorithm looks at **every available feature** (column) and picks the absolute best one to split the data.



**Feature randomness** changes this by forcing each node in a tree to pick the best split from only **a randomly selected subset of features.**



**Why do this?**



1. **Prevents "Dominant" Features:** If you have one very strong predictor (e.g., "Income" in a credit score model), every single tree in a normal forest would start with that feature. This makes all the trees look alike.
2. **Encourages Diversity:** By hiding some features, you force different trees to find patterns in "weaker" or secondary variables.
3. **The "Wisdom of the Crowd":** When you combine these diverse trees, the final result is less biased and more robust because the trees have learned the data from many different "angles" rather than all following the same path.



### **7. What is Majority voting for classification?**



**Majority Voting (Classification):** Each tree predicts a category (like "Spam" or "Not Spam"), and the forest selects the category that received the most "votes" across all trees.



### **8. What is Averaging for Regression?**



**Averaging (Regression):** Each tree predicts a specific numerical value (like a house price), and the forest calculates the mathematical mean of all those individual predictions to give a single final number.



### **9. What are the key hyperparameters?**



**Hyperparameters control the size, complexity, and diversity of the forest. Here is what they do:**



* `n\_estimators`: The number of trees in the forest. Generally, more trees increase accuracy and make the model more stable, but after a certain point, you get diminishing returns and the model just becomes slower to train.
* `max\_depth`: The maximum height of each tree. It limits how many "splits" a tree can make. Keeping this low prevents trees from becoming too complex and overfitting, while setting it too high allows trees to capture finer details (but increases the risk of memorizing noise).
* `max\_features`: The size of the random subset of features considered at each split. This is the "feature randomness" as shown above. it determines how many columns a tree is allowed to look at when deciding how to split the data, ensuring the trees in the forest stay diverse.



### **10. What is "Feature Importance" in a Random Forest? How does it help explain which inputs matter?**



Feature Importance measures how much each input variable contributes to the forest's accuracy by calculating how effectively it reduces uncertainty or impurity across all individual trees.



|**Feature**|**Single Decision Tree**|**Random Forest**|
|-|-|-|
|**Stability**|Low (small data changes change the tree)|High (stable against data variations)|
|**Performance**|Good for simple tasks|Superior for complex tasks|
|**Ease of Use**|High (easy to explain to stakeholders)|Low (requires more tuning and power)|





