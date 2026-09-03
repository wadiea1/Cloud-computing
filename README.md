<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:e8eef7,50:cfe0f5,100:b5cdea&height=200&section=header&text=Cloud%20Computing&fontSize=52&fontColor=1a1a2e&animation=fadeIn&fontAlignY=35&desc=Lab%20Notebooks%20%E2%80%94%20Colab%2C%20Open%20Data%20APIs%2C%20Visualization%20%26%20Firebase&descSize=15&descAlignY=55&descColor=2d3748" width="100%"/>

<p>
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python"/>
  <img src="https://img.shields.io/badge/Jupyter-F37626?style=for-the-badge&logo=jupyter&logoColor=white" alt="Jupyter"/>
  <img src="https://img.shields.io/badge/Google_Colab-F9AB00?style=for-the-badge&logo=googlecolab&logoColor=white" alt="Colab"/>
  <img src="https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white" alt="Pandas"/>
  <img src="https://img.shields.io/badge/Plotly-3F4F75?style=for-the-badge&logo=plotly&logoColor=white" alt="Plotly"/>
  <img src="https://img.shields.io/badge/Firebase-FFCA28?style=for-the-badge&logo=firebase&logoColor=black" alt="Firebase"/>
</p>

<p>
  <img src="https://img.shields.io/badge/Type-Course_Labs-4A5568?style=flat-square" alt="Type"/>
  <img src="https://img.shields.io/badge/Notebooks-6-4A5568?style=flat-square" alt="Notebooks"/>
  <img src="https://img.shields.io/badge/Institution-Braude_College-4A5568?style=flat-square" alt="Institution"/>
</p>

</div>

---

## 📖 Overview

A collection of **cloud computing laboratory exercises**, built and run in **Google Colab**.
The labs work through a practical progression: from first steps in a hosted notebook
environment, to building **interactive UIs** inside notebooks, consuming **live open-data REST
APIs**, analysing and **visualizing** the results, and finally reading and writing to a
**cloud-hosted NoSQL database**.

Every notebook runs entirely in the browser — no local setup required.

---

## 📓 Lab Notebooks

| Notebook | Topic | Key Libraries |
|---|---|---|
| [`MyfirstColab.ipynb`](MyfirstColab.ipynb) | **Colab fundamentals** — notebook basics, mounting Google Drive, reading CSV files, first interactive widgets | `google.colab`, `csv`, `numpy`, `ipywidgets` |
| [`Lab2.ipynb`](Lab2.ipynb) | **Interactive UIs over JSON** — building widget-driven interfaces that load and filter structured records | `ipywidgets`, `json`, `IPython.display` |
| [`tergol4.ipynb`](tergol4.ipynb) | **Open-data REST API + charts** — querying a live government dataset and plotting aggregates as bar charts | `requests`, `pandas`, `matplotlib` |
| [`Lab4.ipynb`](Lab4.ipynb) | **Data analysis & advanced visualization** — API ingestion into DataFrames, then statistical plots and interactive scatter plots | `pandas`, `seaborn`, `plotly`, `matplotlib` |
| [`cloud4.ipynb`](cloud4.ipynb) | Working copy of the Lab 4 exercise | *same as above* |
| [`tergol5.ipynb`](tergol5.ipynb) | **Cloud NoSQL database** — full CRUD against a Firebase Realtime Database | `firebase`, `time` |

---

## 🧠 Topics Covered

### ☁️ Cloud Notebook Environments
Running Python on managed cloud infrastructure with **Google Colab** — mounting Drive for
persistent storage, installing packages at runtime, and sharing executable notebooks.

### 🎛️ Interactive Notebook Applications
Using **`ipywidgets`** to turn static notebooks into small applications — dropdowns, buttons and
output areas wired to callbacks, with `clear_output` for live-updating views.

### 🌐 Consuming Open-Data REST APIs
Querying the **Israeli government open-data portal** ([data.gov.il](https://data.gov.il)) through
its CKAN `datastore_search` endpoint:

```python
url = "https://data.gov.il/api/3/action/datastore_search"
response = requests.get(url, params={"resource_id": "...", "limit": 32000})
records = response.json()["result"]["records"]
df = pd.DataFrame(records)
```

This covers the realistic cloud workflow: paginated API requests, JSON parsing, type coercion
with `pd.to_numeric`, and loading remote data into a DataFrame for analysis.

### 📊 Data Analysis & Visualization
Three complementary plotting stacks, each chosen for a different purpose:

| Library | Used for |
|---|---|
| **Matplotlib** | Bar charts, axis/label/grid control, figure composition |
| **Seaborn** | Statistical summaries such as category count plots |
| **Plotly Express** | Interactive scatter plots with hover and zoom |

### 🔥 Cloud NoSQL — Firebase Realtime Database
Complete **CRUD** against a hosted Firebase Realtime Database using the Python client:

```python
from firebase import firebase
app = firebase.FirebaseApplication("https://<your-db>.firebaseio.com/", None)

app.post("/collection", data)     # Create
app.get("/collection", None)      # Read
app.put("/collection", key, val)  # Update
app.delete("/collection", key)    # Delete
```

Demonstrates how an application persists state in the cloud without managing a server.

---

## 🚀 Getting Started

### Run in Colab (recommended)

Every notebook carries an **Open in Colab** badge at the top — click it and the notebook opens,
ready to run, with no installation.

### Run locally

```bash
pip install jupyter pandas numpy matplotlib seaborn plotly requests ipywidgets firebase
jupyter notebook
```

> **Notes for local runs**
> - Replace the `google.colab` Drive-mount cell with a local file path.
> - `ipywidgets` needs the Jupyter widgets extension enabled to render controls.
> - The Firebase lab requires your own database URL and credentials.

---

## 🛠️ Tech Stack

<div align="center">

| Category | Tools |
|---|---|
| **Language** | Python 3 |
| **Environment** | Google Colab · Jupyter Notebook |
| **Data** | `pandas`, `numpy`, `json`, `csv` |
| **HTTP / APIs** | `requests` · CKAN `datastore_search` |
| **Visualization** | `matplotlib`, `seaborn`, `plotly` |
| **Interactivity** | `ipywidgets`, `IPython.display` |
| **Cloud Services** | Google Drive · Firebase Realtime Database |

</div>

---

## 📂 Repository Contents

| File | Description |
|---|---|
| 📓 `*.ipynb` | The six lab notebooks described above |
| 📄 `students.json` | Sample structured dataset used by the widget labs |
| 📘 `HW1_BEE.docx` · `HW2_BEE.docx` · `HW3_BEE.docx` | Course homework assignments and written solutions |
| 📗 `Bee_FinalProject.docx` | Final project report |

---

## 👤 Author

**Wadiea Farran**
Software Engineering — Braude College of Engineering

<a href="https://github.com/wadiea1">
  <img src="https://img.shields.io/badge/GitHub-wadiea1-181717?style=for-the-badge&logo=github&logoColor=white" alt="GitHub"/>
</a>

---

<div align="center">
<img src="https://capsule-render.vercel.app/api?type=waving&color=0:b5cdea,50:cfe0f5,100:e8eef7&height=120&section=footer" width="100%"/>
</div>
