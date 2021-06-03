## Getting Started

Here are some details to help you getting started with this theme.

<!--more-->

We'll assume here that you have a good understanding of Hugo and its structure. If you have any doubt, check the [Hugo documentation](https://gohugo.io/documentation/ "Hugo documentation"); it is pretty good and the community quite active! Thank you so much by the way! :muscle:

The first thing to do when starting your own website is to **copy the content of exampleSite** in your own root folder. This way, you can have a sample of `config.toml` file and a first structure.

**Don't forget to change the `baseURL` param to avoid deployment failures**

Browse the articles in the `content/post` folder to get any help during setup or using the theme. Please, [contact me](https://baptistej.com "contact me") if you have any problem using the them.

Then **configure the `config.toml` file** to match your need.

You should then write you home (`/content/_index.md`), create your first project (see the [portfolio definition](/content/post/portfolio-definition.md "portfolio definition") and your first blogpost.

Lastly, define the menu in the sidebar: you can get some help in the `/content/post/manage-your-menu.md` file.


## Config File

Here is the basic config file used for personal-web.

You can use it as a base for your website.

<!--more-->

```TOML
baseURL = "https://example.com/"
languageCode = "en-us"
title = "Edna West"
theme = "personal-web"
copyright="© Edna West"
googleAnalytics = ""
enableEmoji=true
enableRobotsTXT=true
pygmentsUseClasses=true
pygmentsCodeFences=true

[params.intro]
  main = "Hi, I'm Edna :wave:"
  sub = "I'm a Web Developer and Entrepreneur"

[params.main]
  latestPublishHeader = "My Latest Project"

[taxonomies]
  design = "designs"
  tech = "techs"

[blackfriday]
  hrefTargetBlank = true

[params]
  breadcrumb = true
  accentColor = "#FD3519"
  mainSections = ['portfolio']

[params.notFound]
  gopher = "/images/gopher.png"
  h1 = 'Bummer!'
  p = "It seems that this page doesn't exist."

[params.sections]
  post = "article"
  portfolio = "project"

[params.sidebar]
  backgroundImage = ''
  gradientOverlay = ''
  logo = ""

[params.assets]
  favicon = ""
  customCSS = ""

[params.social]
  github = "https://github.com/"
  twitter = "https://twitter.com/"
  linkedin = "https://www.linkedin.com/in/"
  medium = "https://medium.com/"
  codepen = "https://codepen.io/"
  facebook = "https://www.facebook.com/"
  youtube = "https://www.youtube.com/"
  instagram = "https://www.instagram.com/"
  gitlab = "https://gitlab.com/"
  keybase = "https://keybase.io/"

[params.contact]
  email = ""
  text= ""


[menu]

[[menu.main]]
  identifier = "about"
  name = "About"
  title = "About section"
  url = "/about/"
  weight = -120

[[menu.main]]
  identifier = "portfolio"
  name = "Portfolio"
  title = "Portfolio"
  url = "/portfolio/"
  weight = -110

[[menu.main]]
  identifier = "blog"
  name = "Post"
  title = "Blog section"
  url = "/post/"
  weight = -100

[sitemap]
  changefreq = "monthly"
  filename = "sitemap.xml"
  priority = 0.5

[privacy]
  [privacy.googleAnalytics]
    anonymizeIP = true
    disable = true
    respectDoNotTrack = true
    useSessionStorage = false
  [privacy.twitter]
    disable = false
    enableDNT = true
    simple = false

```

### Menu

Menu in the sidebar can be defined within the `config.toml` or directly in the files.
I prefer the config file approach, as this menu is pretty simple.

<!--more-->

The following setup will define 3 URLs in your sidebar menu, in order of weight.

```TOML
[menu]

[[menu.main]]
  identifier = "about"
  name = "About"
  title = "About section"
  url = "/about/"
  weight = -120

[[menu.main]]
  identifier = "portfolio"
  name = "Portfolio"
  title = "Portfolio"
  url = "/portfolio/"
  weight = -110

[[menu.main]]
  identifier = "blog"
  name = "Post"
  title = "Blog section"
  url = "/post/"
  weight = -100

```

### Sidebar

The sidebar header is defined within the `params.intro` section. The `main` being the top header and `sub` the subheader

```TOML
[params.intro]
  main = "Hi, I'm Edna :wave:"
  sub = "I'm a Web Developer and Entrepreneur"
```

You can also customize the params with the  `params.sidebar` parameters. The `config.toml` file contains the default values as examples.
```TOML
[params.sidebar]
  backgroundImage = ''
  gradientOverlay = ''
  logo = ''
```

### 404

The 404 page is defined within the `params.notFound` section.
The `gopher`, `h1` and `p` params define the image and texts displayed on the page. 

In the `[params]` section, the `mainSections` params possible values are 'portfolio' or 'post': it defines the section highlighted on the page.

NB: to see the 404 page from your development env, check `/404.html`.

```TOML
[params.notFound]
  gopher = "/images/gopher.png"
  h1 = 'Bummer!'
  p = "It seems that this page doesn't exist."

[params]
  mainSections = ['portfolio']
```

You can also define how the post and portfolio sections will be named on the 404 page, thanks to the `params.sections` params.

```TOML
[params.sections]
  post = "article"
  portfolio = "project"
```

### Customization

You can define a custom CSS file in the `customCSS` param and a favicon.
```TOML
[params.assets]
  favicon = ""
  customCSS = ""
```

### Social

You can define your social media usernames in the `params.social` and the `params.contact` paramaters. 

In this last section, the email expects your email address and the text is what will be displayed on the sidebar, right below the last item of the menu. If blank, nothing is displayed.

```TOML
[params.social]
  github = "https://github.com/"
  twitter = "https://twitter.com/"
  linkedin = "https://www.linkedin.com/in/"
  medium = "https://medium.com/"
  codepen = "https://codepen.io/"
  facebook = "https://www.facebook.com/"
  youtube = "https://www.youtube.com/"
  instagram = "https://www.instagram.com/"
  gitlab = "https://gitlab.com/"
  keybase = "https://keybase.io/"

[params.contact]
  email = ""
  text= ""
```

### Latest Publication
You can define the name of the latest publication header on the home page with the param `latestPublishHeader`.

```TOML
[params.main]
  latestPublishHeader = "My Latest Project"
```

## Archetypes

The archetypes are defined in the `archetypes` folder, for both post and portfolio.

<!--more-->

The archetypes are defined in YAML, so Front matter is formatted in YAML too. You can easily change them to TOML in your own `archetypes` is you wish to.

For example:

```YAML
---
title: title
description: desc
date: "2019-05-02T19:47:09+02:00"
---
```

to

```TOML
+++
title = "title"
description: "desc"
date: "2019-05-02T19:47:09+02:00"
+++
```

## Open Graph Image
Within any page, you can add in the FrontMatter a images array that will be used to define a specific Open Graph image.

For example, see `content/_index.md` page:
```YAML
images: ["/images/sample.jpg"]
```

## Portfolio Definition
Here are some details about the portfolio settings.

{{< figure src="/post/images/portfolio-example.png" caption="Example of Portfolio page" >}}

<!--more-->

```YAML
---
title: 
description: 
date: "2019-05-02T19:47:09+02:00"
jobDate: 201
work: []
techs: []
designs: []
thumbnail: 
projectUrl: 
testimonial:
  name: 
  role: 
  image: 
  text: 
---
```

Here are some explanations about the portfolio FrontMatter:
- `jobDate` is the year displayed on the list and show of your project
- `work` is displayed on the list of projects. It is an array of type of job that you did on the project.
- `techs` and `designs` are displayed on the show page of your project. It is an array of tools you used on the project
- `thumbnail` is a image file displayed both for the list and show of the project
- `projectUrl` is the URL to the project.
- The `testimonial` params define the person giving your a testimonial as well as the text of the testimonial.

NB: if `techs`, `designs` or `projectUrl` is not defined, it will not be displayed at all.



## Shortcodes

Introduction of the shortcodes defined in the personal-web theme.

<!--more-->

### Add a figure
```go-html-template
{{</* figure src="/post/images/sample_image.jpg" 
caption="Photo by Tim Mossholder on Unsplash" */>}}
```

results in

{{< figure src="/post/images/sample_image.jpg" caption="Photo by Tim Mossholder on Unsplash" >}}

**Note:** files are kept in a `images` folder, directly in the post/portfolio folder.


### Add a single Tweet
```go-html-template
{{</* tweet-single 1120412132036706305 */>}}
```

results in
{{< tweet-single 1120412132036706305 >}}

This shortcode is useful in case of multiple tweets in a thread. If you want to show a single tweet, use this shortcode, with the ID of the Tweet. The ID is the end of the tweet link.

For example: \
https://<span></span>twitter.com/BarackObama/status/**1120412132036706305**
