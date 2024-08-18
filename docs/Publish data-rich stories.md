---
title: Publish data-rich stories with DataHub Cloud
---

In this tutorial, we are going to cover the basics of creating and publishing data-rich documents.

### But wait, what is a data-rich story?

A data-rich story is a document in which the writer can easily mix formatted text content with data visualizations. This means that you don't have to code nor embed your charts and tables, those can be added to the document with a very simple syntax, passing inline-data or simply referencing your data files. What you end up with is a plain text, human-readable document which is simple to edit and looks awesome when rendered in DataHub!

### What does this syntax look like?

The structure and text formatting of the documents are created with markdown (take a look at [this guide](https://www.datopian.com/playbook/markdown) to learn more about markdown). But it's not simply markdown, it's markdown on steroids: writers are capable of easily adding tables of content, mathematical formulas, data visualizations and more!

<div class="middle-button-container">
    <a href="https://datahub.io/docs/Markdown%20syntax%20support" class="middle-button">Supported markdown syntax</a>
</div>

And guess what? What you are reading right now is a data-rich document powered by DataHub, that's why we can do this:

<LineChart
  data={{
    values: [
      {
        value: -0.41765878,
        year: '1850'
      },
      {
        value: -0.2333498,
        year: '1851'
      },
      {
        value: -0.22939907,
        year: '1852'
      },
      {
        value: -0.27035445,
        year: '1853'
      },
      {
        value: -0.29163003,
        year: '1854'
      }
    ]
  }}
  xAxis="year"
  yAxis="value"
/>

Awesome, right? Even more awesome is that this chart is created by simply having the following snippet in this document:

```
<LineChart
  data={{
    values: [
      {
        value: -0.41765878,
        year: '1850'
      },
      {
        value: -0.2333498,
        year: '1851'
      },
      {
        value: -0.22939907,
        year: '1852'
      },
      {
        value: -0.27035445,
        year: '1853'
      },
      {
        value: -0.29163003,
        year: '1854'
      }
    ]
  }}
  xAxis="year"
  yAxis="value"
/>
```

You can check out the full source of the data rich document you are reading [here](https://github.com/datahubio/tutorial).

More on how to create charts and tables later, but now, this must be coming from somewhere, right?

### What is a DataHub project?

A DataHub project is simply a GitHub repo with a README and, potentially, data files. That's right: you can take advantage of everything that GitHub offers in terms of revisioning, changes history and so on and transform your repo into a data rich document.

Imagine how cool it would be to store your reports, datasets and analysis in this format. Now, let's learn how to actually do it.


## Steps

### Create a GitHub repo

First, create a repo under your organisation or user in GitHub. DataHub currently does not support private repos, so make sure this new repo is public.

### Push a `README.md` file to the repo

Now, let's start with creating a `README.md` file. In this file, feel free to use anything that markdown has to offer. For this tutorial, we are going to use the following basic structure:

```markdown
# Data-rich story

## Table

## Chart
```

### Add a table

Let's add a table to the `README.md` file. Under the `## Table` header in your file, add the following snippet:

```mdx
<FlatUiTable
  data={{
    values: [
      {
        age: 35,
        firstName: 'Jon',
        id: 1,
        lastName: 'Snow'
      },
      {
        age: 42,
        firstName: 'Cersei',
        id: 2,
        lastName: 'Lannister'
      },
      {
        age: 45,
        firstName: 'Jaime',
        id: 3,
        lastName: 'Lannister'
      },
      {
        age: 16,
        firstName: 'Arya',
        id: 4,
        lastName: 'Stark'
      },
      {
        age: 44,
        firstName: 'Ferrara',
        id: 7,
        lastName: 'Clifford'
      },
      {
        age: 36,
        firstName: 'Rossini',
        id: 8,
        lastName: 'Frances'
      },
      {
        age: 65,
        firstName: 'Harvey',
        id: 9,
        lastName: 'Roxie'
      }
    ]
  }}
 />
```

Here's what it's going to look like:

<FlatUiTable
  data={{
    values: [
      {
        age: 35,
        firstName: 'Jon',
        id: 1,
        lastName: 'Snow'
      },
      {
        age: 42,
        firstName: 'Cersei',
        id: 2,
        lastName: 'Lannister'
      },
      {
        age: 45,
        firstName: 'Jaime',
        id: 3,
        lastName: 'Lannister'
      },
      {
        age: 16,
        firstName: 'Arya',
        id: 4,
        lastName: 'Stark'
      },
      {
        age: 44,
        firstName: 'Ferrara',
        id: 7,
        lastName: 'Clifford'
      },
      {
        age: 36,
        firstName: 'Rossini',
        id: 8,
        lastName: 'Frances'
      },
      {
        age: 65,
        firstName: 'Harvey',
        id: 9,
        lastName: 'Roxie'
      }
    ]
  }}
 />
 
### Add a chart

Now, let's add a graph to the README file. To keep it simple, we are going to use the LineChart component in this tutorial. Add the following snippet to your README file under the `## Chart` header:

```mdx
<LineChart
  data={{
    values: [
      {
        value: -0.41765878,
        year: '1850'
      },
      {
        value: -0.2333498,
        year: '1851'
      },
      {
        value: -0.22939907,
        year: '1852'
      },
      {
        value: -0.27035445,
        year: '1853'
      },
      {
        value: -0.29163003,
        year: '1854'
      }
    ]
  }}
  xAxis="year"
  yAxis="value"
/>
```

This is what it will look like when rendered:

<LineChart
  data={{
    values: [
      {
        value: -0.41765878,
        year: '1850'
      },
      {
        value: -0.2333498,
        year: '1851'
      },
      {
        value: -0.22939907,
        year: '1852'
      },
      {
        value: -0.27035445,
        year: '1853'
      },
      {
        value: -0.29163003,
        year: '1854'
      }
    ]
  }}
  xAxis="year"
  yAxis="value"
/>

### Final document

At this point, your document should look like this:

```markdown
# Data-rich story

## Table

<FlatUiTable
  data={{
    values: [
      {
        age: 35,
        firstName: 'Jon',
        id: 1,
        lastName: 'Snow'
      },
      {
        age: 42,
        firstName: 'Cersei',
        id: 2,
        lastName: 'Lannister'
      },
      {
        age: 45,
        firstName: 'Jaime',
        id: 3,
        lastName: 'Lannister'
      },
      {
        age: 16,
        firstName: 'Arya',
        id: 4,
        lastName: 'Stark'
      },
      {
        age: 44,
        firstName: 'Ferrara',
        id: 7,
        lastName: 'Clifford'
      },
      {
        age: 36,
        firstName: 'Rossini',
        id: 8,
        lastName: 'Frances'
      },
      {
        age: 65,
        firstName: 'Harvey',
        id: 9,
        lastName: 'Roxie'
      }
    ]
  }}
 />

## Chart

<LineChart
  data={{
    values: [
      {
        value: -0.41765878,
        year: '1850'
      },
      {
        value: -0.2333498,
        year: '1851'
      },
      {
        value: -0.22939907,
        year: '1852'
      },
      {
        value: -0.27035445,
        year: '1853'
      },
      {
        value: -0.29163003,
        year: '1854'
      }
    ]
  }}
  xAxis="year"
  yAxis="value"
/>
```

We now have a README file ready to be published with DataHub Cloud!

### Optional steps

You can add as many markdown files to your GitHub repository as you like, and you can freely nest them in subdirectories. You can also enhance your content with other data visualisation components and markdown features.

<div class="middle-button-container">
    <a href="https://datahub.io/docs/Add%20visuals%20and%20data-rich%20components" class="middle-button">Add visuals and data-rich components</a>
</div>

<div class="middle-button-container">
    <a href="https://datahub.io/docs/Markdown%20syntax%20support" class="middle-button">See the full list of supported markdown features</a>
</div>


### Publish with DataHub

1. Sign in to https://cloud.datahub.io/
2. Click on "Create new site".
3. Select your GitHub user/organisation.
4. Select the repository you've just created and the branch you want to build your site off of.
5. Click on "Create Site".
6. Done! Now visit your site by clicking on the URL at the top of the site settings page.

[👀 See an example data-rich document rendered with DataHub](https://datahub.io/@Daniellappv/datarich-demo-newest/posts/story1)

___

Cool, isn't it? Get in contact with us and let us know what you think! [Join our Discord](https://discord.gg/URNSkepK7z)
