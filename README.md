# DECISION-TREE-Practical-with-my-students-today
This experiment is to build a Decision Tree model to determine using data if the weather is suitable to play tennis

# Decision Tree Experiment - Tennis Prediction

This project demonstrates the creation and visualization of a Decision Tree classifier using the `tennis.txt` dataset. The dataset contains 14 samples with weather-related features and a label indicating whether it's suitable for playing tennis.

## Overview

The goal of this experiment is to train a Decision Tree model to predict the "Play Tennis" outcome based on various weather conditions. The process involves data preprocessing (vectorization of categorical features) and then training and visualizing the decision tree.

## Dataset

The `tennis.txt` dataset is used in this experiment. It is expected to be a tab-separated file with no header, where the last column represents the target variable (suitable for tennis or not) and the preceding columns are weather-related features.

## Steps

The project follows these steps:

1.  **Import Dependencies**: Essential libraries like `pandas` for data manipulation, `numpy` for numerical operations, `sklearn.tree` for the Decision Tree classifier, and `pydotplus` for visualizing the tree are imported.

2.  **Define the function for generating a decision tree (`createTree`)**:
    * This function takes `trainingData` as input.
    * It separates the feature matrix (`data`) from the labels (`labels`).
    * A `DecisionTreeClassifier` is initialized with the `criterion` set to "entropy".
    * The model is trained using the `fit` method with `data` and `labels`.
    * The trained decision tree is returned.

3.  **Define the function for saving the generated tree diagram (`showtree2pdf`)**:
    * This function takes the `trainedTree` and a `filename` as input.
    * It exports the tree into Graphviz format using `tree.export_graphviz`.
    * `pydotplus.graph_from_dot_data` is used to create a graph object.
    * The tree diagram is saved as a PDF file with the specified `filename` (e.g., "tennis.pdf") on the local machine.

4.  **Define the function for generating vectorized data (`data2vectoc`)**:
    * This function converts categorical information in the dataset into numerical (vectorized) information.
    * It iterates through each feature column (excluding the last column which is the label).
    * `pd.Categorical(list).codes` is used to obtain a sequence number list corresponding to the original categorical data.
    * The modified DataFrame with numerical features is returned.

5.  **Invoke the function for prediction**:
    * The `tennis.txt` training data is read into a pandas DataFrame.
    * The `data2vectoc` function is called to vectorize the training data.
    * A decision tree is created using `createTree` with the vectorized data.
    * Finally, `showtree2pdf` is called to plot and save the decision tree as "tennis.pdf".

## How to Run

1.  Ensure you have the `tennis.txt` file in the same directory as your Jupyter Notebook.
2.  Make sure you have all the necessary dependencies installed (`pandas`, `numpy`, `scikit-learn`, `pydotplus`, and Graphviz).
3.  Open the Jupyter Notebook (`Decision Tree Practical Experiment for my students today 06 06 2025.ipynb`).
4.  Run all the cells sequentially. This will generate a PDF file named `tennis.pdf` containing the decision tree visualization.

## Dependencies

* `pandas`
* `numpy`
* `scikit-learn`
* `pydotplus`
* Graphviz (must be installed separately on your system for `pydotplus` to generate PDF/images)
