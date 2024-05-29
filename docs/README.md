# Docs 

Welcome to Datahub Cloud documentation! 

Datahub Cloud is your stupidly simple and fast tool for turning datasets and data-driven content on GitHub into a published, shareable site.

> Note: The current version of Datahub Cloud runs only off Github.

# Table of contents


# Quick Start

There are two ways you can start publishing quickly with Datahub Cloud:

1. Starting off from our [template](https://github.com/datahubio/datahub-cloud-template) 
2. Or if you want to live dangerously, you can start from scratch

> [!info] We recommend starting with the template first to better understand how it works and what's possible.

-------

# Tutorial 1: Starting off from our template 

1. Go to https://github.com/datahubio/datahub-cloud-template
2. Click "Use this template" at the top right and create the repository (can be public or private - works with both)
3. Go to the app and create a new site by selecting the repository you just created (leave the "Root Dir" field empty)
5. That's it! It is now published. Hit the green "Visit" button at the top right to see what it looks like.
6. Scroll down to #Adding visuals and data-rich components

-------

# Tutorial 2: Create a dataset from scratch and publish it with Datahub Cloud

In this tutorial, we're going to learn how to publish a dataset (multiple data files or a single data file) with DataHub Cloud.

As an example we're going to use an example dataset with an analysis of the top 1000 global universities: https://www.kaggle.com/datasets/zahrayazdani81/univercitiesranking?resource=download

## What You'll Need

- GitHub account and basic knowledge of GitHub UI (especially editing and adding files)
- A [DataHub Cloud](https://datahub.io/) account.

### Step 1: Create a GitHub repository with the data files and `README.md` file

Any DataHub Cloud site is built off of a GitHub repository. This is where you'd put all your dataset file(s) and any related markdown content that you want to publish. For the sake of simplicity, in this tutorial, we're only going to use a single `README.md` file. It's going to serve as a landing page for our site.

> [!tip]
> Any `README.md` or `index.md` file, either in a root of the repository or in a subfolder, will be treated as a "landing" page (of the whole site or a given folder) by the DataHub Cloud.

Go to your GitHub account and create a new repository. Note, you can check "Add a README file" checkbox. This will make GitHub automatically add an empty `README.md` file to our repository.

![[../assets/Pasted image 20240514091335.png]]

> [!hint]
> If you're new to GitHub, here are simple instructions on creating a repository: https://docs.github.com/en/repositories/creating-and-managing-repositories/quickstart-for-repositories

Now, let's also add a short introduction about our dataset to the `README.md` file. We'll use the one from the original Kaggle dataset.

![[../assets/Pasted image 20240515003021.png]]

Now we need to add our dataset files to our repository. The universities dataset we're using only has a single `csv` file. Let's download it and upload it to our repository. We're going to name it `data.csv` but you can name it whatever you want.

> [!hint] 
> If you have multiple data files, to keep things tidy, we recommend putting them in a subfolder, e.g. in `/data`. 

Here is how your repository should look like at this stage:

![[../assets/Pasted image 20240517225336.png]]

> [!hint]
> If you're new to GitHub, here are simple instructions on uploading files to a repository: https://docs.github.com/en/repositories/working-with-files/managing-files/adding-a-file-to-a-repository

### Step 2: Create a DataHub Cloud site

We're not done yet, but let's first publish our repository with DataHub Cloud first to see how it works and what our site looks like.

Go to your DataHub Cloud account and click on "Create New Site" button at the top of the screen. Then, select your newly created GitHub repository and submit the form. You should now be redirected to the settings page of your newly created DataHub Cloud site. Click on the "Visit" button to see how your site looks!

![[../assets/Pasted image 20240515003051.png]]

As you can see, there is no mention of your data file. The current landing page only shows our `README.md` page content. Obviously, this requires some more work. We need to describe our dataset for DataHub Cloud, so that it can display information about it to our site's visitors.

### Step 3: Describe your dataset with Frictionless data standard

In DataHub Cloud, we leverage Frictionless [data standard](https://specs.frictionlessdata.io/) for describing datasets. 

What is it and how does it fit in DataHub Cloud? In short, it's a standard format for describing and sharing datasets with others. DataHub Cloud understands it, and, by default, will render any `README.md` (or `index.md`) file that has a [Frictionless Data Package spec](https://specs.frictionlessdata.io/data-package/) in a `datapackage` frontmatter field using a special `dataset` layout. This layout combines markdown content from the `README.md` file with metadata from the `datapackage` frontmatter field and displays them in an elegant format.

> [!tip]
> You can also put your Data Package spec in a file named `datapackage.{json,yaml,yml}` next to your `README.md` (or `index.md`). This is especially useful if your dataset includes lots of files and your Data Package spec starts being really long.

Note, that currently only a subset of Frictionless Data Package fields is displayed by DataHub Cloud's `dataset` layout. You can find the template Data Package with all the currently supported fields in [this template](https://github.com/datahubio/datahub-cloud-template/blob/main/README.md).

In this tutorial we're only going to focus on the most important fields:
- `title`
- `description`
- `resources` (**required**): describes all the data files included in the dataset. It is a list of objects with the following fields:
	- `name`: unique identifier of the resource
	- `path`: path to the resource file (relative or absolute path)
	- (and some more, but your can explore them on your own)

Now, based on the above information, let's create a `datapackage` yaml spec for our universities dataset and put it in the frontmatter of our `README.md` file, like so:

```md
---
datapackage:
  title: Top 1000 universities in the world
  resources:
  - name: universities-ranking
    path: data.csv
---

...Rest of the README file content...
```

Now, commit your changes, go to your DataHub Cloud dashboard, and **"Sync" your site**.

> [!note]
> Note, instead of nesting the datapackage specification in a `datapackage` field, you can just put the whole spec in a separate `datapackage.yaml` (or json) file right next to the README file. Important: In this case you wouldn't nest it in a top level `datapackage` key!

This is what the resulting site looks like:

![[../assets/Pasted image 20240517224144.png]]
![[../assets/Pasted image 20240515010236.png]]
![[../assets/Pasted image 20240515010252.png]]

Congratulations! You've just learned how to publish a dataset with DataHub Cloud. As you can see, some of the metadata fields in the layout are currently empty. The more information you provide is obviously the better, so we encourage you to explore the full set of currently supported fields in [our template](https://github.com/datahubio/datahub-cloud-template/tree/main).

---------

# Adding visuals and data-rich components

Now that you have published your dataset, you can add more features to make it data-richer.

> [!info] Github is playing the role of your Editor.
> Any changes you want to make to your published site, you need to make in your GitHub repository first.
> Once you hit "sync" on your Site dashboard, the changes get reflected on your published site.

You can check the full list and API of the available features here [https://storybook.portaljs.org](https://storybook.portaljs.org)

## Inserting a component 

1. Select the desired component you want to add from the sidebar list:

![[../assets/Screenshot1.png]]

2. Click on "Docs"
3. Hit "Show code" at the bottom right of the showcased feature

![[../assets/Screenshot2.png]]

6. Copy-paste the code into your markdown file in your GitHub repository
7. Commit the changes made
8. Navigate back to the App and hit "Sync"
9. Visit your site or refresh the page in order to see the reflected changes

> [!info] To import a feature from URL, simply upload your data file to your Github repository and replace the URL in the copied code. Relative paths are supported.
> For concrete examples, please continue reading.

# What features are supported?

You can use several data preview and data visualization components to make your dataset more insightful.

## Overview 

- Catalog
- Tabluar
  - Excel
  - FlatUiTable
- Embedding
  - Iframe
  - PdfViewer 
- Line Charts and Bar Charts
  - Plotly Charts
  - VegaLite Charts
- Geospatial
  - Map

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

If you're working with Microsoft Power BI reports of similar, you can embed it within your page as follows:

<Iframe
  data={{
    url: 'https://app.powerbi.com/view?r=eyJrIjoiYzBmN2Q2MzYtYzE3MS00ODkxLWE5OWMtZTQ2MjBlMDljMDk4IiwidCI6Ijk1M2IwZjgzLTFjZTYtNDVjMy04MmM5LTFkODQ3ZTM3MjMzOSIsImMiOjh9'
  }}
  style={{
    height: '100%',
    width: '100%'
  }}
/>

Simply copy and paste the following code snippet in the markdown file in your Github repository:

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

The only thing you need to do after that is to replace the url with the correct one.

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

Simply copy and paste the following code snippet and update the values to reflect your data points:

```
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
```

> [!info] Line Chart

Same goes for this Line Chart:

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

Copy and paste the following code snippet and update the values to reflect your data points:

```
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

## Summary

In summary, depending on the type of feature you selected from the list https://storybook.portaljs.org and the code copied across, you may need to:
1) update the params _(refer to the params in the docs and their description)_
2) update the CSV link with the link of your data file. You can also use a relative path. 
3) or update the URL to one of your own file
4) And then insert in your markdown file in your Github repository
5) Publish it with Datahub Cloud and share it with the world!

-------

## Datahub Cloud Sidebar Navigation (Alpha version)

You can enable the sidebar by adding config.json file in the root of your site's repository (or it's subfolder if you're publishing only this subfolder with DH Cloud) with the following content:

```
{
  "showSidebar": true
}
```

![[Screenshot3.png]]

# What syntax is supported?

Datahub Cloud supports CommonMark and GitHub Flavored Markdown, but also many Obsidian-specific syntax elements, like Wiki links or footnotes[^1].

For more syntax elements supported by Datahub Cloud, see https://flowershow.app/docs/syntax#commonmark

-------
