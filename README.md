# Posit Assistant Lounge at posit::conf(2026)

Use Posit Assistant to explore one of the following datasets!

## Edible plants (`edible-plants.csv`)

The Edible Plant Database from the GROW Observatory, a European citizen science project on growing food and monitoring soil. Covers 140 plants.

Read it with `readr::read_csv()` in R or `polars.read_csv()` in Python.

### Questions to start with

- Do plants that require more sunlight also require higher temperatures?
- Which cultivation classes require the most water?
- How many distinct values does each category column really contain? Count them before you group by anything.
- Which plants can share a bed? Look at `cultivation` alongside the pH and nutrient columns.

### Source

[TidyTuesday 2026-02-03](https://github.com/rfordatascience/tidytuesday/tree/main/data/2026/2026-02-03), curated by [Nicola Rennie](https://github.com/nrennie). Underlying data from the [Edible Plant Database](https://discovery.dundee.ac.uk/en/datasets/edible-plant-database/), GROW Observatory.

## Pokemon (`pokemon.xlsx`)

Names, types, base stats, colors, and egg groups for 949 Pokemon, from the {pokemon} R package. Two sheets: `pokemon` holds 949 rows and 22 columns, and `data_dictionary` describes each column.

Read it with `readxl::read_excel()` in R or `polars.read_excel()` in Python. Missing values are blank cells rather than a text placeholder, so numeric columns stay numeric.

### Questions to start with

- Which types have the highest base stats, and does that hold up across generations?
- Do heavier Pokemon hit harder, or is weight unrelated to attack?
- What units are `height` and `weight` in? Check one Pokemon you already know.
- Every row has a unique `id`, but `species_id` repeats. What are the extra rows?

### Source

[TidyTuesday 2025-04-01](https://github.com/rfordatascience/tidytuesday/tree/main/data/2025/2025-04-01), curated by [Frank Hull](https://github.com/frankiethull). Underlying data from the [{pokemon} R package](https://github.com/williamorim/pokemon).

## Palomar spectroscopic survey (`palomar-survey.parquet`)

Spectroscopic observations and nuclear activity classifications for 486 nearby galaxies, from the Palomar survey carried out with the 200-inch Hale Telescope.

Read it with `arrow::read_parquet()` in R or `polars.read_parquet()` in Python. Every column carries a `description` in its Parquet field metadata, and the categorical columns are dictionary-encoded, so they arrive as factors in R and as `Categorical` columns in polars instead of bare character vectors.

### Questions to start with

- What types of nuclear activity are most common, and how does that vary with galaxy morphology?
- Can you recreate the classic BPT diagnostic diagram from the emission-line ratios? Where do the different activity types fall?
- Is there a relationship between velocity dispersion, a proxy for central mass, and the type of nuclear activity?
- Do the four `log_` columns hold what their names promise? Look at the range of values before you trust an axis label.

### Source

[TidyTuesday 2026-08-11](https://github.com/rfordatascience/tidytuesday/tree/main/data/2026/2026-08-11), curated by [Tony Galvan](https://github.com/gdatascience). Underlying data from Ho, Filippenko & Sargent (1995, 1997, 2009) via VizieR.

## Country music lyrics (`country-music.duckdb`)

A DuckDB database of every country song that reached the Top 30 of Billboard's Country Airplay chart between 2013 and 2019, with full lyrics and writing and production credits.

Open it with Positron's Data Connections, or with the `duckdb` package in R or with `duckdb.connect()` in Python.

### Tables

| Table | Rows | Description |
|:---|---:|:---|
| `songs` | 484 | One row per song. `song_id` is the primary key. Includes full `lyrics`. |
| `song_writers` | 1,495 | One row per songwriter credit. Joins to `songs` on `song_id`. |
| `song_producers` | 751 | One row per producer credit. Joins to `songs` on `song_id`. |
| `top_all_writers` | 510 | Published summary of songwriter credit counts. |
| `top_primary_writers` | 71 | Published summary of writer counts, as distributed upstream. |
| `top_producers` | 110 | Published summary of producer credit counts. |

### Questions to start with

- Is country radio run by a small circle of hitmakers? Count how many of the 484 songs the top few writers touch.
- How has the country vocabulary shifted over time? Search `songs.lyrics` for trucks, beer, or blue jeans by year.
- Do the most prolific writers also work with the most producers?

### Source

[TidyTuesday 2026-08-25](https://github.com/rfordatascience/tidytuesday/tree/main/data/2026/2026-08-25), curated by [Ntobeko Sosibo](https://github.com/afrikaniz3d-za). Underlying data collected by [Grady Smith](https://www.youtube.com/@GradySmith) for his video ["Every country song has these lyrics. Right?"](https://www.youtube.com/watch?v=48ZxNFGJTo8).

