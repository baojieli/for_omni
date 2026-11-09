# Answers — `daily_14.json`

Source: `omnifold/daily_14.json` (JSONL, 22,635 records). Temperatures converted from Kelvin to °C.

---

## 1. How many city records are in the file?

**22,635** — and all 22,635 have a distinct `city.id`, so there are 22,635 distinct cities.

## 2. How many unique countries are represented?

**243**

## 3. Which 10 countries have the most cities?

| Rank | Country | Cities |
|---:|---|---:|
| 1 | US | 2,924 |
| 2 | IN | 2,393 |
| 3 | BR | 1,194 |
| 4 | DE | 985 |
| 5 | RU | 953 |
| 6 | CN | 788 |
| 7 | JP | 752 |
| 8 | GB | 672 |
| 9 | IT | 670 |
| 10 | FR | 610 |

These 10 countries account for 11,941 of the 22,635 cities (52.8 %).

## 4. Exploded to one row per city-day, how many total rows?

**368,909 rows** — one row per `(city_id, date)`, from 15,886 cities × 16 days + 6,749 cities × 17 days.

On the `(city, country, date)` grain the count is **358,817**, because 468 name/country pairs
contain more than one distinct city (e.g. four different `Albany`s in the US).

## 5. Top 10 hottest cities by mean `temp.day` across the forecast horizon

| Rank | City | Country | Mean `temp.day` (°C) |
|---:|---|---|---:|
| 1 | Dourbali | TD | 39.81 |
| 2 | Ayorou | NE | 39.41 |
| 3 | Damaturu | NG | 39.36 |
| 4 | Maiduguri | NG | 39.35 |
| 5 | Magumeri | NG | 39.35 |
| 6 | Niamey | NE | 39.25 |
| 7 | Massakory | TD | 39.25 |
| 8 | Geidam | NG | 39.22 |
| 9 | Potiskum | NG | 39.20 |
| 10 | Daura | NG | 39.20 |

Dourbali (Chad) is the hottest city under every treatment tested, so the first place is robust.

## 6. Tidy table for San Francisco, California

16 days, 2017-03-13 → 2017-03-28. Temperatures in °C. `humidity` is `NaN` where the source has
no reading (the API stores these as `0`).

| date | temp_min (°C) | temp_max (°C) | humidity | weather_description |
|---|---:|---:|---:|---|
| 2017-03-13 | 9.81 | 18.95 | 67.0 | sky is clear |
| 2017-03-14 | 7.45 | 25.93 | 55.0 | sky is clear |
| 2017-03-15 | 8.63 | 22.75 | 56.0 | sky is clear |
| 2017-03-16 | 10.18 | 18.75 | NaN | light rain |
| 2017-03-17 | 6.50 | 18.56 | NaN | light rain |
| 2017-03-18 | 9.20 | 16.79 | NaN | light rain |
| 2017-03-19 | 10.50 | 18.08 | NaN | light rain |
| 2017-03-20 | 6.82 | 18.35 | NaN | light rain |
| 2017-03-21 | 4.57 | 16.67 | NaN | sky is clear |
| 2017-03-22 | 3.85 | 16.50 | NaN | light rain |
| 2017-03-23 | 5.21 | 12.25 | NaN | moderate rain |
| 2017-03-24 | 8.01 | 15.06 | NaN | moderate rain |
| 2017-03-25 | 5.45 | 13.59 | NaN | light rain |
| 2017-03-26 | 8.27 | 13.70 | NaN | moderate rain |
| 2017-03-27 | 5.55 | 15.79 | NaN | sky is clear |
| 2017-03-28 | 4.13 | 19.30 | NaN | sky is clear |

`San Francisco` also appears in AR, CR, PH and SV; the `country == "US"` filter selects the one
US record. The dataset has no state field, so country is the proxy for "California".
