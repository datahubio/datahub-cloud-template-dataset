<div class="hero">
    <h1 class="hero-title">Create a dataset from scratch and publish it with Datahub Cloud<br/></h1>
</div>

# Create a dataset from scratch and publish it with Datahub Cloud

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

![[./assets/Pasted image 20240514091335.png]]

> [!hint]
> If you're new to GitHub, here are simple instructions on creating a repository: https://docs.github.com/en/repositories/creating-and-managing-repositories/quickstart-for-repositories

Now, let's also add a short introduction about our dataset to the `README.md` file. We'll use the one from the original Kaggle dataset.

![[./assets/Pasted image 20240515003021.png]]

Now we need to add our dataset files to our repository. The universities dataset we're using only has a single `csv` file. Let's download it and upload it to our repository. We're going to name it `data.csv` but you can name it whatever you want.

> [!hint] 
> If you have multiple data files, to keep things tidy, we recommend putting them in a subfolder, e.g. in `/data`. 

Here is how your repository should look like at this stage:

![[./assets/Pasted image 20240517225336.png]]

> [!hint]
> If you're new to GitHub, here are simple instructions on uploading files to a repository: https://docs.github.com/en/repositories/working-with-files/managing-files/adding-a-file-to-a-repository

### Step 2: Create a DataHub Cloud site

We're not done yet, but let's first publish our repository with DataHub Cloud first to see how it works and what our site looks like.

Go to your DataHub Cloud account and click on "Create New Site" button at the top of the screen. Then, select your newly created GitHub repository and submit the form. You should now be redirected to the settings page of your newly created DataHub Cloud site. Click on the "Visit" button to see how your site looks!

![[./assets/Pasted image 20240515003051.png]]

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

![[./assets/Pasted image 20240517224144.png]]
![[./assets/Pasted image 20240515010236.png]]
![[./assets/Pasted image 20240515010252.png]]

Congratulations! You've just learned how to publish a dataset with DataHub Cloud. As you can see, some of the metadata fields in the layout are currently empty. The more information you provide is obviously the better, so we encourage you to explore the full set of currently supported fields in [our template](https://github.com/datahubio/datahub-cloud-template/tree/main).
