# ⚽ Identifying the Next Mo Salah: A Statistical Similarity Model

> **🚧 STATUS: ACTIVE DEVELOPMENT (WORK IN PROGRESS)**
> *This project is currently in the active build phase. The methodology, data pipeline design, and statistical frameworks are outlined below. Code and visual outputs will be pushed in iterative phases.*

## 📌 Project Context
With Mohamed Salah potentially departing Liverpool, this project utilizes statistical similarity modeling and unsupervised machine learning to identify the most compatible data-driven replacement from across Europe's top five leagues. 

Moving beyond basic raw-stat comparisons, this pipeline employs Cosine Similarity scoring and KMeans clustering to identify player archetypes based on a 5-category performance framework (Output, Ball Progression, Creation, Dribbling, and Efficiency).

## 🛠️ Tech Stack & Arsenal
* **Language:** Python
* **Data Processing:** `pandas`, `soccerdata` (FBref scraping)
* **Machine Learning:** `scikit-learn` (KMeans Clustering, Cosine Similarity, MinMaxScaler)
* **Visualization:** `mplsoccer` (Radar charts), `seaborn`, `matplotlib`

## 📊 Data Sources & Scope
* **Primary Stats:** FBref (per-90 player metrics).
* **Market Context:** Transfermarkt (Market values, ages, contract status).
* **Filters Applied:** Minimum 900 minutes played (to remove small sample noise), Wingers/Wide Attacking Midfielders, Top 5 European Leagues.

## 🧮 Analytical Methodology

1. **Profile Definition & Normalization:** Isolate Salah's per-90 metrics. Apply `MinMaxScaler` (0–1 scale) to all player data to ensure fair comparison across different leagues and tactical contexts.
2. **Similarity Scoring:** Calculate a **Cosine Similarity** score for every qualifying player against Salah's normalized profile to produce a mathematically ranked shortlist.
3. **Unsupervised Clustering:** Apply **KMeans Clustering** to group players into tactical archetypes. Identify Salah's specific cluster to find players not just with high output, but similar structural playstyles.
4. **Feasibility Filtering:** Apply a realistic market value filter (€60M–€80M range) via Transfermarkt data to narrow the shortlist to realistic scouting targets.

## 🗺️ Project Roadmap

### Phase 1: Setup & Data Collection `[IN PROGRESS]`
- [ ] Automate FBref extraction for current season metrics.
- [ ] Apply position and minutes-played filters.
- [ ] Clean and structure into a primary DataFrame.

### Phase 2: Modeling & Clustering `[PENDING]`
- [ ] Normalize data using `MinMaxScaler`.
- [ ] Execute Cosine Similarity scoring against target profile.
- [ ] Run KMeans clustering to define player archetypes.

### Phase 3: Visualization & Reporting `[PENDING]`
- [ ] Generate comparative radar charts using `mplsoccer`.
- [ ] Build similarity score distributions and xG vs. xAG scatter plots.
- [ ] Publish final qualitative scouting profiles for the top 5 statistical matches.
