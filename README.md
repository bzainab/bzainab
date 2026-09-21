# Hi, I'm Zainab Baig

Computer science graduate working across machine learning, backend development, and systems programming. I like problems where correctness actually matters — clinical risk modelling, concurrency, and data structures — and I care about building things end to end rather than stopping at a notebook.

## Featured Projects

### [Public Spend Audit](https://github.com/bzainab/public-spend-audit)
Forensic analytics over UK public sector spending data — 23,707 payments worth £7.13bn, reduced to a ranked shortlist of 44 suppliers.

Pulls spend-over-£25,000 transparency releases from the data.gov.uk API and reconciles inconsistent publisher schemas into one ledger, handling the things that actually break ingestion: accounting-bracket negatives, European decimal separators, files labelled CSV that are really XLSX. Then runs the standard forensic tests — Benford conformity, duplicate payment detection, threshold proximity, supplier concentration — and scores supplier risk two ways: a transparent weighted sum that names the reason for every selection, plus an Isolation Forest as an unsupervised cross-check.

The part I'd point at: this population is censored at £25,000, so first-digit Benford is invalid by construction. The pipeline detects that and marks the result unreliable rather than reporting a false finding.

`Python` `pandas` `scikit-learn` `Altair` `Streamlit` `pytest`

### [Threat Intelligence Toolkit](https://github.com/bzainab/threat-intel-toolkit)
Turns unstructured threat reporting into a structured intelligence product, running against live MITRE ATT&CK and CISA KEV data.

Extracts indicators from prose — handling the defanged notation published reporting uses (`hxxps://evil[.]com`), and suppressing the false positives that dominate naive extraction: version strings that parse as IP addresses, filenames that parse as domains. Maps the report narrative onto ATT&CK techniques, compares observed tradecraft against documented actor profiles, and cross-references referenced CVEs against CISA's Known Exploited Vulnerabilities catalogue to surface what is ransomware-linked and overdue.

The part I'd point at: ranking actors by TTP overlap is biased toward whoever is best documented. The sample demonstrates it — APT18 tops the Jaccard ranking on 7 matched techniques purely because it has 11 documented in total, while BlackByte explains 15 of 17. The report leads with coverage of what was observed, not the similarity score.

No third-party runtime dependencies — standard library only, because for a tool ingesting hostile input every dependency is supply-chain surface.

`Python` `MITRE ATT&CK` `STIX` `threat intelligence` `pytest`

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
**ML & Data** — scikit-learn, XGBoost, pandas, NumPy, imbalanced-learn, Altair, matplotlib
**Security** — MITRE ATT&CK, STIX, threat intelligence, OSINT, IOC analysis
**Tools** — Streamlit, Git, pytest, Visual Studio, CMake, Jupyter

## Get in touch

- Email: zainabyasin286@gmail.com
