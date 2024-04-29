# Docs 

Welcome to Datahub Cloud documentation! 

Datahub Cloud is your stupidly simple and fast tool for turning datasets and data-driven content on GitHub into a published, shareable site.

> Note: The current version of Datahub Cloud runs only off Github.

--------

# Quick Start

There are two ways you can start publishing quickly with Datahub Cloud:

1. Starting off from our [template](https://github.com/datahubio/datahub-cloud-template) 
2. Or if you want to live dangerously, you can start from scratch

> [!info] We recommend starting with the template first to better understand how it works and what's possible.

## Starting off from our template

1. Go to https://github.com/datahubio/datahub-cloud-template
2. Click "Use this template" at the top right and create the repository (can be public or private - works with both)
3. Go to the app and create a new site by selecting the repository you just created (leave the "Root Dir" field empty)
5. That's it! It is now published. Hit the green "Visit" button at the top right to see what it looks like.

## Starting from scratch 

You can create a new repository in Github. Currently, any Github repository with the following files is supported:
- Any markdown file (.md) + a `datapackage` frontmatter field ([Frictionless data package spec](https://specs.frictionlessdata.io/data-package/#language))
- Any `index.md/README.md` + same level `datapackage.{json/yaml/yml}` file

> Note: Having data files that are **not** specifically listed in the data package are ignored.

-------

## I have my site up and running. How do I customize it?

Now that you have created your first site, you can add more features to make it data-richer.

> [!info] Github is playing the role of your Editor.
> Any changes you want to make to your published site, you need to make in your GitHub repository first.
> Once you hit "sync" on your Site dashboard, the changes get reflected on your published site.

To start with, please check the full list and API of the available features here [https://storybook.portaljs.org](https://storybook.portaljs.org)

**Then follow the steps below:**

1. Upload all relevant data files and/or images to your Github repository.
2. Select the desired feature you want to add from the sidebar list.
3. Once you click on the selected feature, you will find 1) docs related to the feature as well as 2) the different ways in which you can import this feature
4. In any way, navigate to the docs
5. Hit "Show code" at the bottom right of the showcased feature

<img width="1388" alt="Screenshot 2024-04-11 at 14 52 59" src="https://github.com/datahubio/datahub-cloud-template/assets/45828069/67de61a9-3479-4881-8457-cb5742f7842e"/>

6. Copy-paste the code into your markdown file in your GitHub repository (if you haven't added one while creating the repo, do it now)*
7. Commit the changes made
8. Navigate back to the App and hit "Sync"
9. Visit your site or refresh the page in order to see the reflected changes

> [!info] To import a feature from URL, simply upload your data file to your Github repository and replace the URL in the copied code. Relative paths are supported.
> If you need more detailed instructions on how to customize the copied code in order to make it fit with your data, please continue reading.

-------

# What syntax is supported?

Datahub Cloud supports CommonMark and GitHub Flavored Markdown, but also many Obsidian-specific syntax elements, like Wiki links or footnotes[^1].

For more syntax elements supported by Datahub Cloud, see https://flowershow.app/docs/syntax#commonmark

-------

# What features are supported?

Depending on the type of feature you selected from the list https://storybook.portaljs.org and the code copied across, you may need to:
1) update the params _(refer to the params in the docs and their description)_
2) update the CSV link with the link of your data file. You can also use a relative path. 
3) or update the URL to one of your own file

## Summary
- Catalog
- Excel
- Map
- Data Table
- Line Charts and Bar Charts
  - Plotly Charts
  - VegaLite Charts

You can use a number of data preview and data visualization components in order to make your dataset more insightful. Continue reading to explore other currently supported features.

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

This makes it easy to navigate and quickly find or filter down the data you're looking for. You can add as many facets as you'd like. 

> Simply copy-paste the code and update the values. 

## Excel 

`==Excel==`

If you're working a lot with Excel files, you can embed a preview of your file such as this one:

<Excel data={{
  url: "https://storage.portaljs.org/IC-Gantt-Chart-Project-Template-8857.xlsx"
}} />

This component allows you to present all tabs in your Excel file. You can sort the rows by clicking on the Column name and you can also filter each column by clicking on the triple bar symbol next to the Column name.

> Simply upload your Excel file to your Github repository and replace the URL with the URL of the uploaded file (absolute and relative paths are supported). 


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

> Make sure to upload your geoJSON file to the Github repository and update the params in the code. 

## Data Table

Let's continue by adding a table of your data like the one below:

<FlatUiTable data={{
  url: "https://storage.openspending.org/alberta-budget/__os_imported__alberta_total.csv"
}} />

> To get this data replaced with your data, upload your csv file to your repository and update the URL 

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
3) Update the params (data, title, xAxis, yAxis) to fit your data

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

> There are also other types of charts and graphs you can use to enhance your dataset. You can create charts with Plotly or VegaLite.

### Plotly charts

> [!info] Bar Chart

<PlotlyBarChart
  data={{
    values: [
      {
        temperature: -0.41765878,
        year: '1850'
      },
      {
        temperature: -0.2333498,
        year: '1851'
      },
      {
        temperature: -0.22939907,
        year: '1852'
      },
      {
        temperature: -0.27035445,
        year: '1853'
      },
      {
        temperature: -0.29163003,
        year: '1854'
      }
    ]
  }}
  xAxis="year"
  yAxis="temperature"
/>

> [!info] Line Chart

<PlotlyLineChart
  data={{
  values: [
      {
        temperature: -0.41765878,
        year: '1850'
      },
      {
        temperature: -0.2333498,
        year: '1851'
      },
      {
        temperature: -0.22939907,
        year: '1852'
      },
      {
        temperature: -0.27035445,
        year: '1853'
      },
      {
        temperature: -0.29163003,
        year: '1854'
      }
  ]}}
  xAxis="year"
  yAxis="temperature"
/>

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


For a full list and API of available data visualization components visit [https://storybook.portaljs.org](https://storybook.portaljs.org)
