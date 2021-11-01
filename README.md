<img src="https://opensearch.org/assets/img/opensearch-logo-themed.svg" height="64px">

# OpenSearch 文档

本仓库（repository）中包含有 OpenSearch 的文档, 在 OpenSearch 中提供了高级安全特性，警告，SQL 支持，自动索引管理，深度性能分析等功能。

### 中文本地化

本仓库的内容是从官方 GitHub 代码库中 Fork 下来后进行编译和修改的。完整编译的简体中文文档，请访问[opensearch.ossez.com](https://opensearch.ossez.com)。
有关如何对内容进行编译和本地查看的方法，请查看本页面中有关项目本地部署的内容。

如果你对文档的内容有任何建议和需要修改的地方，请向本仓库中提交 PR，本仓库使用默认的分支为 [docs_cn](https://github.com/cwiki-us-docs/opensearch-docs-cn)，以区别官方使用的分支。

本文档使用的是 GitHub Pages 功能进行部署的，因此你也可以非常容易的将本文档中内容 Fork 到你的仓库中部署到你的域名下面，如果你在部署上有什么问题的话，请访问 [OSSEZ.COM](https://www.ossez.com/tag/opensearch) 中的内容，并参与讨论。

### 官方文档地址

你可以访问官方的文档地址 [opensearch.org/docs](https://opensearch.org/docs) 来显示完整被渲染后的文档。

社区成员的贡献对保持本文档的完整性，有效性，完整组织和保持最新起到了非常重要的作用。


## 你可以做什么样的帮助

- 你在对 OpenSearch 的插件进行开发吗？请查看有关插件的文档。在有关插件的文档中是否所有的内容都是准确的还有什么需要在后续开发中改进的呢？

  通常来说，项目团队将会对已经存在的文档保持必要的最小更新，这样能够让项目团队关注更多关键内容和重要的项目。

- 你是否对 OpenSearch 的特定领域有专业的知识吗？集群大小？查询语言（DSL）？Do you have expertise in a particular area of OpenSearch? Cluster sizing? 无痛脚本（Painless scripting）？聚合（Aggregations）？JVM 设置？请查看 [OpenSearch 当前内容](https://opensearch.ossez.com/) 来了解你是否可以为项目加入一些有价值的内容。 [OpenSearch 文档项目组](#points-of-contact) 非常高兴能够帮助你对内容进行润色和重新组织你的草稿。

- 你是 OpenSearch 面板（Dashboards）的专家吗？你是如何设置你的可视化环境的呢？为什么这个可视化环境对你的项目或者组织来说是非常重要的呢？针对 OpenSearch Dashboards 我们现在只有 [非常有限](https://opensearch.ossez.com/opensearch-dashboards/) 的内容，仅仅显示如何来进行安装。

- 你是一个页面开发工程师（web developer）吗？你是否希望为文档添加一个可选的黑暗模式（dark mode）？针对代码复制提供一个拷贝到剪切板（copy to clipboard）的按钮？或者有关能够增加曝光量的设计或者改进？请参考 [主要修改（major changes）](#major-changes) 页面来获得有关完整本地化构建的相关信息。

- 我们的 [问题跟踪（issue tracker）](https://github.com/opensearch-project/documentation-website/issues) 中包含有文档的缺陷（bug）和其他内容的问题，在这里面将会被使用彩色标签标记为 "good first issue" 和 "help wanted"。


## 联系方式

如果你对文档进行贡献有任何问题，请通过链接联系下面的人来获得帮助：

- [aetter](https://github.com/aetter)
- [ashwinkumar12345](https://github.com/ashwinkumar12345)
- [keithhc2](https://github.com/keithhc2)
- [snyder114](https://github.com/snyder114)


## 网站是如何工作的

This repository contains many [Markdown](https://guides.github.com/features/mastering-markdown/) files organized into Jekyll "collections" (e.g. `_search-plugins`, `_opensearch`, etc.). Each Markdown file correlates with one page on the website.

Using plain text on GitHub has many advantages:

- Everything is free, open source, and works on every operating system. Use your favorite text editor, Ruby, Jekyll, and Git.
- Markdown is easy to learn and looks good in side-by-side diffs.
- The workflow is no different than contributing code. Make your changes, build locally to check your work, and submit a pull request. Reviewers check the PR before merging.
- Alternatives like wikis and WordPress are full web applications that require databases and ongoing maintenance. They also have inferior versioning and content review processes compared to Git. Static websites, such as the ones Jekyll produces, are faster, more secure, and more stable.

In addition to the content for a given page, each Markdown file contains some Jekyll [front matter](https://jekyllrb.com/docs/front-matter/). Front matter looks like this:

```
---
layout: default
title: Alerting security
nav_order: 10
parent: Alerting
has_children: false
---
```

If you're making [trivial changes](#trivial-changes), you don't have to worry about front matter.

If you want to reorganize content or add new pages, keep an eye on `has_children`, `parent`, and `nav_order`, which define the hierarchy and order of pages in the lefthand navigation. For more information, see the documentation for [our upstream Jekyll theme](https://pmarsceill.github.io/just-the-docs/docs/navigation-structure/).


## Contribute content

There are three ways to contribute content, depending on the magnitude of the change.

- [Trivial changes](#trivial-changes)
- [Minor changes](#minor-changes)
- [Major changes](#major-changes)


### Trivial changes

If you just need to fix a typo or add a sentence, this web-based method works well:

1. On any page in the documentation, click the **Edit this page** link in the lower-left.

1. Make your changes.

1. Choose **Create a new branch for this commit and start a pull request** and **Commit changes**.


### Minor changes

If you want to add a few paragraphs across multiple files and are comfortable with Git, try this approach:

1. Fork this repository.

1. Download [GitHub Desktop](https://desktop.github.com), install it, and clone your fork.

1. Navigate to the repository root.

1. Create a new branch.

1. Edit the Markdown files in `/docs`.

1. Commit, push your changes to your fork, and submit a pull request.


### Major changes

If you're making major changes to the documentation and need to see the rendered HTML before submitting a pull request, here's how to build locally:

1. Fork this repository.

1. Download [GitHub Desktop](https://desktop.github.com), install it, and clone your fork.

1. Navigate to the repository root.

1. Install [Ruby](https://www.ruby-lang.org/en/) if you don't already have it. We recommend [RVM](https://rvm.io/), but use whatever method you prefer:

   ```
   curl -sSL https://get.rvm.io | bash -s stable
   rvm install 2.6
   ruby -v
   ```

1. Install [Jekyll](https://jekyllrb.com/) if you don't already have it:

   ```
   gem install bundler jekyll
   ```

1. Install dependencies:

   ```
   bundle install
   ```

1. Build:

   ```
   sh build.sh
   ```

1. If the build script doesn't automatically open your web browser (it should), open [http://localhost:4000/docs/](http://localhost:4000/docs/).

1. Create a new branch.

1. Edit the Markdown files in each collection (e.g. `_security-plugin/`).

   If you're a web developer, you can customize `_layouts/default.html` and `_sass/custom/custom.scss`.

1. When you save a file, marvel as Jekyll automatically rebuilds the site and refreshes your web browser. This process can take anywhere from 10-30 seconds.

1. When you're happy with how everything looks, commit, push your changes to your fork, and submit a pull request.


## Writing tips

1. Try to stay consistent with existing content and consistent within your new content. Don't call the same plugin KNN, k-nn, and k-NN in three different places.

1. Shorter paragraphs are better than longer paragraphs. Use headers, tables, lists, and images to make your content easier for readers to scan.

1. Use **bold** for user interface elements, *italics* for key terms or emphasis, and `monospace` for Bash commands, file names, REST paths, and code.

1. Markdown file names should be all lowercase, use hyphens to separate words, and end in `.md`.

1. Avoid future tense. Use present tense.

   **Bad**: After you click the button, the process will start.

   **Better**: After you click the button, the process starts.

1. "You" refers to the person reading the page. "We" refers to the OpenSearch contributors.

   **Bad**: Now that we've finished the configuration, we have a working cluster.

   **Better**: At this point, you have a working cluster, but we recommend adding dedicated master nodes.

1. Don't use "this" and "that" to refer to something without adding a noun.

   **Bad**: This can cause high latencies.

   **Better**: This additional loading time can cause high latencies.

1. Use active voice.

   **Bad**: After the request is sent, the data is added to the index.

   **Better**: After you send the request, the OpenSearch cluster indexes the data.

1. Introduce acronyms before using them.

   **Bad**: Reducing customer TTV should accelerate our ROIC.

   **Better**: Reducing customer time to value (TTV) should accelerate our return on invested capital (ROIC).

1. Spell out one through nine. Start using numerals at 10. If a number needs a unit (GB, pounds, millimeters, kg, celsius, etc.), use numerals, even if the number if smaller than 10.

   **Bad**: 3 kids looked for thirteen files on a six GB hard drive.

   **Better**: Three kids looked for 13 files on a 6 GB hard drive.


## New releases

1. Branch.
1. Change the `opensearch_version`, `opensearch_major_minor_version`, and `lucene_version` variables in `_config.yml`.
1. Start up a new cluster using the updated Docker Compose file in `docs/install/docker.md`.
1. Update the version table in `version-history.md`.

   Use `curl -XGET https://localhost:9200 -u admin:admin -k` to verify the OpenSearch and Lucene versions.

1. Update the plugin compatibility table in `_opensearch/install/plugin.md`.

   Use `curl -XGET https://localhost:9200/_cat/plugins -u admin:admin -k` to get the correct version strings.

1. Update the plugin compatibility table in `_dashboards/install/plugins.md`.

   Use `docker ps` to find the ID for the OpenSearch Dashboards node. Then use `docker exec -it <opensearch-dashboards-node-id> /bin/bash` to get shell access. Finally, run `./bin/opensearch-dashboards-plugin list` to get the plugins and version strings.

1. Run a build (`build.sh`), and look for any warnings or errors you introduced.
1. Verify that the individual plugin download links in `docs/install/plugins.md` and `docs/opensearch-dashboards/plugins.md` work.
1. Check for any other bad links (`check-links.sh`). Expect a few false positives for the `localhost` links.
1. Submit a PR.


## Classes within Markdown

This documentation uses a modified version of the [just-the-docs](https://github.com/pmarsceill/just-the-docs) Jekyll theme, which has some useful classes for labels and buttons:

```
[Get started](#get-started){: .btn .btn-blue }

## Get started
New
{: .label .label-green }
```

* Labels come in default (blue), green, purple, yellow, and red.
* Buttons come in default, purple, blue, green, and outline.
* Warning, tip, and note blocks are available (`{: .warning }`, etc.).
* If an image has a white background, you can use `{: .img-border }` to add a one pixel border to the image.

These classes can help with readability, but should be used *sparingly*. Each addition of a class damages the portability of the Markdown files and makes moving to a different Jekyll theme (or a different static site generator) more difficult.

Besides, standard Markdown elements suffice for most documentation.


## Labels for APIs

Each API operation has a label indicating when it was introduced. For most operations, this label is 1.0:

```
## Get roles
Introduced 1.0
{: .label .label-purple }
```

If we introduce a breaking change to an operation, add an additional label with a link to the release note for that breaking change:

```
## Get roles
Introduced 1.0
{: .label .label-purple }
[Last breaking change 2.0](https://example.com)
{: .label .label-red }
```


## Math

If you want to use the sorts of pretty formulas that [MathJax](https://www.mathjax.org) allows, add `has_math: true` to the Jekyll page metadata. Then insert LaTeX math into HTML tags with the rest of your Markdown content:

```
## Math

Some Markdown paragraph. Here's a formula:

<p>
  When \(a \ne 0\), there are two solutions to \(ax^2 + bx + c = 0\) and they are
  \[x = {-b \pm \sqrt{b^2-4ac} \over 2a}.\]
</p>

And back to Markdown.
```


## Code of conduct

This project has adopted an [Open Source Code of Conduct](https://opensearch.org/codeofconduct.html).


## Security

See [CONTRIBUTING](CONTRIBUTING.md#security-issue-notifications) for more information.


## License

This project is licensed under the Apache-2.0 License.


## Copyright

Copyright OpenSearch contributors.
