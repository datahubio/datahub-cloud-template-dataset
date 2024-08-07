<div class="hero">
    <h1 class="hero-title">Configuring Nav bar and SEO fields<br/></h1>
</div>

# How to Configure Basic SEO Fields and Nav Bar in Your DataHub Cloud Sites

You can now personalize your DataHub Cloud site by:
- setting your own site-wide SEO title and description
- changing the navbar's logo and title, and adding your own navigation links
- switching from top navbar to sidebar with all your site's pages.

## Meet `config.json` file

Any site-wide configurations of your DataHub Cloud sites (other than the ones you can find in the dashboard's site settings page) can be applied via root-level `config.json` file. We'll explore each of the available config options below. If you want to follow, first create this file in your site's repo.

> [!tip]
> You can find a full `config.json` file example in our [template repository](https://github.com/datahubio/datahub-cloud-template/tree/main).

## Improve SEO by Setting Your Site's Title and Description

You can change your site's default SEO title and description by setting the following config fields:
- `title`: default SEO title for your site (will be used as a fallback value for pages without a title set); **note**: this title will also be used in your site's navbar
- `description`: default SEO title for your site (will be used as a fallback value for pages without a title set)

For example, putting the following in the `config.json` file:

```json
{
  "title": "Joe's Digital Garden",
  "description": "Welcome to my personal travel blog, where I share my experiences and travel tips."
}
```

...will result in the following SEO values (note, that `title` tag's value is set to the actual page title, which takes precedence over the site-wide title):

![[./assets/Pasted image 20240520152158.png]]

... and the following navbar title change:
![[./assets/Pasted image 20240520152011.png]]

## Changing Navbar's Logo, Title and Links 

As you just saw, setting the `title` field in `config.json` already changes/sets the navbar title. But the logo is still the default one. To change it, you can add a local path or an external URL to your logo in the `logo` field, like this:

```json
{
  "logo": "logo.jpeg"
}
```

Now we have the navbar title and logo changed, but there are still default DataHub links in there. To change those to your custom links you can include `navLinks` field in your `config.json` file, with each link having the following fields:
- `name`: label of the link
- `href`: the actual link

For example:

```json
{
 "navLinks": [
  {
   "href": "/blog",
   "name": "Blog"
  }, 
  {
   "href": "/about",
   "name": "About"
  }, 
  {
  "href": "https://twitter.com/datopian",
  "name": "Follow me on twitter!"
  }
 ]
}
```

![[./assets/Pasted image 20240520155132.png]]

## Conclusion

Congratulations! You've just learned how to configure basic SEO fields and the navigation bar of your DataHub Cloud site using `config.json` file.

---

If you encounter any issues or have questions, the DataHub Cloud community and support team are here to help.

Happy hacking!
