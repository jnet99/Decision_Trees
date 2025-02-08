# Decision_Trees
**Objective:**
Implement a Python function, decision_tree, to train and evaluate decision trees and random forests for classification tasks. The function learns from training data and classifies test data based on configurable hyperparameters.

## Repository Structure
- `data/`: Contains datasets (e.g., `pendigits_training.txt`).
- `outputs/`: Contains test results for different configurations.
- `gifs/`: Contains visualizations of tree structures or classification results.

**1. Code Structure**
**decision_tree_main.py:**  
  - Sets the dataset directory, dataset name, and hyperparameters (option, pruning_thr).
  - Calls the decision_tree function with the specified inputs.

**decision_tree.py:**  
  - **Data Loading:** Reads training and test data from UCI-format files.  
  - **Tree/Forest Construction:**  
    - **Optimized Tree:** Chooses the optimal feature and threshold at each node to maximize information gain.  
    - **Randomized Tree:** Randomly selects features at each node, optimizing thresholds for information gain.  
    - **Random Forest:** Builds multiple randomized trees and aggregates their predictions.  
  - **Pruning:** Stops splitting nodes if the number of samples is below the `pruning_thr`.  
  - **Classification:**  
    - Predicts classes for test data using the trained tree or forest.  
    - Handles ties in predictions and computes accuracy for each test object.  
  - **Output:**  
    - Prints the tree structure in breadth-first order during training.  
    - Prints object ID, predicted class, true class, and accuracy for each test example.  
    - Computes and prints the overall classification accuracy.  

**Key Features**
1. Supports both single decision trees and random forests.
   
2. Configurable hyperparameters:
  - option: "optimized" for a single optimized tree, or an integer for a random forest           with that many trees.
  - pruning_thr: Controls early stopping during tree construction.
     Uses information gain to select features and thresholds.
     Handles multi-class classification tasks.

**Testing and Results**
  Tested on the pendigits dataset with the following configurations:
  1. Optimized Tree:
     -  Output: Tree structure and classification accuracy (e.g., 83.82%).

  2. Single Randomized Tree:
     -  Output: Tree structure and classification accuracy (e.g., 67.90%–77.53%).

  3. Random Forest (3 Trees):
     -  Output: Forest structure and classification accuracy (e.g., 80.47%–86.99%).

  3. Random Forest (15 Trees):
     -  Output: Forest structure and classification accuracy (e.g., 87.31%–89.94%).
My results were consistent with expected performance ranges.

**Example Output**  
- **Training Output (tree structure):**  
  ```plaintext
  tree= 1, node=  1, feature= 1, thr=  0.50, gain=0.123456  
  tree= 1, node=  2, feature=-1, thr= -1.00, gain=0.000000  
  ...  
- **Test Output (classification results):**
  ```plaintext
  ID=    1, predicted=  2, true=  2, accuracy=1.00
  ID=    2, predicted=  4, true=  4, accuracy=1.00
  ...
  Overall accuracy: 0.8382"


    
![decision_tree_1_50](https://github.com/user-attachments/assets/74b3fa96-5fbf-4861-9428-93cd2d82d2fa)



