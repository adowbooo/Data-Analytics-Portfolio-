# Tubi Movie Catalog Analysis and Dashboard

## Project Overview

-# data set from Kaggle

Tubi is an online streaming platform. The dataset provided has movie titles with columns for Age Rating, Release Date, and Film Duration.

Since the dataset is pretty much an inventory of a business, that's where I wanted my analysis to focus. This project aims to provide insights on the following:
  * Movie Catalog Diversity per Genre, Era, and Age Rating
  * Film Duration relationships with the rest of the data.

## Data Validation and Cleaning

When starting a project, I always make it a point to make a copy of the original spreadsheet so that I can keep an unmodified copy that I can reference from time to time. Afterwards, I took a quick look at the type of data that I will be working with. At a quick glance: I noticed the following impediments that would need cleaning:
 * Duration values are in text format with "hr" and "min"
 * Duration values that are over or equal to 2 hours have non-breaking spaces in them.
 * Movie titles with multiple genres have their genre value appended.
 * Sort each release year into eras

To clean the Duration values:
 * I used the Find and Replace feature in Excel to look for " hr" and "hr" and replace them with ":".
 * Used Find and Replace again to replace "min" with "".
 * I then applied a custom Time formatting to the resulting values.

<img width="150" height="103" alt="image" src="https://github.com/user-attachments/assets/d4ce25fe-36f1-43dc-b295-7682b0444cb0" />

To clean the movie titles having appended movie genres, I used Power Query to separate them and populate them into rows.

<img width="352" height="184" alt="image" src="https://github.com/user-attachments/assets/8cf18a3b-93f6-405b-9e3e-dfbb2f5a6ae1" />

To convert the release year into eras by decade, I used the FLOOR() function and appended "s" at the end of each return value.

## Initial Analysis and Visualization
One of the things that I was most interested about was the inclusion of film duration, I wanted to find out if it had any relationship with the other categories. Additionally Tubi's catalog diversity is also one of the mane focus of this study. For these analysis, I utilized Excel's Charts and PivotTables to quickly generate aggregated values and visualization.

### Film Duration and Release Year

<img width="476" height="279" alt="image" src="https://github.com/user-attachments/assets/6bffe3f9-f6a8-4433-a6cb-2bca47f643fc" />

### Film Duration and Age Rating

<img width="483" height="288" alt="image" src="https://github.com/user-attachments/assets/744e7bba-78e0-4f94-b228-a294345cc30e" />

## Film Duration and Genre

<img width="479" height="286" alt="image" src="https://github.com/user-attachments/assets/93b789c9-3883-40a8-961f-85d0240f1759" />

Quickly looking at these charts, we can say that there film duration has no relevance to age rating and the year the film was released in. We might notice that there might be a trend in the relationship between film duration and genre but all of the total values all sit at around the overall average film duration. Overall, we can't really make a relevant analysis with the film duration data because the dataset is limited to what movies Tubi is actually offering, not the entire movie catalog that was ever released.

### Tubi Movie Catalogue Diversity

Moving forward, i focused on the diversity of the Tubi movie catalogue so that stakeholders can see the gaps and dominance in the entire movie selections based on: Genres, Film Era, and Age Rating.

<img width="1583" height="750" alt="image" src="https://github.com/user-attachments/assets/79e749f4-3619-4afd-8324-3ea92a7335fa" />

## Findings

This report analyzes the content distribution, genre density, release eras, and content rating profile of Tubi’s movie library. By normalizing multi-genre tags and categorizing film runtimes and eras within Excel, the analysis uncovers clear catalog patterns: Tubi’s offerings are heavily weighted toward modern releases, strongly anchored by core popular genres like Drama and Comedy, and targeted primarily toward broad teen and mature audiences.

### Genre Composition and Diversity
 * **Core Catalog Anchors:** Drama (34.19X% of total titles) and Comedy (26.45%) represent the largest volume within the catalog. These two foundational genres drive the majority of listings and frequently serve as anchor categories in multi-genre pairings.
 * **Underrepresented Categories:** Genres such as Musical ([X titles]), War ([X titles]), and Adult ([X titles]) show minimal representation across the platform.

### Temporal Distribution
 * **Modern Expansion:** The catalog is heavily skewed toward modern releases. Movies released from 2010 onwards account for 62% of all catalog offerings, highlighting a strategy focused on contemporary digital distributions and modern titles.
 * **Legacy Film Diversity Deficit:** Older eras (pre-2000s) exhibit lower overall genre diversity compared to recent decades. Modern additions feature a much broader range of multi-genre classifications, whereas older titles concentrate heavily within traditional Drama, Action, and Western categories.

### Maturity and Content Rating Profile
 - **Teen & General Audience Dominance:** The majority of the catalog falls under general-to-teen viewing classifications (e.g., PG, PG-13, and TV-14), comprising 86.43% of total movies.
 - *Mature Content Segment:* While family and teen content forms the primary baseline, mature-targeted titles (R and TV-MA rated) still make up a substantial secondary portion ([X%]), giving the platform balanced coverage between general and adult viewership.

## Key Takeaways
 - **Niche Acquisition Opportunities:** Addressing gaps in underrepresented categories like Musicals and War films could capture niche cinephile demographics currently underserved by the platform.
 - **Legacy Library Enrichment:** Diversifying the variety of older films (pre-2000s) could improve engagement for retro movie enthusiasts seeking classic library breadth.
