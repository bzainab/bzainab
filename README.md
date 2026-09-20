# Hi, I'm Zainab Baig

Computer science graduate working across machine learning, backend development, and systems programming. I like problems where correctness actually matters — clinical risk modelling, concurrency, and data structures — and I care about building things end to end rather than stopping at a notebook.

## Featured Projects

### [Cardiovascular Risk Prediction](https://github.com/bzainab/cardiovascular-risk-prediction)
An end-to-end machine learning system predicting 10-year coronary heart disease risk from the Framingham Heart Study dataset.

Built the full pipeline: preprocessing, training, evaluation, and a Streamlit app for interactive inference. Compared Logistic Regression, Random Forest, Gradient Boosting, XGBoost, SVM, an ANN, and a clinically informed stacking ensemble — scored with ROC-AUC, precision, recall, F1, calibration curves, bootstrap confidence intervals, and pairwise statistical tests, plus SMOTE experiments for class imbalance.

Best ROC-AUC was 0.6975 (Logistic Regression). I report that honestly rather than tuning for a headline number — modest discrimination is the realistic result on this dataset, and overstating it would be the wrong call for anything health-related.

`Python` `scikit-learn` `XGBoost` `pandas` `imbalanced-learn` `Streamlit`

### [Parallel Matrix Operations](https://github.com/bzainab/parallel-matrix-operations)
A multithreaded C++ matrix-processing engine built on a custom worker pool.

Threads are created once and reused, work is split into row bands so each worker owns a disjoint output region, and condition variables act as a completion barrier between pipeline stages. Tuned for memory behaviour too: flat row-major storage for cache locality, a fused transpose/zone-sum pass, and `i-k-j` loop ordering for multiplication. Benchmarked over repeated runs with a verification harness checking output against known-good matrices.

`C++` `std::thread` `mutexes` `condition variables` `thread pools` `CMake`

### [C# Algorithms and Data Structures](https://github.com/bzainab/csharp-algorithms-data-structures)
Core data structures and algorithms implemented from scratch, with no external dependencies.

A three-layer tree hierarchy — binary tree, BST, then a self-balancing AVL tree handling all four rotation cases — over a generic `IComparable` constraint. A fixed-capacity circular queue with wrapping head/tail indices. A greedy knapsack solver selecting by value-to-weight ratio. And a weighted graph supporting BFS, DFS, and a least-risk `SafestRoute` traversal that expands the lowest-weight edge available via a priority queue.

`C#` `.NET Framework` `WinForms`

## Tech

**Languages** — Python, C#, C++, JavaScript, SQL
**ML & Data** — scikit-learn, XGBoost, pandas, NumPy, imbalanced-learn, matplotlib, seaborn
**Tools** — Streamlit, Git, Visual Studio, CMake, Jupyter

## Get in touch

- Email: zainabyasin286@gmail.com
