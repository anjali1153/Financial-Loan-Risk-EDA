# Financial-Loan-Risk-EDA
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Bank Loan Data — EDA (README)</title>
  <style>
    :root{--bg:#0f1724;--card:#0b1220;--muted:#9aa4b2;--accent:#3b82f6}
    body{font-family:Inter, ui-sans-serif, system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial; background:linear-gradient(180deg,#071028 0%, #071827 60%); color:#e6eef6; margin:0; padding:32px}
    .container{max-width:1000px;margin:0 auto}
    header{display:flex;align-items:center;gap:16px}
    header h1{margin:0;font-size:1.6rem}
    header p{margin:0;color:var(--muted)}
    nav{margin:18px 0}
    nav a{color:var(--accent);text-decoration:none;margin-right:12px}
    .card{background:rgba(255,255,255,0.03);border-radius:12px;padding:18px;margin-bottom:16px;box-shadow:0 6px 18px rgba(2,6,23,0.6)}
    pre{background:#020617;padding:12px;border-radius:8px;overflow:auto;color:#d6e6ff}
    code{font-family:ui-monospace, SFMono-Regular, Menlo, Monaco, "Roboto Mono", "Courier New", monospace}
    table{width:100%;border-collapse:collapse;margin-top:12px}
    th,td{padding:8px;border-bottom:1px solid rgba(255,255,255,0.04);text-align:left}
    th{color:#cfe3ff}
    .muted{color:var(--muted)}
    .sample-table{margin-top:16px}
    .grid{display:grid;grid-template-columns:1fr 1fr;gap:12px}
    @media (max-width:760px){.grid{grid-template-columns:1fr}}
    .btn{display:inline-block;padding:8px 12px;background:var(--accent);color:white;border-radius:8px;text-decoration:none}
    footer{margin-top:24px;color:var(--muted);font-size:0.9rem}
  </style>
</head>
<body>
  <div class="container">
    <header>
      <div>
        <h1>Bank Loan Data — Exploratory Data Analysis (EDA)</h1>
        <p class="muted">Single-file HTML README containing project overview, how-to, code snippets and supporting files.</p>
      </div>
    </header>

    <nav class="card">
      <strong>Table of contents:</strong>
      <div style="margin-top:8px">
        <a href="#overview">Project overview</a>
        <a href="#files">Files</a>
        <a href="#run">How to run</a>
        <a href="#notebook">Notebook structure</a>
        <a href="#key">Key analyses</a>
        <a href="#deps">Dependencies</a>
        <a href="#dict">Data dictionary</a>
        <a href="#snippet">HTML preview</a>
        <a href="#recommend">Recommendations</a>
        <a href="#contribute">Contributing & License</a>
        <a href="#author">Author</a>
      </div>
    </nav>

    <section id="overview" class="card">
      <h2>Project overview</h2>
      <p>This repository contains an exploratory data analysis (EDA) for a bank loan dataset. The objective is to inspect data quality, perform cleaning and feature engineering, visualize distributions and relationships, and present findings useful for predictive modelling (loan approval / default).</p>
      <ul class="muted">
        <li>Audience: data analysts, students, ML engineers</li>
        <li>Primary artefact: <code>Bank_loan_data_EDA.ipynb</code> (Jupyter Notebook)</li>
      </ul>
    </section>

    <section id="files" class="card">
      <h2>Files in this repo</h2>
      <ul>
        <li><code>Bank_loan_data_EDA.ipynb</code> — main notebook with step-by-step EDA and plots</li>
        <li><code>data/</code> — place dataset CSV files here (e.g. <code>loan_data.csv</code>)</li>
        <li><code>requirements.txt</code> — Python dependencies (example below)</li>
        <li><code>CONTRIBUTING.md</code> (optional) — how others can contribute</li>
        <li><code>LICENSE</code> — license for this project</li>
      </ul>
    </section>

    <section id="run" class="card">
      <h2>How to run</h2>
      <ol>
        <li>Clone the repo and change directory:
          <pre><code>git clone &lt;your-repo-url&gt;
cd &lt;repo-folder&gt;</code></pre>
        </li>
        <li>Create and activate virtual environment, then install requirements:
          <pre><code>python -m venv venv
# macOS / Linux
source venv/bin/activate
# Windows PowerShell
venv\Scripts\activate
pip install -r requirements.txt</code></pre>
        </li>
        <li>Open the notebook:
          <pre><code>jupyter notebook Bank_loan_data_EDA.ipynb
# or
jupyter lab</code></pre>
        </li>
        <li>If the dataset is missing, place it in <code>data/</code> or update the notebook cell that reads the CSV.</li>
      </ol>
    </section>

    <section id="notebook" class="card">
      <h2>Notebook structure & steps performed</h2>
      <p>The notebook follows a reproducible EDA workflow:</p>
      <ol>
        <li><strong>Load libraries & dataset</strong> — pandas, numpy, matplotlib, seaborn, sklearn (optional).</li>
        <li><strong>Initial inspection</strong> — <code>df.head()</code>, <code>df.info()</code>, <code>df.describe()</code>.</li>
        <li><strong>Missing value analysis</strong> — detect and plan imputation.</li>
        <li><strong>Data cleaning</strong> — trimming whitespace, fixing data types, encoding categorical columns.</li>
        <li><strong>Feature engineering</strong> — e.g., <code>TotalIncome</code>, <code>EMI_ratio</code>, <code>Income_per_family_member</code>.</li>
        <li><strong>Univariate & bivariate analysis</strong> — histograms, boxplots, barplots, correlation heatmap.</li>
        <li><strong>Summary of findings</strong> — key takeaways and suggested next steps for modelling.</li>
      </ol>
    </section>

    <section id="key" class="card">
      <h2>Key analyses & visualizations</h2>
      <ul>
        <li>Distribution plots for <code>ApplicantIncome</code>, <code>CoapplicantIncome</code>, <code>LoanAmount</code> — check skew and log-transform needs.</li>
        <li>Approval rate bar charts grouped by <code>Gender</code>, <code>Married</code>, <code>Education</code>, <code>Self_Employed</code>, <code>Property_Area</code>.</li>
        <li>Correlation heatmap to inspect relationships between numeric features.</li>
        <li>Missing-value heatmap to quickly visualize gaps.</li>
      </ul>
    </section>

    <section id="deps" class="card">
      <h2>Dependencies (example)</h2>
      <p>Add the following to <code>requirements.txt</code> or install manually:</p>
      <pre><code>pandas
numpy
matplotlib
seaborn
scikit-learn
jupyter
openpyxl</code></pre>
      <p class="muted">Tip: you can pin versions once you stabilise the notebook (e.g., <code>pandas==2.2.2</code>).</p>
    </section>

    <section id="dict" class="card">
      <h2>Data dictionary (example)</h2>
      <p>Update these entries to match your dataset's exact column names.</p>
      <table>
        <thead>
          <tr><th>Column</th><th>Description</th></tr>
        </thead>
        <tbody>
          <tr><td><code>Loan_ID</code></td><td>Unique Loan identifier</td></tr>
          <tr><td><code>Gender</code></td><td>Male / Female</td></tr>
          <tr><td><code>Married</code></td><td>Yes / No</td></tr>
          <tr><td><code>Dependents</code></td><td>0, 1, 2, 3+</td></tr>
          <tr><td><code>Education</code></td><td>Graduate / Not Graduate</td></tr>
          <tr><td><code>Self_Employed</code></td><td>Yes / No</td></tr>
          <tr><td><code>ApplicantIncome</code></td><td>Applicant monthly income</td></tr>
          <tr><td><code>CoapplicantIncome</code></td><td>Coapplicant monthly income</td></tr>
          <tr><td><code>LoanAmount</code></td><td>Loan amount (in thousands)</td></tr>
          <tr><td><code>Loan_Amount_Term</code></td><td>Term (months)</td></tr>
          <tr><td><code>Credit_History</code></td><td>1.0 = meets criteria, 0.0 = otherwise</td></tr>
          <tr><td><code>Property_Area</code></td><td>Urban / Semiurban / Rural</td></tr>
          <tr><td><code>Loan_Status</code></td><td>Y = Approved, N = Not approved</td></tr>
        </tbody>
      </table>
    </section>

    <section id="snippet" class="card">
      <h2>HTML preview — sample table</h2>
      <p>Use this snippet to preview a small dataset sample in a browser. Copy the block below into a file named <code>preview.html</code> and open it.</p>
      <pre><code>&lt;!doctype html&gt;
&lt;html lang="en"&gt;
  &lt;head&gt;
    &lt;meta charset="utf-8" /&gt;
    &lt;meta name="viewport" content="width=device-width, initial-scale=1" /&gt;
    &lt;title&gt;Loan Data Preview&lt;/title&gt;
    &lt;style&gt;table{border-collapse:collapse;width:100%}th,td{border:1px solid #ddd;padding:8px;text-align:left}th{background:#f4f4f4}&lt;/style&gt;
  &lt;/head&gt;
  &lt;body&gt;
    &lt;h2&gt;Loan Data — Sample&lt;/h2&gt;
    &lt;table&gt;
      &lt;thead&gt;&lt;tr&gt;&lt;th&gt;Loan_ID&lt;/th&gt;&lt;th&gt;Gender&lt;/th&gt;&lt;th&gt;Married&lt;/th&gt;&lt;th&gt;ApplicantIncome&lt;/th&gt;&lt;th&gt;LoanAmount&lt;/th&gt;&lt;th&gt;Loan_Status&lt;/th&gt;&lt;/tr&gt;&lt;/thead&gt;
      &lt;tbody&gt;
        &lt;tr&gt;&lt;td&gt;LP001002&lt;/td&gt;&lt;td&gt;Male&lt;/td&gt;&lt;td&gt;No&lt;/td&gt;&lt;td&gt;5849&lt;/td&gt;&lt;td&gt;128&lt;/td&gt;&lt;td&gt;Y&lt;/td&gt;&lt;/tr&gt;
        &lt;tr&gt;&lt;td&gt;LP001003&lt;/td&gt;&lt;td&gt;Male&lt;/td&gt;&lt;td&gt;Yes&lt;/td&gt;&lt;td&gt;4583&lt;/td&gt;&lt;td&gt;128&lt;/td&gt;&lt;td&gt;N&lt;/td&gt;&lt;/tr&gt;
      &lt;/tbody&gt;
    &lt;/table&gt;
  &lt;/body&gt;
&lt;/html&gt;</code></pre>
    </section>

    <section id="recommend" class="card">
      <h2>Recommendations & next steps</h2>
      <ol>
        <li>Train tree-based models (RandomForest, XGBoost) on the cleaned dataset and inspect feature importances.</li>
        <li>Use SHAP or LIME for model explainability to understand per-instance predictions.</li>
        <li>Try target encoding for categorical variables with many categories and model-based imputation for missing data.</li>
        <li>Use stratified k‑fold cross-validation for imbalanced targets.</li>
        <li>Wrap preprocessing and model into a single <code>sklearn.pipeline</code> and save with <code>joblib</code>.</li>
      </ol>
    </section>

    <section id="contribute" class="card">
      <h2>Contributing & License</h2>
      <div class="grid">
        <div>
          <h3>CONTRIBUTING.md (suggested)</h3>
          <pre><code># Contributing

Thanks for your interest in contributing! Please:
1. Fork the repo
2. Create a feature branch: git checkout -b feature/your-feature
3. Commit changes with descriptive messages
4. Open a pull request explaining your changes

If adding code, include tests and documentation updates.</code></pre>
        </div>
        <div>
          <h3>LICENSE (suggested)</h3>
          <pre><code>MIT License

Copyright (c) &lt;year&gt; &lt;author&gt;

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction...</code></pre>
        </div>
      </div>
    </section>

    <section id="extras" class="card">
      <h2>Quick helper files — copy/paste</h2>
      <div class="grid">
        <div>
          <h3>requirements.txt</h3>
          <pre><code>pandas
numpy
matplotlib
seaborn
scikit-learn
jupyter
openpyxl</code></pre>
        </div>
        <div>
          <h3>Sample .gitignore</h3>
          <pre><code>venv/
__pycache__/
.ipynb_checkpoints/
*.pyc
.env
.DS_Store</code></pre>
        </div>
      </div>
    </section>

    <section id="author" class="card">
      <h2>Author / Contact</h2>
      <p><strong>Prepared by:</strong> Anjali Wable</p>
      <p><strong>Email:</strong> wableab1153@gmail.com</p>
      <p><strong>GitHub:</strong> <span class="muted">https://github.com/anjali1153/Financial_Loan_Risk_EDA</span></p>
    </section>

    <footer>
      <p class="muted">If you'd like, I can embed the actual sample rows from your notebook, produce a downloadable requirements.txt, or convert this into a GitHub-friendly README.md instead. Tell me which one you prefer.</p>
    </footer>
  </div>
</body>
</html>
