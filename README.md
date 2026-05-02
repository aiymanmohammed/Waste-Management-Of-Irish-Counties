<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>IS6061 Group 24 README</title>
  <link href="https://fonts.googleapis.com/css2?family=IBM+Plex+Mono:wght@400;600&family=IBM+Plex+Sans:wght@400;500;600&display=swap" rel="stylesheet" />
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    :root {
      --bg: #0d1117;
      --surface: #161b22;
      --border: #30363d;
      --text: #e6edf3;
      --muted: #8b949e;
      --accent: #4493f8;
      --tag-bg: #1f2d3d;
      --tag-text: #79c0ff;
    }

    body {
      background: var(--bg);
      color: var(--text);
      font-family: 'IBM Plex Sans', sans-serif;
      font-size: 15px;
      line-height: 1.7;
      padding: 48px 24px;
    }

    .container {
      max-width: 760px;
      margin: 0 auto;
    }

    .repo-label {
      font-family: 'IBM Plex Mono', monospace;
      font-size: 12px;
      color: var(--muted);
      letter-spacing: 0.08em;
      text-transform: uppercase;
      margin-bottom: 10px;
    }

    h1 {
      font-size: 26px;
      font-weight: 600;
      color: var(--text);
      margin-bottom: 10px;
      line-height: 1.3;
    }

    .subtitle {
      color: var(--muted);
      font-size: 14px;
      margin-bottom: 36px;
    }

    hr {
      border: none;
      border-top: 1px solid var(--border);
      margin: 32px 0;
    }

    h2 {
      font-size: 13px;
      font-weight: 600;
      text-transform: uppercase;
      letter-spacing: 0.1em;
      color: var(--muted);
      margin-bottom: 14px;
    }

    p {
      color: var(--text);
      margin-bottom: 12px;
    }

    .section {
      margin-bottom: 32px;
    }

    .authors-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
      gap: 10px;
    }

    .author-card {
      background: var(--surface);
      border: 1px solid var(--border);
      border-radius: 6px;
      padding: 12px 16px;
    }

    .author-name {
      font-weight: 600;
      font-size: 14px;
      color: var(--text);
    }

    .author-id {
      font-family: 'IBM Plex Mono', monospace;
      font-size: 12px;
      color: var(--muted);
      margin-top: 2px;
    }

    .tags {
      display: flex;
      flex-wrap: wrap;
      gap: 8px;
    }

    .tag {
      background: var(--tag-bg);
      color: var(--tag-text);
      font-family: 'IBM Plex Mono', monospace;
      font-size: 12px;
      padding: 4px 10px;
      border-radius: 4px;
      border: 1px solid #2d5a8a;
    }

    .notebook-table {
      width: 100%;
      border-collapse: collapse;
      font-size: 14px;
    }

    .notebook-table th {
      text-align: left;
      padding: 8px 12px;
      font-weight: 600;
      font-size: 12px;
      text-transform: uppercase;
      letter-spacing: 0.07em;
      color: var(--muted);
      border-bottom: 1px solid var(--border);
    }

    .notebook-table td {
      padding: 10px 12px;
      border-bottom: 1px solid var(--border);
      vertical-align: top;
    }

    .notebook-table tr:last-child td {
      border-bottom: none;
    }

    .step-num {
      font-family: 'IBM Plex Mono', monospace;
      font-size: 12px;
      color: var(--accent);
      white-space: nowrap;
    }

    .data-row {
      display: flex;
      gap: 12px;
      margin-bottom: 10px;
    }

    .data-card {
      flex: 1;
      background: var(--surface);
      border: 1px solid var(--border);
      border-radius: 6px;
      padding: 14px 16px;
    }

    .data-card .label {
      font-size: 12px;
      color: var(--muted);
      margin-bottom: 4px;
      font-weight: 600;
      text-transform: uppercase;
      letter-spacing: 0.07em;
    }

    .data-card .value {
      font-family: 'IBM Plex Mono', monospace;
      font-size: 13px;
      color: var(--accent);
    }

    .data-card .desc {
      font-size: 13px;
      color: var(--muted);
      margin-top: 4px;
    }
  </style>
</head>
<body>
  <div class="container">

    <div class="repo-label">IS6061 / Group 24</div>
    <h1>Irish Waste Management Analysis</h1>
    <p class="subtitle">Exploratory analysis of quarterly waste generation and treatment across Irish counties</p>

    <hr />

    <div class="section">
      <h2>Overview</h2>
      <p>
        This project analyses quarterly waste generation and treatment data across 26 Irish counties.
        The goal was to identify patterns in waste volumes, treatment methods, and treatment costs
        across different waste types and regions, using structured data analysis and exploratory visualisation.
      </p>
    </div>

    <hr />

    <div class="section">
      <h2>Data Sources</h2>
      <div class="data-row">
        <div class="data-card">
          <div class="label">Waste Generation</div>
          <div class="value">19,656 records</div>
          <div class="desc">Quarter, County, Waste Type, Waste Category, Amount (tonnes)</div>
        </div>
        <div class="data-card">
          <div class="label">Waste Treatment</div>
          <div class="value">45,864 records</div>
          <div class="desc">Quarter, County, Waste Type, Treatment Method, Amount (tonnes), Price (per tonne)</div>
        </div>
      </div>
    </div>

    <hr />

    <div class="section">
      <h2>Notebook Overview</h2>
      <table class="notebook-table">
        <thead>
          <tr>
            <th>Step</th>
            <th>Description</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td class="step-num">01</td>
            <td>Data loading and initial inspection of both datasets</td>
          </tr>
          <tr>
            <td class="step-num">02</td>
            <td>Standardisation of Quarter column format (YYYY QX) and column naming conventions</td>
          </tr>
          <tr>
            <td class="step-num">03</td>
            <td>Data type conversion, missing value handling, and outlier treatment</td>
          </tr>
          <tr>
            <td class="step-num">04</td>
            <td>Merging of generation and treatment datasets into a single dataframe</td>
          </tr>
          <tr>
            <td class="step-num">05</td>
            <td>Exploratory Data Analysis with boxplots, histograms, and trend lines by county, waste type, and quarter</td>
          </tr>
          <tr>
            <td class="step-num">06</td>
            <td>Findings and conclusions on treatment costs, regional patterns, and seasonal trends</td>
          </tr>
        </tbody>
      </table>
    </div>

    <hr />

    <div class="section">
      <h2>Tech Stack</h2>
      <div class="tags">
        <span class="tag">Python</span>
        <span class="tag">Pandas</span>
        <span class="tag">NumPy</span>
        <span class="tag">Matplotlib</span>
        <span class="tag">Seaborn</span>
        <span class="tag">Jupyter Notebook</span>
      </div>
    </div>

    <hr />

    <div class="section">
      <h2>Authors</h2>
      <div class="authors-grid">
        <div class="author-card">
          <div class="author-name">Aiyman Mohammed</div>
          <div class="author-id">124110673</div>
        </div>
        <div class="author-card">
          <div class="author-name">Prashanth Punniyaseelan</div>
          <div class="author-id">121108055</div>
        </div>
        <div class="author-card">
          <div class="author-name">Hatice Aslihan Kutluca</div>
          <div class="author-id">124117387</div>
        </div>
        <div class="author-card">
          <div class="author-name">Hammad Imtiaz Bhatti</div>
          <div class="author-id">124118917</div>
        </div>
        <div class="author-card">
          <div class="author-name">Lehar Rana</div>
          <div class="author-id">124116767</div>
        </div>
      </div>
    </div>

  </div>
</body>
</html>
