# Docs 

Welcome to Datahub Cloud! 

> [!info] You can publish your dataset or your data story quickly and easily with Datahub Cloud. 
> The current version of Datahub Cloud runs only off Github. 

## Quick Start

There are two ways you can start publishing quickly with Datahub Cloud:

1. Starting off from our [template](https://github.com/datahubio/datahub-cloud-template) and customizing it to fit your needs
2. Or if you want to live dangerously, you can start from scratch

> [!info] We recommend starting with the template first to better understand how it works and what's possible.

### Starting off from our template

1. Go to https://github.com/datahubio/datahub-cloud-template
2. Click "Use this template" at the top right and create the repository (can be public or private - works with both)
3. Go to the app and create a new site by selecting the repository you just created (leave the "Root Dir" field empty)
5. That's it! It is now published. Hit "Visit" at the top right to see what it looks like.

#### Customizing the template

Now that you have the template deployed in your repository, you can add more features to it, or tidy it up in case you don't need everything.

TODO

If you want to eg. 



### Starting from scratch 

> [!info] This currently requires some basic technical background.

You can create a new repository in Github. Currently, any Github repository with the following is supported:
- Any markdown file + a `datapackage` frontmatter field ([Frictionless data package spec](https://specs.frictionlessdata.io/data-package/#language))
- Any `index.md/README.md` + same level `datapackage.{json/yaml/yml}` file

> Note: Having data files that are **not** specifically listed in the data package are ignored.

#### Adding new components to your brand new repository

Refer to the full list and API of available data visualization components here [https://storybook.portaljs.org](https://storybook.portaljs.org)

1. Click on the desired component you want to add from the sidebar list.
2. Look at the right side of your screen to see what this component would look like
3. Navigate to the bottom right of the component and click on "Show code"

<img width="1388" alt="Screenshot 2024-04-11 at 14 52 59" src="https://github.com/datahubio/datahub-cloud-template/assets/45828069/67de61a9-3479-4881-8457-cb5742f7842e">

4. Copy-paste the code into your markdown file in your Github repository (if you haven't added one while creating the repo, do it now)
5. TODO


## Supported features 

### Summary
- Catalog
- Excel
- Map
- Data Table
- Line Charts and Bar Charts
  - Plotly Charts
  - VegaLite Charts

You can use a number of data preview and data visualization components in order to make your dataset more insightful. Continue reading to explore other currently supported features.

### Catalog 

