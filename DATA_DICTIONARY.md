# Data Dictionary: tmdb_clean.csv (15,386 rows, 2000-2025)

| Column | Type | Description | Range / Notes |
|--------|------|-------------|---------------|
| id | int | TMDB movie ID (unique key) | no duplicates |
| title | text | Movie title | |
| release_date | datetime | Release date | 2000-01-01 to 2025-12-31 |
| original_language | categorical | ISO 639-1 code | 89 languages, top 10 = 84.9% |
| overview | text | Plot summary (used for text mining) | no empty values |
| popularity | float | TMDB popularity score | 0.01 - 92.5, right-skewed |
| vote_average | float | Mean user rating | 1.2 - 10.0, median 6.1 |
| vote_count | int | Number of votes | 10 - 34,747, median 30 |
| genres | list | Genre names (mapped from genre_ids) | 19 genres, multi-label |
| release_year | int | Derived from release_date | 2000 - 2025 |
| low_votes | bool | Derived: vote_count < 20 | 34.5% True (noisy ratings) |

Cleaning: removed 169 rows (empty overview, missing genres/dates, invalid values); no duplicates or NaNs remain.
Dropped fields: adult, backdrop_path, original_title, poster_path, softcore, video.