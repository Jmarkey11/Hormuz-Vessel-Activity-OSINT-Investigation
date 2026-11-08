# Preliminary Analysis: Maritime Vessel Activity in the Persian Gulf (March 2026)

**[Read the full report (PDF)](Strait_of_Hormuz_Maritime_OSINT_Report.pdf)**

A preliminary open-source investigation into maritime vessel activity across the Persian Gulf and Gulf of Oman during the Iran conflict, March 2026. The report demonstrates how multiple open data sources can be combined to characterise a maritime picture. It is not a definitive intelligence assessment.

<!-- Optional: export one figure as PNG, upload it, and uncomment the line below -->
<!-- ![Dark vessel candidate density](figures/dark_vessel_density.png) -->

## Questions

- How did declared (AIS) vessel traffic change over the course of the conflict?
- Where are vessels operating, and how does vessel clustering relate to strategic locations?
- Can satellite imagery supplement vessel tracking data at locations of interest?

## Data Sources

| Source | Data | Resolution |
| --- | --- | --- |
| Global Fishing Watch API | AIS vessel presence | 0.1° grid (~11 km), hourly |
| Global Fishing Watch API | SAR (Sentinel-1) vessel detections | 0.1° grid (~11 km), hourly |
| Copernicus Data Space | Sentinel-2 optical imagery | 10 m |

## Method

- Analysed AIS vessel presence to establish a baseline of declared activity: spatial density, daily trends by flag state and vessel persistence.
- Identified dark vessel candidates by matching SAR radar detections against AIS records in the same grid cell and time window. Candidates with three or more SAR detections were classed as high-confidence.
- Assigned candidates to strategic zones to prioritise areas for further investigation.
- Overlaid AIS records on Sentinel-2 imagery of Bandar Abbas Naval Base to compare declared vessel presence against what was visible.

## Key Findings

- AIS activity declined 55% between 1 and 13 March, coinciding with escalation in the Strait of Hormuz, and did not return to pre-drop levels.
- 54% of identified vessels remained in the area for 15 or more days.
- 1,198 dark vessel candidates showed an eastward shift towards the Strait of Hormuz, which recorded the highest concentration (124 candidates, 21 high-confidence) and is the priority area for further investigation.
- Imagery of Bandar Abbas Naval Base on 18 March showed over 100 vessels visually present against 20 identifiable AIS records, highlighting the limits of the available data.

## Limitations

The findings are preliminary. Three limitations constrain them:

- **Low spatial resolution:** The AIS and SAR data use a 0.1° grid, about 11 km per cell.
- **Incomplete vessel identification:** 69.3% of AIS records have no vessel identification.
- **Open sources only:** No other data was available to corroborate the results.

All dark vessel identifications are candidates that need further corroboration. The report sets out collection gaps and recommended next steps.

## Tools

Python (pandas, matplotlib, plotly, folium, rasterio, contextily, scikit-learn), Global Fishing Watch API (`gfwapiclient`) and Copernicus STAC API (`pystac_client`).

*Report only: the analysis code was not retained.*

---

Jonathan Markey · April 2026
