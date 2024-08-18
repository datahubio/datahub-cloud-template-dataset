---
title: "Add visuals and data-rich components"
---

<div className="hero">
    <p className="hero-description">With Datahub Cloud, you can easily add various visual and data-rich components to your datasets or data stories, making them more engaging and insightful. This section will guide you through the process of incorporating charts, graphs, and other visual elements to bring your data to life.</p>
</div>

> [!info] Github is playing the role of your Editor.
> Any changes you want to make to your published site, you need to make in your GitHub repository first.
> Once you hit "sync" on your Site dashboard, the changes get reflected on your published site (unless you turn on the Auto-sync)

You can check the full list and API of the available features here [https://storybook.portaljs.org](https://storybook.portaljs.org)

# Table of Contents 

# Inserting a component 

1. Select the desired component you want to add from the sidebar list:

![[./assets/Screenshot1.png]]

2. Click on "Docs"
3. Hit "Show code" at the bottom right of the showcased feature

![[./assets/Screenshot2.png]]

6. Copy-paste the code into your markdown file in your GitHub repository
7. Commit the changes made
8. Navigate back to the App and hit "Sync"
9. Visit your site or refresh the page in order to see the reflected changes

> [!info] To import a feature from URL, simply upload your data file to your Github repository and replace the URL in the copied code. Relative paths are supported.
> For concrete examples, please continue reading.

## Different ways to insert a component 

Depending on the type of feature you selected from the list https://storybook.portaljs.org, you need to copy-paste the code block into your md file and:

1) update the params _(refer to the params in the docs and their description)_ or
2) update the CSV link with the link of your data file (you can also use a relative path) or
3) update the URL to one of your own file and
4) Publish it with Datahub Cloud and share it with the world!

# What features are supported?

You can use several data preview and data visualization components to make your dataset more insightful.

> [!hint]
> If the feature you need isn't on the list, ping us on [discord](https://discord.gg/KZSf3FG4EZ) or create an issue in the [datahub repository](https://github.com/datopian/datahub/issues) requesting it and we promise to look into it! 

## Catalog 

If your dataset is part of a larger dataset collection, you may want to start by listing the related datasets here in a catalog-like component with search and facets like this one: 

<Catalog
  datasets={[
    {
      _id: '07026b22d49916754df1dc8ffb9ccd1c31878aae',
      file_path: 'https://github.com/datasets/awesome-data/blob/master/climate-change.md',
      metadata: {
        'details-of-task': 'Detect and categorise abusive language in social media data',
        collection: 'Climate data',
        'level-of-annotation': [
          'Posts'
        ],
        'link-to-data': 'https://doi.org/10.6084/m9.figshare.19333298.v1',
        'link-to-publication': 'https://arxiv.org/abs/2107.13592',
        medium: [
          'Text'
        ],
        'percentage-abusive': 13.2,
        platform: [
          'Instagram',
          'Youtube'
        ],
        reference: 'Nurce, E., Keci, J., Derczynski, L., 2021. Detecting Abusive Albanian. arXiv:2107.13592',
        'size-of-dataset': 11874,
        'task-description': 'Hierarchical (offensive/not; untargeted/targeted; person/group/other)',
        title: 'Climate Change'
      },
      url_path: 'dataset-4'
    },
    {
      _id: '42c86cf3c4fbbab11d91c2a7d6dcb8f750bc4e19',
      file_path: 'https://github.com/datasets/awesome-data/blob/master/economic-data.md',
      metadata: {
        'details-of-task': 'Enriched versions of the OffensEval/OLID dataset with the distinction of explicit/implicit offensive messages and the new dimension for abusive messages. Labels for offensive language: EXPLICIT, IMPLICT, NOT; Labels for abusive language: EXPLICIT, IMPLICT, NOTABU',
        collection: 'Economy',
        'level-of-annotation': [
          'Tweets'
        ],
        'link-to-data': 'https://github.com/tommasoc80/AbuseEval',
        'link-to-publication': 'http://www.lrec-conf.org/proceedings/lrec2020/pdf/2020.lrec-1.760.pdf',
        medium: [
          'Text'
        ],
        'percentage-abusive': 20.75,
        platform: [
          'Twitter'
        ],
        reference: 'Caselli, T., Basile, V., Jelena, M., Inga, K., and Michael, G. 2020. "I feel offended, don’t be abusive! implicit/explicit messages in offensive and abusive language". The 12th Language Resources and Evaluation Conference (pp. 6193-6202). European Language Resources Association.',
        'size-of-dataset': 14100,
        'task-description': 'Explicitness annotation of offensive and abusive content',
        title: 'Economic Data and Indicators'
      },
      url_path: 'dataset-1'
    },
    {
      _id: '80001dd32a752421fdcc64e91fbd237dc31d6bb3',
      file_path: 'https://github.com/datasets/awesome-data/blob/master/stock-market-data.md',
      metadata: {
        'details-of-task': 'Incivility',
        collection: 'Stock Market',
        'level-of-annotation': [
          'Posts'
        ],
        'link-to-data': 'http://alt.qcri.org/~hmubarak/offensive/AJCommentsClassification-CF.xlsx',
        'link-to-publication': 'https://www.aclweb.org/anthology/W17-3008',
        medium: [
          'Text'
        ],
        'percentage-abusive': 0.81,
        platform: [
          'AlJazeera'
        ],
        reference: 'Mubarak, H., Darwish, K. and Magdy, W., 2017. Abusive Language Detection on Arabic Social Media. In: Proceedings of the First Workshop on Abusive Language Online. Vancouver, Canada: Association for Computational Linguistics, pp.52-56.',
        'size-of-dataset': 32000,
        'task-description': 'Ternary (Obscene, Offensive but not obscene, Clean)',
        title: 'Stock Market Data'
      },
      url_path: 'dataset-2'
    },
    {
      _id: '96649d05d8193f4333b10015af76c6562971bd8c',
      file_path: 'https://github.com/datasets/awesome-data/blob/master/air-pollution.md',
      metadata: {
        'details-of-task': 'Detectioning CDC from abusive comments',
        collection: 'Climate data',
        'level-of-annotation': [
          'Posts'
        ],
        'link-to-data': 'https://github.com/shekharRavi/CoRAL-dataset-Findings-of-the-ACL-AACL-IJCNLP-2022',
        'link-to-publication': 'https://aclanthology.org/2022.findings-aacl.21/',
        medium: [
          'Newspaper Comments'
        ],
        'percentage-abusive': 100,
        platform: [
          'Posts'
        ],
        reference: 'Ravi Shekhar, Mladen Karan and Matthew Purver (2022). CoRAL: a Context-aware Croatian Abusive Language Dataset. Findings of the ACL: AACL-IJCNLP.',
        'size-of-dataset': 2240,
        'task-description': 'Multi-class based on context dependency categories (CDC)',
        title: 'Air pollution data'
      },
      url_path: 'dataset-3'
    }
  ]}
  facets={[
    'collection',
    'platform'
  ]}
/>

Simply copy and paste the following code snippet in the markdown file in your Github repository:

```
<Catalog
  datasets={[
    {
      _id: '07026b22d49916754df1dc8ffb9ccd1c31878aae',
      metadata: {
        'details-of-task': 'Detect and categorise abusive language in social media data',
        language: 'Albanian',
        'level-of-annotation': [
          'Posts'
        ],
        'link-to-data': 'https://doi.org/10.6084/m9.figshare.19333298.v1',
        'link-to-publication': 'https://arxiv.org/abs/2107.13592',
        medium: [
          'Text'
        ],
        'percentage-abusive': 13.2,
        platform: [
          'Instagram',
          'Youtube'
        ],
        reference: 'Nurce, E., Keci, J., Derczynski, L., 2021. Detecting Abusive Albanian. arXiv:2107.13592',
        'size-of-dataset': 11874,
        'task-description': 'Hierarchical (offensive/not; untargeted/targeted; person/group/other)',
        title: 'Detecting Abusive Albanian'
      },
      url_path: 'dataset-4'
    },
    {
      _id: '42c86cf3c4fbbab11d91c2a7d6dcb8f750bc4e19',
      file_path: 'content/dataset-1/index.md',
      metadata: {
        'details-of-task': 'Enriched versions of the OffensEval/OLID dataset with the distinction of explicit/implicit offensive messages and the new dimension for abusive messages. Labels for offensive language: EXPLICIT, IMPLICT, NOT; Labels for abusive language: EXPLICIT, IMPLICT, NOTABU',
        language: 'English',
        'level-of-annotation': [
          'Tweets'
        ],
        'link-to-data': 'https://github.com/tommasoc80/AbuseEval',
        'link-to-publication': 'http://www.lrec-conf.org/proceedings/lrec2020/pdf/2020.lrec-1.760.pdf',
        medium: [
          'Text'
        ],
        'percentage-abusive': 20.75,
        platform: [
          'Twitter'
        ],
        reference: 'Caselli, T., Basile, V., Jelena, M., Inga, K., and Michael, G. 2020. "I feel offended, don’t be abusive! implicit/explicit messages in offensive and abusive language". The 12th Language Resources and Evaluation Conference (pp. 6193-6202). European Language Resources Association.',
        'size-of-dataset': 14100,
        'task-description': 'Explicitness annotation of offensive and abusive content',
        title: 'AbuseEval v1.0'
      },
      url_path: 'dataset-1'
    },
    {
      _id: '80001dd32a752421fdcc64e91fbd237dc31d6bb3',
      file_path: 'content/dataset-2/index.md',
      metadata: {
        'details-of-task': 'Incivility',
        language: 'Arabic',
        'level-of-annotation': [
          'Posts'
        ],
        'link-to-data': 'http://alt.qcri.org/~hmubarak/offensive/AJCommentsClassification-CF.xlsx',
        'link-to-publication': 'https://www.aclweb.org/anthology/W17-3008',
        medium: [
          'Text'
        ],
        'percentage-abusive': 0.81,
        platform: [
          'AlJazeera'
        ],
        reference: 'Mubarak, H., Darwish, K. and Magdy, W., 2017. Abusive Language Detection on Arabic Social Media. In: Proceedings of the First Workshop on Abusive Language Online. Vancouver, Canada: Association for Computational Linguistics, pp.52-56.',
        'size-of-dataset': 32000,
        'task-description': 'Ternary (Obscene, Offensive but not obscene, Clean)',
        title: 'Abusive Language Detection on Arabic Social Media (Al Jazeera)'
      },
      url_path: 'dataset-2'
    },
    {
      _id: '96649d05d8193f4333b10015af76c6562971bd8c',
      file_path: 'content/dataset-3/index.md',
      metadata: {
        'details-of-task': 'Detectioning CDC from abusive comments',
        language: 'Croatian',
        'level-of-annotation': [
          'Posts'
        ],
        'link-to-data': 'https://github.com/shekharRavi/CoRAL-dataset-Findings-of-the-ACL-AACL-IJCNLP-2022',
        'link-to-publication': 'https://aclanthology.org/2022.findings-aacl.21/',
        medium: [
          'Newspaper Comments'
        ],
        'percentage-abusive': 100,
        platform: [
          'Posts'
        ],
        reference: 'Ravi Shekhar, Mladen Karan and Matthew Purver (2022). CoRAL: a Context-aware Croatian Abusive Language Dataset. Findings of the ACL: AACL-IJCNLP.',
        'size-of-dataset': 2240,
        'task-description': 'Multi-class based on context dependency categories (CDC)',
        title: 'CoRAL: a Context-aware Croatian Abusive Language Dataset'
      },
      url_path: 'dataset-3'
    }
  ]}
  facets={[
    'language',
    'platform'
  ]}
/>
```

Now update the values to reflect your datasets data (title, path) and the facet values relevant to your data. 

## Excel 

If you're working a lot with Excel files, you can embed a preview of your file such as this one:

<Excel data={{
  url: "https://storage.portaljs.org/IC-Gantt-Chart-Project-Template-8857.xlsx"
}} />

This component allows you to present all tabs in your Excel file. You can sort the rows by clicking on the Column name and you can also filter each column by clicking on the triple bar symbol next to the Column name.

Simply copy and paste the following code snippet in the markdown file in your Github repository:

```
<Excel
  data={{
    url: 'https://storage.portaljs.org/IC-Gantt-Chart-Project-Template-8857.xlsx'
  }}
 />
```

Then upload your Excel file to your Github repository and replace the URL with the URL of the uploaded file (absolute and relative paths are supported). 

## Data Table

Let's continue by adding a table of your data like the one below:

<FlatUiTable data={{
  url: "https://storage.openspending.org/alberta-budget/__os_imported__alberta_total.csv"
}} />

Simply copy and paste the following code snippet in the markdown file in your Github repository:

```
<FlatUiTable
  data={{
    url: 'https://storage.openspending.org/alberta-budget/__os_imported__alberta_total.csv'
  }}
 />
```

 To get this data replaced with your data, upload your csv file to your repository and update the URL 

## Iframe

If you're working with Microsoft Power BI reports or Google Lookerstudio or any similar, you can embed them within your page as follows:

<Iframe
  data={{
    url: 'https://app.powerbi.com/view?r=eyJrIjoiYzBmN2Q2MzYtYzE3MS00ODkxLWE5OWMtZTQ2MjBlMDljMDk4IiwidCI6Ijk1M2IwZjgzLTFjZTYtNDVjMy04MmM5LTFkODQ3ZTM3MjMzOSIsImMiOjh9'
  }}
  style={{
    height: '100%',
    width: '100%'
  }}
/>

Simply copy and paste the following code snippet in the markdown file in your GitHub repository:

```
<Iframe
  data={{
    url: 'https://app.powerbi.com/view?r=eyJrIjoiYzBmN2Q2MzYtYzE3MS00ODkxLWE5OWMtZTQ2MjBlMDljMDk4IiwidCI6Ijk1M2IwZjgzLTFjZTYtNDVjMy04MmM5LTFkODQ3ZTM3MjMzOSIsImMiOjh9'
  }}
  style={{
    height: '100%',
    width: '100%'
  }}
/>
```

The only thing you need to do after that is to replace the URL with the correct one.


## PdfViewer

You can also embed a view of a PDF file such as this one:

<PdfViewer
  data={{
    url: 'https://cdn.filestackcontent.com/wcrjf9qPTCKXV3hMXDwK'
  }}
  parentClassName="h-96"
/>

Simply copy and paste the following code snippet in the markdown file in your Github repository:

```
<PdfViewer
  data={{
    url: 'https://cdn.filestackcontent.com/wcrjf9qPTCKXV3hMXDwK'
  }}
  parentClassName="h-96"
/>
```

Then update the url to lead to your pdf file.

> [!tip]
> The easiest way would be to upload it to the Github repository and use the relative/absolute path

## Line and Bar Charts

Here's a quick line chart:

<LineChart
  data={{
    url: "data.csv"
  }}
  title="Annual CO2 Emissions"
  xAxis="year"
  yAxis="co2"
/>

You can add this line chart component by simply: 

1) Uploading your data CSV file to your repository
2) Copy-pasting the below snippet into the markdown file in your repository
3) Updating the URL (relative path)
4) Updating the params (data, title, xAxis, yAxis) to reflect the relevant data

```
<LineChart
  data={{
    url: "data.csv"
  }}
  title="Annual CO2 Emissions"
  xAxis="year"
  yAxis="co2"
/>
```

> [!note]
> There are also other types of charts and graphs you can use to enhance your dataset. You can create charts with Plotly or VegaLite.

### Plotly charts

> [!info] Bar Chart

You can insert a Plotly Bar Chart like this one:

<PlotlyBarChart
  data={{
    url: 'https://raw.githubusercontent.com/plotly/datasets/master/finance-charts-apple.csv'
  }}
  title="Apple Stock Prices"
  xAxis="Date"
  yAxis="AAPL.Open"
/>

Simply copy and paste the following code snippet and update the URL and the title, xAxis, yAxis to reflect your data points:

```
<PlotlyBarChart
  data={{
    url: 'https://raw.githubusercontent.com/plotly/datasets/master/finance-charts-apple.csv'
  }}
  title="Apple Stock Prices"
  xAxis="Date"
  yAxis="AAPL.Open"
/>
```



> [!info] Line Chart

Same goes for this Line Chart:

<PlotlyLineChart
  data={{
    url: 'https://raw.githubusercontent.com/datasets/oil-prices/main/data/wti-year.csv'
  }}
  title="Oil Price x Year"
  xAxis="Date"
  yAxis="Price"
/>

Copy and paste the following code snippet and update the URL and the title, xAxis, yAxis to reflect your data points:

```
<PlotlyLineChart
  data={{
    url: 'https://raw.githubusercontent.com/datasets/oil-prices/main/data/wti-year.csv'
  }}
  title="Oil Price x Year"
  xAxis="Date"
  yAxis="Price"
/>
```

### VegaLite Charts

> [!info] VegaLite Charts are also supported

<VegaLite
  data={{
    table: [
      {
        x: 1850,
        y: -0.418
      },
      {
        x: 2020,
        y: 0.923
      }
    ]
  }}
  spec={{
    $schema: 'https://vega.github.io/schema/vega-lite/v4.json',
    data: {
      name: 'table'
    },
    encoding: {
      x: {
        field: 'x',
        type: 'ordinal'
      },
      y: {
        field: 'y',
        type: 'quantitative'
      }
    },
    mark: 'bar'
  }}
/>

If you want to add it, copy paste the below snippet and insert it in your markdown file:

```
<VegaLite
  data={{
    table: [
      {
        x: 1850,
        y: -0.418
      },
      {
        x: 2020,
        y: 0.923
      }
    ]
  }}
  spec={{
    $schema: 'https://vega.github.io/schema/vega-lite/v4.json',
    data: {
      name: 'table'
    },
    encoding: {
      x: {
        field: 'x',
        type: 'ordinal'
      },
      y: {
        field: 'y',
        type: 'quantitative'
      }
    },
    mark: 'bar'
  }}
/>
```

Now update the values to reflect your data points and you're done!

## Map

In case you're dealing with geo data, you can visualize your data on a GeoJSON polygons and points map with auto zoom in the points layer:

<Map
  autoZoomConfiguration={{
    layerName: 'Points'
  }}
  center={{
    latitude: 45,
    longitude: 0
  }}
  layers={[
    {
      data: {
        url: 'https://opendata.arcgis.com/datasets/9c58741995174fbcb017cf46c8a42f4b_25.geojson'
      },
      name: 'Points',
      tooltip: true
    },
    {
      colorScale: {
        ending: '#00ff00',
        starting: '#ff0000'
      },
      data: {
        url: 'https://d2ad6b4ur7yvpq.cloudfront.net/naturalearth-3.3.0/ne_10m_geography_marine_polys.geojson'
      },
      name: 'Polygons',
      tooltip: true
    }
  ]}
  title="Polygons and points"
  zoom={2}
/>

Just copy paste the following snippet and update the values and urls to reflect your data:

```
<Map
  autoZoomConfiguration={{
    layerName: 'Points'
  }}
  center={{
    latitude: 45,
    longitude: 0
  }}
  layers={[
    {
      data: {
        url: 'https://opendata.arcgis.com/datasets/9c58741995174fbcb017cf46c8a42f4b_25.geojson'
      },
      name: 'Points',
      tooltip: true
    },
    {
      colorScale: {
        ending: '#00ff00',
        starting: '#ff0000'
      },
      data: {
        url: 'https://d2ad6b4ur7yvpq.cloudfront.net/naturalearth-3.3.0/ne_10m_geography_marine_polys.geojson'
      },
      name: 'Polygons',
      tooltip: true
    }
  ]}
  title="Polygons and points"
  zoom={2}
/>
```

> Make sure to upload your geoJSON file to the Github repository and update the params in the code. 

