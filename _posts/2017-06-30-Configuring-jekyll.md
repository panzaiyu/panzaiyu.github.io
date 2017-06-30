---

layout: post

title: jekyll配置

author: 潘再余

date: 2017-06-29

description: 介绍如何在Github Pages中配置jekyll

---

> 本文参考：
> <a href="https://help.github.com/articles/setting-up-your-github-pages-site-locally-with-jekyll/#keeping-your-site-up-to-date-with-the-github-pages-gem">如何使用jekyll在本地建立Github Pages</a>

> <a href="https://help.github.com/articles/configuring-jekyll/">jekyll配置</a>

对于使用Github Pages生成的网页，Github会向*_config.yml*中添加额外的默认配置信息。



## 不可更改的默认配置

     lsi: false
     safe: true
     source: [your repo's top level directory]
     incremental: false
     highlighter: rouge
     gist:
       noscript: false
     kramdown:
       math_engine: mathjax

## 可更改的默认配置

    github: [metadata]
    kramdown:
      input: GFM
      hard_wrap: false
    gems:
      - jekyll-coffeescript
      - jekyll-paginate

## site.github

github会为Github Pages项目的jekyll模板附版本库元数据。版本库元数据存放在`site.github`命名空间，包含一般的仓库信息，例如项目名称和描述。
`site.github`具体结构如下：

    {
        "versions": {
            "jekyll": <version>,
            "kramdown": <version>,
            "liquid": <version>,
            "maruku": <version>,
            "rdiscount": <version>,
            "redcarpet": <version>,
            "RedCloth": <version>,
            "jemoji": <version>,
            "jekyll-mentions": <version>,
            "jekyll-redirect-from": <version>,
            "jekyll-sitemap": <version>,
            "github-pages": <version>,
            "ruby": <version>"
        },
        "hostname": "github.com",
        "pages_hostname": "github.io",
        "api_url": "https://api.github.com",
        "help_url": "https://help.github.com",
        "environment": "dotcom",
        "pages_env": "dotcom",
        "public_repositories": [ Repository Objects ],
        "organization_members": [ User Objects ],
        "build_revision": "cbd866ebf142088896cbe71422b949de7f864bce",
        "project_title": "metadata-example",
        "project_tagline": "A GitHub Pages site to showcase repository metadata",
        "owner_name": "github",
        "owner_url": "https://github.com/github",
        "owner_gravatar_url": "https://github.com/github.png",
        "repository_url": "https://github.com/github/metadata-example",
        "repository_nwo": "github/metadata-example",
        "repository_name": "metadata-example",
        "zip_url": "https://github.com/github/metadata-example/zipball/gh-pages",
        "tar_url": "https://github.com/github/metadata-example/tarball/gh-pages",
        "clone_url": "https://github.com/github/metadata-example.git",
        "releases_url": "https://github.com/github/metadata-example/releases",
        "issues_url": "https://github.com/github/metadata-example/issues",
        "wiki_url": "https://github.com/github/metadata-example/wiki",
        "language": null,
        "is_user_page": false,
        "is_project_page": true,
        "show_downloads": true,
        "url": "http://username.github.io/metadata-example", // (or the CNAME)
        "baseurl": "/metadata-example",
        "contributors": [ User Objects ],
        "releases": [ Release Objects ]
    }
