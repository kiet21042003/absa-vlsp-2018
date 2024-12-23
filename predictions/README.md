This is the folder for the experiment results.

## **Folder Structure**

The folder is organized as follows:

```
predictions/
│
├── SAEvaluate.java               # The Java evaluator for running evaluations
│
├── Method1/                      # Folder for predictions of Method1
│   ├── hotel/                    # Subfolder for hotel predictions
│   │   ├── predictions.txt       # Predicted labels for hotel
│   │   ├── labels.txt            # True labels for hotel
│   │   └── results.txt           # Evaluation results (generated automatically)
│   ├── Restaurant/
│   │   ├── predictions.txt
│   │   ├── labels.txt
│   │   └── results.txt
│
├── Method2/                      # Folder for predictions of Method2
│   ├── hotel/
│   │   ├── predictions.txt
│   │   ├── labels.txt
│   │   └── results.txt
│   └── ...
│
└── ...
```

### **File Descriptions**
- **`predictions.txt`**: The predicted labels generated by your method.
- **`labels.txt`**: The ground truth labels for the dataset.
- **`results.txt`**: The evaluation output, generated automatically by the script.

---

## **How to Add Predictions for Your Method**

1. Create a folder under `predictions/` with the name of your method. For example:
   ```
   predictions/MyNewMethod/
   ```

2. Inside your method's folder, create a subfolder for each dataset you evaluate, such as:
   ```
   predictions/MyNewMethod/hotel/
   ```

3. Add the following files to each dataset's folder:
   - **`predictions.txt`**: Your method's predicted labels for the dataset.
   - **`labels.txt`**: The true labels for the dataset. It should be the same for all methods.

---

## **Running the Evaluation**

1. **Ensure you have Java installed** on your machine.
   - You can check by running: `java -version`.
   - If Java is not installed, [download and install Java](https://www.oracle.com/java/technologies/javase-downloads.html).

2. Navigate to the `predictions` folder in your terminal:
   ```
   cd path/to/predictions
   ```

3. Run the evaluation script:
   ```
   bash evaluate.sh
   ```

### **Script Details**
- The script automatically detects subfolders containing `predictions.txt` and `labels.txt` files.
- For each valid folder, it evaluates the predictions using `SAEvaluate.java` and saves the results in a `results.txt` file within the same folder.

---

## **Example**

If you add predictions for **`MyNewMethod`** on **`hotel`**:

1. Create the folder structure:
   ```
   predictions/MyNewMethod/hotel/
   ```
2. Add the files:
   ```
   predictions.txt  # Your method's predictions
   labels.txt       # Ground truth labels
   ```
3. Run the evaluation script:
   ```
   bash evaluate.sh
   ```
4. The results will be saved to:
   ```
   predictions/MyNewMethod/hotel/results.txt
   ```