# ODI Cricket Analysis

A data pipeline that scrapes One Day International (ODI) cricket records from ESPNcricinfo, structures the raw HTML into clean JSON, loads it into a relational database, and queries it to identify the all-time top run scorers and wicket takers.

## Overview

This project answers a straightforward question — *who are the leading ODI batsmen and bowlers of all time?* — by building an end-to-end pipeline:

1. **Scrape** the ODI records pages on ESPNcricinfo (stats.espncricinfo.com) for the top run scorers and top wicket takers, capturing each player's name, matches, runs, and wickets.
2. **Structure** the scraped HTML into a list of dictionaries and persist it to **cricket.json**.
3. **Load** the data into a MySQL database — tables **PLAYERS**, **BATSMAN**, and **BOWLER** — using pymysql.
4. **Query** the database with SQL to rank the top batsmen by career runs and the top bowlers by career wickets.

## Repository structure

| Path | Description |
| --- | --- |
| **Final_project3.ipynb** | Main notebook: scraping, JSON structuring, database load, and SQL analysis |
| **cricket.json** | Scraped dataset of top ODI batsmen and bowlers |
| **Images/** | Figures and screenshots supporting the analysis |

## Tech stack

- **Language:** Python 3
- **Scraping & parsing:** requests, json (HTML parsed with Python string methods)
- **Database:** MySQL, accessed through pymysql
- **Querying:** SQL — table definition, inserts, and ranking queries

## Sample findings

The pipeline reproduces the well-known ODI leaderboards from the scraped data — for example, SR Tendulkar leads career runs (18,426) and M Muralitharan leads career wickets (534).

## Getting started

Clone the repository:

    git clone https://github.com/RajatGoel19/odi-cricket-analysis.git
    cd odi-cricket-analysis

Install dependencies and launch the notebook:

    pip install requests pymysql jupyter
    jupyter notebook

Open **Final_project3.ipynb** and run the cells in order.

> **Note:** The load step connects to a MySQL instance. Update the connection settings (host, user, password, database) in the notebook to point at your own database before running it.
