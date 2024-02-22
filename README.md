---
datapackage:
  title: VIX - CBOE Volatility Index
  description: CBOE Volatility Index (VIX) time-series dataset including daily open, close, high and low. The CBOE Volatility Index (VIX) is a key measure of market expectations of near-term volatility conveyed by S&P 500 stock index option prices introduced in 1993.
  licenses:
  - id: odc-pddl
    name: open_data_commons_public_domain_dedication_and_license_v1.0
    path: http://opendatacommons.org/licenses/pddl/
    title: Open Data Commons Public Domain Dedication and License v1.0
  resources:
  - format: csv
    mediatype: text/csv
    name: vix-daily
    path: data/vix-daily.csv
    schema:
      fields:
      - name: Date
        type: date
      - name: VIX Open
        type: number
      - name: VIX High
        type: number
      - name: VIX Low
        type: number
      - name: VIX Close
        type: number
    title: VIX Daily
---

[Here is the source file on GitHub](https://github.com/datopian/datarich-demo/blob/main/posts/story2.md) used to render this page.
