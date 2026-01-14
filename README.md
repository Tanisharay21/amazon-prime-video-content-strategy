# Amazon Prime Video Catalog Analysis

## Overview
This project analyzes Amazon Prime's content catalog to understand its composition, content strategy, and potential areas for growth or improvement. The dataset contains metadata for movies and TV shows available on Amazon Prime as of the time of collection.

## Objectives
- Perform exploratory data analysis (EDA) on Amazon Prime's catalog.
- Assess data quality and clean the dataset for analysis.
- Engineer new features to enable deeper insights (e.g., duration normalization, content age).
- Visualize genre distribution, content type mix, and content freshness.
- Derive strategic insights about Amazon Prime’s content library.

## Dataset
**File:** `amazon_prime_titles.csv`  
**Rows:** 9,668  
**Columns:** 12  

### Columns:
- `show_id`, `type`, `title`, `director`, `cast`, `country`, `date_added`, `release_year`, `rating`, `duration`, `listed_in`, `description`

### Key Data Issues Identified:
- `date_added` → 98% missing
- `country` → 93% missing
- `director` → ~21% missing
- `cast` → ~13% missing
- `duration` stored in mixed units (minutes vs. seasons)

## Methodology

### 1. Data Inspection & Cleaning
- Loaded data and displayed random samples.
- Identified missing values and unique value counts.
- Created a raw copy for preservation.
- Cleaned text fields (strip, title case).

### 2. Feature Engineering
- Created binary indicators: `is_movie`, `is_tv_show`.
- Split `duration` into:
  - `duration_minutes` (for movies)
  - `num_seasons` (for TV shows)
- Split `listed_in` and `country` into list columns for multi-value analysis.
- Calculated `content_age` from `release_year`.
- Parsed `date_added` for freshness analysis (where available).

### 3. Analysis & Visualization
- Content type mix: 80.82% movies, 19.18% TV shows.
- Top genres: Drama, Comedy, Action, Suspense, Kids.
- Content age: Movies are older on average (~18 years) vs. TV shows (~10 years).
- Catalog appears movie-heavy with older film libraries, suggesting a cost-effective retention-focused strategy.

### 4. Visualizations
- Horizontal bar chart of top 10 genres by volume.
- Future charts could include release year trends, rating distributions, and country-wise content availability.

## Geographic Content Strategy Insights

### Key Findings:
- **High Missing Data:** Over 90% of titles lack `country` attribution, severely limiting reliable geographic analysis.
- **Heavy Concentration in US & India:** Among titles with country data, content is heavily skewed toward the United States and India.
- **Global Licensing Over Localization:** The catalog appears driven by **global licensing deals** rather than regionally curated acquisitions.

### Strategic Implications:
- **Risk of Under-Localization:** Relying on global content may limit appeal in non-core markets.
- **Localization Gaps:** Missing regional or culturally tailored content could impact subscriber retention in diverse markets.
- **Scalability vs. Depth:** The model prioritizes wide availability over deep regional customization—a cost-effective but potentially engagement-limiting approach.

### Recommendation:
Amazon Prime should consider **enhancing regional metadata** and investing in **local original content** to improve market penetration outside the US and India.

## Conclusion

This analysis reveals Amazon Prime’s content strategy as:

1. **Movie-Heavy & Older Film Library** – Cost-effective catalog bulk via legacy films.
2. **Genre-Focused on Adult Content** – Strong presence in Drama, Comedy, Action; limited kids/animation.
3. **Geographically Concentrated** – Dominated by US and Indian content with poor regional metadata.
4. **Global Over Local** – Prioritizes wide, licensable content over localized curation.

### Strategic Recommendations:
- **Increase kids/family content** to improve household retention.
- **Improve metadata completeness** (especially country and date_added).
- **Consider regional original content** to compete in localized streaming markets.

